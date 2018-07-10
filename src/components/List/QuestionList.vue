<template>
    <div class="list" v-on:newQuestion="add">
        <div v-for="item in questions" v-bind:key="item">
            {{ item.img }}
        </div>
    </div>    
</template>
<script>
import style from './question__list.css'

// console.dir(this.$root)

console.log('list');
export default {
    data() {
        return{
            questions: [],
            ind: "",
        }
    },
    props: ['test'],
    methods: {
        add () {
            // console.log('from QuestionList');
            // console.log(this.test);
            this.questions.push(this.test);
            // return this.ind = 'this.test';
        }
    },
}
</script>
