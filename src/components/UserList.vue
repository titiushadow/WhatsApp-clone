<template>
    <div>
        <ul class="flex gap-4 flex-col w-[405px]">
            <li v-for="user in users" :key="user.login.uuid" class="flex items-center border-b w-calc[100%-80px] float-right">
                <img class="rounded-full ml-1 w-10" src="https://random.imagecdn.app/500/500" alt="">

                <div class="w-full">
                    <div class="flex justify-between items-center">
                    <span class="ml-2">{{ user.name.first }} {{ user.name.last }}</span>
                        <span class="text-[12px] text-gray-500">5:01</span>
                    </div>
                    <div class="flex items-center mx-2">
                        <CheckAllIcon :size="15" class="mr-1 text-blue-600" />
                        <span class="text-[15px] w-full text-gray-500 flex items-center justify-between">Isso é uma mensagem</span>
                    </div>
                </div>
            </li>
        </ul>
    </div>
</template>

<script>
import CheckAllIcon from 'vue-material-design-icons/CheckAll.vue'

export default {
    components: {
        CheckAllIcon
    },
    data() {
        return {
        users: [],
        };
    },
    mounted() {
        this.fetchUsers();
    },
    methods: {
        async fetchUsers() {
            try {
                const response = await this.$axios.get('https://randomuser.me/api/?results=5');
                this.users = response.data.results;
            } catch (error) {
                console.error('Erro ao buscar usuários:', error);
            }
        },
    },
};
</script>
