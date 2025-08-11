<script setup>
import { ref } from 'vue'
import UserFormInput from '@/forms/UserFormInput.vue';

// Variaveis reativas para os campos do formulario
const userData = ref({
    firstname: '',
    lastname: '',
    email: '',
    password: '',
})

const inputsAttributes = ref(
    [
        {
            forId: 'firstname',
            labelClasses: 'text-sm ml-4 tracking-wider block mb-1',
            type: 'text',
            name: 'firstname',
            inputClasses: 'rounded-full py-2 px-4 focus:pl-6 transition-[padding] ease-in-out bg-elighter w-full'
        },
        {
            forId: 'lastname',
            labelClasses: 'text-sm ml-4 tracking-wider block mb-1',
            type: 'text',
            name: 'lastname',
            inputClasses: 'rounded-full py-2 px-4 focus:pl-6 transition-[padding] ease-in-out bg-elighter w-full'
        },
        {
            forId: 'email',
            labelClasses: 'text-sm ml-4 tracking-wider block mb-1',
            type: 'email',
            name: 'email',
            inputClasses: 'rounded-full py-2 px-4 focus:pl-6 transition-[padding] ease-in-out bg-elighter w-full'
        },
        {
            forId: 'password',
            labelClasses: 'text-sm ml-4 tracking-wider block mb-1',
            type: 'password',
            name: 'password',
            inputClasses: 'rounded-full py-2 px-4 focus:pl-6 transition-[padding] ease-in-out bg-elighter w-full'
        }

    ]
)

const registerUser = () => {

    const users = JSON.parse(localStorage.getItem('users')) ?? []

    users.push({ ...userData.value });

    localStorage.setItem('users', JSON.stringify(users))
}
</script>

<template>

    <div class="mt-8 mx-auto sm:max-w-md flex flex-col gap-1 ">
        <div class="bg-elight font-[Crimson_Pro] text-lg px-4 rounded-t-2xl font-semibold">Register
            New
            User
        </div>

        <form action="" class="p-4 space-y-6 bg-elight py-8 ">
            <UserFormInput v-for="input in inputsAttributes" :input=input :key="input.forId"
                v-model="userData[input.name]" />
        </form>

        <div class="bg-elight 
        text-lg p-4 
        rounded-b-2xl 
        flex justify-end 
        font-semibold">

            <button @click=registerUser class="bg-edark-gray 
                text-elight px-4 py-2 
                text-sm font-medium 
                rounded-full 
                hover:bg-edark 
                cursor-pointer 
                active:scale-99 
                active:bg-edarker">

                <i class="fa-solid fa-arrow-right mr-2"></i>
                Register
            </button>

        </div>

    </div>

</template>