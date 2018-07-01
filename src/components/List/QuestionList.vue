<template>
    <div class="list" v-on:newQuestion="add">

    </div>    
</template>
<script>
import style from './question__list.css'


console.log('list');
export default {
    data() {
        return{
            questions: [],
        }
    },
    methods: {
        add() {
            this.$on('newQuestion', function (question) {
                console.log('a');
            })
        },
    },
}
</script>
