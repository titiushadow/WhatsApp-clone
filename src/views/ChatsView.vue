<template>
    <div id="Messages" class="w-full">
        <div class="w-full">
            <div class="border-l w-full">
                <div 
                    class="
                        bg-[#F0F0F0] 
                        fixed
                        ml-[620px]
                        z-10 
                        min-w-[calc(100vw-420px)] 
                        flex 
                        justify-between 
                        items-center
                        px-2
                        py-2
                    "
                >

                    <div class="flex items-center">
                        <img class="rounded-full ml-1 w-10" src="https://random.imagecdn.app/100/100" alt="">

                        <div v-for="user in users" :key="user.login.uuid" class="text-gray-900 ml-1 font-semibold">
                            {{ user.name.first }}
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
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
                    const response = await this.$axios.get('https://randomuser.me/api/?results=1');
                    this.users = response.data.results;
                } catch (error) {
                    console.error('Erro ao buscar usuários:', error);
                }
            },
        },
    };
</script>

<style lang="scss" scoped></style>