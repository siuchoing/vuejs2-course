<template>
    <div class="container">
        <session title="server">
            <app-header></app-header>
            <hr>
            <div class="row">
                <servers></servers>
                <app-server-details></app-server-details>
            </div>
            <hr>
            <app-footer></app-footer>
        </session>
        <hr>
        <session title="user">
            <user></user>
        </session>

    </div>
</template>

<script>
    import User from './components/User/User.vue';
    import Header from './components/Shared/Header.vue';
    import Footer from './components/Shared/Footer.vue';
    import Servers from './components/Server/Servers.vue';
    import ServerDetails from './components/Server/ServerDetails.vue';

    export default {
        components: {
            appHeader: Header,
            Servers: Servers,
            'app-server-details': ServerDetails,
            'app-footer': Footer,
            'user': User
        }
    }
</script>

<style>

</style>
