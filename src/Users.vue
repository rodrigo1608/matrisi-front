<script setup>

import DefaultButton from './buttons/DefaultButton.vue';

// Você pode adicionar a lógica para buscar os usuários aqui
const users = [
    { id: 1, name: 'João Silva', email: 'joao.silva@example.com', role: 'Administrador' },
    { id: 2, name: 'Maria Souza', email: 'maria.souza@example.com', role: 'Editor' },
    { id: 3, name: 'Pedro Santos', email: 'pedro.santos@example.com', role: 'Usuário' },
    { id: 4, name: 'Ana Oliveira', email: 'ana.oliveira@example.com', role: 'Usuário' },
    { id: 5, name: 'Carlos Lima', email: 'carlos.lima@example.com', role: 'Usuário' },
    { id: 6, name: 'Fernanda Rocha', email: 'fernanda.rocha@example.com', role: 'Editor' },
    { id: 7, name: 'Bruno Costa', email: 'bruno.costa@example.com', role: 'Administrador' },
    { id: 8, name: 'Luiza Ferreira', email: 'luiza.ferreira@example.com', role: 'Usuário' },
    { id: 9, name: 'Ricardo Dias', email: 'ricardo.dias@example.com', role: 'Editor' },
    { id: 10, name: 'Mariana Pires', email: 'mariana.pires@example.com', role: 'Usuário' },
    { id: 11, name: 'Gustavo Neves', email: 'gustavo.neves@example.com', role: 'Administrador' },
    { id: 12, name: 'Isabela Mendes', email: 'isabela.mendes@example.com', role: 'Usuário' },
    { id: 13, name: 'Daniel Souza', email: 'daniel.souza@example.com', role: 'Editor' },
    { id: 14, name: 'Patrícia Gomes', email: 'patricia.gomes@example.com', role: 'Usuário' },
    { id: 15, name: 'Marcelo Pires', email: 'marcelo.pires@example.com', role: 'Usuário' },
    { id: 16, name: 'Aline Martins', email: 'aline.martins@example.com', role: 'Editor' },
    { id: 17, name: 'Felipe Cabral', email: 'felipe.cabral@example.com', role: 'Usuário' },
    { id: 18, name: 'Juliana Castro', email: 'juliana.castro@example.com', role: 'Administrador' },
    { id: 19, name: 'Lucas Gomes', email: 'lucas.gomes@example.com', role: 'Usuário' },
    { id: 20, name: 'Camila Ribeiro', email: 'camila.ribeiro@example.com', role: 'Usuário' },
    { id: 21, name: 'Rafael Santos', email: 'rafael.santos@example.com', role: 'Editor' },
    { id: 22, name: 'Beatriz Almeida', email: 'beatriz.almeida@example.com', role: 'Usuário' },
    { id: 23, name: 'Vinícius Fernandes', email: 'vinicius.fernandes@example.com', role: 'Administrador' },
    { id: 24, name: 'Sophia Costa', email: 'sophia.costa@example.com', role: 'Usuário' },
    { id: 25, name: 'Eduardo Pereira', email: 'eduardo.pereira@example.com', role: 'Usuário' },
    { id: 26, name: 'Gabriela Nunes', email: 'gabriela.nunes@example.com', role: 'Editor' },
    { id: 27, name: 'Henrique Cardoso', email: 'henrique.cardoso@example.com', role: 'Usuário' },
    { id: 28, name: 'Larissa Lima', email: 'larissa.lima@example.com', role: 'Administrador' },
    { id: 29, name: 'Tiago Santos', email: 'tiago.santos@example.com', role: 'Usuário' },
    { id: 30, name: 'Letícia Ferreira', email: 'leticia.ferreira@example.com', role: 'Usuário' },
]


const tableHeaders = ['ID', 'Nome', 'Email', 'Permissão', 'Ações'];

const requestNewUser = () => console.log('Create new user requested')

</script>

<template>

    <div class="flex flex-col gap-1 h-full flex-1">

        <header class="bg-elight text-lg px-4 py-2 rounded-t-2xl flex justify-between items-center">

            <h1 class="font-[Crimson_Pro] text-lg font-semibold">User Management</h1>

            <DefaultButton @click='requestNewUser' :iconClasses="'fa-solid fa-user-plus'" :label="'create user'"
                :aria-label="'Button to request to create a new user'" />

        </header>

        <div class="bg-elight overflow-y-auto">

            <table class="divide-y   h-90">

                <thead class="bg-elight sticky top-0 z-10">
                    <tr>
                        <th v-for="header in tableHeaders" :key="header" scope="col"
                            class="px-6 py-3 text-left text-xs font-semibold text-edark-gray uppercase tracking-wider"
                            :class="{ 'relative': header === 'Ações' }">
                            <span v-if="header === 'Ações'" class="sr-only">{{ header }}</span>
                            <span v-else>{{ header }}</span>
                        </th>
                    </tr>
                </thead>
                <tbody class="bg-elight divide-y divide-gray-200">
                    <tr v-for="user in users" :key="user.id">
                        <td class="px-6 py-4 whitespace-nowrap text-sm font-medium text-edark-gray">{{ user.id }}</td>
                        <td class="px-6 py-4 whitespace-nowrap text-sm">{{ user.name }}</td>
                        <td class="px-6 py-4 whitespace-nowrap text-sm">{{ user.email }}</td>
                        <td class="px-6 py-4 whitespace-nowrap text-sm">{{ user.role }}</td>
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
