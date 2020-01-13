<template>
    <li
            class="list-group-item"
            style="cursor: pointer"
            @click="serverSelected">
            Server #{{ myServer.id }}
    </li>
</template>

<script>
    import { serverBus } from '../../main';

    export default {
        // passing data from Servers.vue to Server.vue by props [parent to child]
        props: ['myServer'],
        methods: {
            // passing data to from Server to Servers
            serverSelected() {
                serverBus.$emit('serverSelected', this.myServer);
            }
        }
    }
</script>

<style>

</style>
