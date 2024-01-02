<template>
    <div id="Messages" class="ml-[420px] fixed">
        <div class="w-full">
            <div class="border-l w-full">
                <div 
                    class="
                        bg-[#F0F0F0] 
                        fixed
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

                    <div class="flex gap-6">
                        <Magnify class="cursor-pointer" />
                        <DotsVertical class="cursor-pointer" />
                    </div>
                </div>
            </div>
            
            <div id="MessageSection" class="pt-20 pb-8 z-[-1] h-[calc(100vh-65px)] overflow-auto fixed touch-auto">
                <div class="px-20 text-sm">
                    <div class="flex w-[calc(100%-50px)]">
                        <div class="inline-block bg-white shadow-md p-2 rounded-md my-1 text-justify">
                            Lorem, ipsum dolor sit amet consectetur adipisicing elit. Quam ullam iure repudiandae, voluptatem earum consequatur optio, eos vero odio eum iusto reprehenderit dignissimos ad ea quo perspiciatis odit blanditiis temporibus.
                        </div>
                    </div>

                    <div class="flex justify-end space-x-1 w-[calc(100%-50px)] float-right">
                        <div class="inline-block bg-green-200 p-2 rounded-md my-1 text-justify">
                            Lorem, ipsum dolor sit amet consectetur adipisicing elit. Quam ullam iure repudiandae, voluptatem earum consequatur optio, eos vero odio eum iusto reprehenderit dignissimos ad ea quo perspiciatis odit blanditiis temporibus.
                        </div>
                    </div>

                    <div class="flex w-[calc(100%-50px)]">
                        <div class="inline-block bg-white shadow-md p-2 rounded-md my-1 text-justify">
                            Lorem, ipsum dolor sit amet consectetur adipisicing elit. Quam ullam iure repudiandae, voluptatem earum consequatur optio, eos vero odio eum iusto reprehenderit dignissimos ad ea quo perspiciatis odit blanditiis temporibus.
                        </div>
                    </div>
                </div>    
            </div>
            
            
            <div class="w-[calc(100vw-420px)] p-2.5 z-10 bg-[#F0F0F0] fixed bottom-0">
                <div class="flex items-center justify-center">
                    <EmoticonExcitedOutline :size="27" fillColor="#515151" class="mx-1.5 cursor-pointer" />
                    <Paperclip :size="27" fillColor="#515151" class="mx-1.5 mr-3 cursor-pointer" />
                    
                    <input 
                    class="
                        mr-1
                        shadow-md
                        appearance-none 
                        w-full 
                        py-3
                        px-4 
                        text-gray-700
                        focus:outline-none
                        focus:shadow-outline
                        placeholder:text-sm
                        rounded-md
                    " 
        
                        autocomplete="off"
                        type="text"
                        placeholder="Digite uma mensagem"
                    >

                    <button class="ml-3 p-2 flex items-center justify-center">
                        <Send fillColor="#515151" />
                    </button>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
import Magnify from 'vue-material-design-icons/Magnify.vue'
import DotsVertical from 'vue-material-design-icons/DotsVertical.vue'
import EmoticonExcitedOutline from 'vue-material-design-icons/EmoticonExcitedOutline.vue'
import Paperclip from 'vue-material-design-icons/Paperclip.vue'
import Send from 'vue-material-design-icons/Send.vue'

    export default {
        components: {
            DotsVertical,
            Magnify,
            EmoticonExcitedOutline,
            Paperclip,
            Send
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