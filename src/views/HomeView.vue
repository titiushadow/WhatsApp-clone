<template>
    <div class="flex">
        <div id="Header" class="fixed w-[420px] z-10">

            <!-- Header -->
            <div class="bg-[#F0F0F0] w-full flex justify-between items-center px-3 py-2">
                <img class="rounded-full ml-1 w-10" src="https://random.imagecdn.app/100/100" alt="">
                <div class="flex items-center justify-center gap-4">
                    <AccountGroupIcon fillColor="#515151" class="cursor-pointer" />
                    <CircleSlice6 fillColor="#515151" class="cursor-pointer" />
                    <Newspaper fillColor="#515151" class="cursor-pointer" />
                    <DotsVertical fillColor="#515151" class="cursor-pointer" />
                </div>
            </div>

            <!-- Serch field -->
            <div id="Search" class="bg-white w-full px-2 py-2 border-b shadow-sm">
                <div class="px-1 bg-[#F0F0F0] flex items-center justify-center rounded-md">
                    <Magnify fillColor="#515151" :size="18" class="ml-2" />
                    <input 
                    class="
                        ml-5 
                        appearance-none 
                        w-full 
                        bg-[#F0F0F0] 
                        py-1.5 
                        px-2.5 
                        text-gray-700
                        focus:outline-none
                        focus:shadow-outline
                        placeholder:text-sm
                        placeholder:text-gray-500
                    " 

                    autocomplete="off"
                    type="text"
                    placeholder="Pesquisar ou começar uma nova conversa"
                    >
                </div>
            </div>
        </div>

        
        <Message class="mt-[100px]" />
        <ChatsView />

        <div v-if="open">
            <ChatsView />
        </div>

        <div v-else>
            <div class="ml-[420px] fixed w-[calc(100vw-420px)] h-[100vh] bg-gray-100 text-center">
                <div class="grid h-screen place-items-center">
                    <div>
                        <div class="w-full flex items-center justify-center">
                            <img width="375px" src="https://random.imagecdn.app/400/200" alt="">
                        </div>
                        <div class="text-[32px] text-gray-500 font-light mt-10">
                            WhatsApp Web
                        </div>
                        <div class="text-[14px] text-gray-600 font-light mt-2">
                            <div>Envie e receba mensagens sem manter seu telefone online.</div>
                            <div>Use o WhatsApp em até 4 dispositivos vinculados e 1 telefone ao mesmo tempo.</div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script setup>
    import ChatsView from './ChatsView.vue'
    import Message from '../components/Message.vue'
    import AccountGroupIcon from 'vue-material-design-icons/AccountGroup.vue'
    import DotsVertical from 'vue-material-design-icons/DotsVertical.vue'
    import Magnify from 'vue-material-design-icons/Magnify.vue'
    import Newspaper from 'vue-material-design-icons/Newspaper.vue'
    import CircleSlice6 from 'vue-material-design-icons/CircleSlice6.vue'
    import { ref } from 'vue'

    let open = ref(true)
</script>

<style lang="scss" scoped></style>