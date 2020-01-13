<template>
    <div class="col-xs-12 col-sm-6">
        <p v-if="!server">Please select a Server</p>
        <p v-else>Server # {{ server.id }} selected, Status: {{ server.status }}</p>
        <hr>
        <button @click="resetStatus">Change to Normal</button>
    </div>

</template>

<script>
    import { serverBus } from '../../main';

    export default {
        data: function () {
            return {
                server: null    // it is undefined
            }
        },
        methods: {
            resetStatus() {
                // it will store in Server.vue because it is object type
                this.server.status = 'Normal';
            }
        },
        created() {
            // listen to serverBus, and get serverSelected from Server.vue
            serverBus.$on('serverSelected', (server) => {
                this.server = server; // that allows to access the server id
            });
        }
    }
</script>

<style>

</style>
