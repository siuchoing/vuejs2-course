<template>
    <div class="component">
        <h3>You may view the User Details here</h3>
        <p>Many Details {{ switchName() }}</p>
    </div>
</template>

<script>
    export default {
        props: {
        // Validating string for "props"
            myName: {
                type: String
                default: 'Max'
            },

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
            }
        }
    }
</script>

<style scoped>
    div {
        background-color: lightcoral;
    }
</style>
