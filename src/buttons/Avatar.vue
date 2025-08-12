<template>
    <button
        class="group relative cursor-pointer flex items-center justify-center w-8 h-8 rounded-full font-medium overflow-hidden transition-colors "
        @click="handleClick" :aria-label="ariaLabel">

        <img v-if="imageUrl && !imageLoadError" :src="imageUrl" :alt="altText" class="object-cover w-full h-full"
            @error="handleImageError" />
        <span v-else-if="!imageLoadError" class="bg-gray-200 w-full h-full flex items-center justify-center">{{ initials
            }}</span>

        <div class="absolute inset-0 bg-black opacity-0 group-hover:opacity-20 transition-opacity duration-200"></div>
    </button>
</template>

<script>
export default {
    name: 'UserAvatar',
    props: {
        imageUrl: {
            type: String,
            default: '',
        },
        name: {
            type: String,
            default: 'Usuário',
        },
    },
    data() {
        return {
            imageLoadError: false,
        };
    },
    computed: {
        initials() {
            if (this.name) {
                const parts = this.name.split(' ');
                if (parts.length > 1) {
                    return parts[0][0].toUpperCase() + parts[parts.length - 1][0].toUpperCase();
                }
                return parts[0][0].toUpperCase();
            }
            return '?';
        },
        altText() {
            return `Avatar do usuário ${this.name}`;
        },
        ariaLabel() {
            return `Botão do menu do usuário. Avatar de ${this.name}`;
        }
    },
    methods: {
        handleImageError() {
            this.imageLoadError = true;
        },
        handleClick() {
            this.$emit('click');
            // Lógica adicional, como abrir um menu de usuário
        },
    },
};
</script>