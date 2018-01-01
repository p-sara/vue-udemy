<template>
    <div class="container">
        <button class="primary"
                @click="changeName">Change name</button>
        <p>Name is: {{nameApp}}</p>
        <app-header
        :userAge = "age"
        ></app-header>
        <hr>
        <all-servers></all-servers>
        <hr>
        <app-footer
          :nameFoot="nameApp"
          @nameWasReset="nameApp = $event"
          :resetFn="resetNameCallback"
          :userAge = "age"
          @ageWasEdited="age = $event"
        ></app-footer>
    </div>
</template>

<script>
    import AllServers from './AllServers.vue';
    import Header from './Header.vue';
    import Footer from './Footer.vue';

    export default {
        data() {
            return {
                nameApp: 'Sara',
                age: 27
            }
        },
        components: {
            'app-header': Header,
            'all-servers': AllServers,
            'app-footer': Footer
        },
        methods: {
            changeName() {
                this.nameApp = 'Andrej'
            },
            resetNameCallback() {
                this.nameApp = 'Sara'
            }
        }
    }
</script>

<style>

</style>
