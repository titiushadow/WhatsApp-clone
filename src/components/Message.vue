
<template>
  <div class="flex w-full px-2 py-3 items-center cursor-pointer">
    <UserList 
      class="mt-2"
    />
  </div>
</template>

<script>
    import UserList from '../components/UserList.vue';

    export default {
        components: {
            UserList,
        },
    };
</script>

