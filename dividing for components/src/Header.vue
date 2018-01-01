<template>
    <div class="row">
        <div class="col-xs-12">
            <header>
                <h1>Server Status</h1>
            </header>
            <p>User age: {{userAge}} </p>
            <button @click="editAge">Edit age</button>
        </div>
    </div>
</template>
<script>
    import { eventBus } from './main'

    export default {
        props: ['userAge'],
        methods: {
            editAge: function() {
                this.userAge = 30;
                this.$emit('ageWasReset', this.userAge);
                //eventBus.$emit('ageWasReset', this.userAge);
            }
        }
    }

</script>