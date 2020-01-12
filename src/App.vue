<template>
    <div class="container">
        <app-header></app-header>
        <hr>
        <div class="row">
            <app-servers></app-servers>
        </div>
        <hr>
    </div>
</template>

<script>
    import Header from './Header.vue';
    import Servers from './Servers.vue';

    export default {
        components: {
            'app-header': Header,
            'app-servers': Servers,
        }
    }
</script>

<style>

</style>
