<template>
    <li
            class="list-group-item"
            style="cursor: pointer">
        Server #{{ id }}
    </li>
</template>

<script>
    export default {
        // passing id from Servers.vue to Server.vue by props [parent to child]
        props: ['id'],
    }
</script>

<style>

</style>
