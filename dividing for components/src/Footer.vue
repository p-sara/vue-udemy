<template>
    <div class="row">
        <div class="col-xs-12">
            <p>User name: <b>{{ nameFoot }}</b></p>
            <button @click="resetName">Reset name</button>
            <button @click="resetFn()">Reset name</button>
            <footer>
                <p>All Servers are managed here</p>
            </footer>
            <p>User age: {{userAge}}</p>
        </div>
    </div>
</template>
<script>
import {eventBus} from './main'

 export default {
     props: {
         nameFoot: {
             type: String
         },
         resetFn: Function,
         userAge: Number
     },
     methods: {
        resetName: function () {
            this.nameFoot = 'Sara';
            this.$emit('nameWasReset', this.nameFoot)
        }
     },
     created() {
         eventBus.$on('ageWasEdited', (age) =>
         this.userAge = age)
     }
 }
</script>