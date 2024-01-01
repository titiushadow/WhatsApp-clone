<template>
    <div class="flex">
        <div id="Header" class="fixed w-[420px] z-10">

            <!-- Header -->
            <div class="bg-[#F0F0F0] w-full flex justify-between items-center px-3 py-2">
                <img class="rounded-full ml-1 w-10" src="https://random.imagecdn.app/100/100" alt="">
                <div class="flex items-center justify-center">
                    <AccountGroupIcon fillColor="#515151" class="mr-6" />
                    <DotsVertical fillColor="#515151" class="cursor-pointer" />
                </div>
            </div>

            <!-- Serch field -->
            <div id="Search" class="bg-white w-full px-2 border-b shadow-sm">
                <div class="px-1 m-2 bg-[#F0F0F0] flex items-center justify-center rounded-md">
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

        <ChatsView class="mt-[100px]" />

        <div class="ml-[420px] fixed w-[calc(100vw-420px)] h-[100vh] bg-gray-100 text-center"></div>
    </div>
</template>

<script setup>
    import ChatsView from './ChatsView.vue'
    import Message from '../components/Message.vue'
    import AccountGroupIcon from 'vue-material-design-icons/AccountGroup.vue'
    import DotsVertical from 'vue-material-design-icons/DotsVertical.vue'
    import Magnify from 'vue-material-design-icons/Magnify.vue'
</script>

<style lang="scss" scoped></style>