<script setup>

import DefaultButton from './buttons/DefaultButton.vue';

// Você pode adicionar a lógica para buscar os usuários aqui
const users = [
    { id: 1, name: 'João Silva', email: 'joao.silva@example.com', role: 'Administrador' },
    { id: 2, name: 'Maria Souza', email: 'maria.souza@example.com', role: 'Editor' },
    { id: 3, name: 'Pedro Santos', email: 'pedro.santos@example.com', role: 'Usuário' },
    { id: 4, name: 'Ana Oliveira', email: 'ana.oliveira@example.com', role: 'Usuário' },
]

const requestNewUser = () => console.log('Create new user requested')

</script>

<template>

    <div class="flex flex-col gap-1">

        <header class="bg-elight text-lg px-4 py-2 px-4 rounded-t-2xl flex justify-between">
            <h1 class="font-[Crimson_Pro]  text-lg font-semibold">User Management</h1>
            <DefaultButton @click='requestNewUser' :iconClasses="'fa-solid fa-user-plus'" :label="'create user'"
                :aria-label="'Button to request to create a new user'" />
        </header>

        <div class="bg-white rounded-xl shadow overflow-hidden">
            <table class="min-w-full divide-y divide-gray-200">
                <thead class="bg-gray-50">
                    <tr>
                        <th scope="col"
                            class="px-6 py-3 text-left text-xs font-medium text-gray-500 uppercase tracking-wider">ID
                        </th>
                        <th scope="col"
                            class="px-6 py-3 text-left text-xs font-medium text-gray-500 uppercase tracking-wider">Nome
                        </th>
                        <th scope="col"
                            class="px-6 py-3 text-left text-xs font-medium text-gray-500 uppercase tracking-wider">Email
                        </th>
                        <th scope="col"
                            class="px-6 py-3 text-left text-xs font-medium text-gray-500 uppercase tracking-wider">
                            Permissão</th>
                        <th scope="col" class="relative px-6 py-3"><span class="sr-only">Ações</span></th>
                    </tr>
                </thead>
                <tbody class="bg-white divide-y divide-gray-200">
                    <tr v-for="user in users" :key="user.id">
                        <td class="px-6 py-4 whitespace-nowrap text-sm font-medium text-gray-900">{{ user.id }}</td>
                        <td class="px-6 py-4 whitespace-nowrap text-sm text-gray-500">{{ user.name }}</td>
                        <td class="px-6 py-4 whitespace-nowrap text-sm text-gray-500">{{ user.email }}</td>
                        <td class="px-6 py-4 whitespace-nowrap text-sm text-gray-500">{{ user.role }}</td>
                        <td class="px-6 py-4 whitespace-nowrap text-right text-sm font-medium">
                            <a href="#" class="text-indigo-600 hover:text-indigo-900 mr-4">Editar</a>
                            <a href="#" class="text-red-600 hover:text-red-900">Excluir</a>
                        </td>
                    </tr>
                </tbody>
            </table>
        </div>

    </div>
</template>