<template>
    <div class="component">
        <h3>You may edit the User here</h3>
        <p>Edit me!</p>
        <p>User Age: {{ userAge }}</p>
        <button @click="editAge">Edit Age</button>
    </div>
</template>

<script>
    import { eventBus } from '../../main';

    export default {
        props: ['userAge'],
        methods: {
            editAge () {
                this.userAge = 30;
                //this.$emit('ageWasEdited', this.userAge);      // passing data (age) between all parent components [child to parent]
                //eventBus.$emit('ageWasEdited', this.userAge);  // passing data (age) between UserEdit and UserDetail [child to child]
                eventBus.changeAge(this.userAge);                // passing data (age) centrally between all child components [child to child]
            }
        }
    }
</script>

<style scoped>
    div {
        background-color: lightgreen;
    }
</style>
