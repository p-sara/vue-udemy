<template>
    <div>
        <button class="btn btn-danger" @click="asyncIncrement({by: 50, duration: 3000})">Increment</button>
        <button class="btn btn-danger" @click="asyncDecrement({by: 50, duration: 3000})">Decrement</button>
    </div>
</template>

<script>
    import { mapActions } from 'vuex';
    export default {
        methods: {
            ...mapActions([
                'asyncIncrement',
                'asyncDecrement'
            ])
        }
    }
</script>