<template>
    <div class="component">
        <h3>You may view the User Details here</h3>
        <p>Many Details</p>
        <p>User Name: {{ switchName() }}</p>
        <p>User Age: {{ userAge }}</p>
        <button @click="resetName">Reset Name by $emit</button>
        <button @click="resetFn()">Reset Name by callback</button>
    </div>
</template>

<script>
    import { eventBus } from '../../main';

    export default {
        // Passing data from parent to child
        props: {
        // Validating string for "props"
            myName: {
                type: String,
                default: 'Max'
            },
            resetFn: Function,
            userAge: Number

        // Validating object for "props"
            // myName: {
            //     type: Object,
            //     default() {
            //         return {
            //             name: 'Max'
            //         }
            //     }
            // },

        // Multiple types
            // myName: {
            //     type: [String, Array],
            //     required: true // to make sure this is a property which always is a string with passing props.
            //     // it will overwritten by default, so either default or required
            // },

        },
        methods: {
            switchName() {
                return this.myName.split("").reverse().join("");
            },
            resetName() {
                // only changed it in the child component, so myName="Anna" in the parent component
                this.myName = 'Max';
                this.$emit('nameWasReset', this.myName);
            }
        },
        created() {
            // passing data from UserEdit component
            eventBus.$on('ageWasEdited', (age) => {
                this.userAge = age;
            });
        }
    }
</script>

<style scoped>
    div {
        background-color: lightcoral;
    }
</style>
