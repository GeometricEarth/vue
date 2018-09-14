<template>
    <div class="list">
        <!-- <ul>
            <li v-for="item in questions" :key="item.id">
                {{item.question}}
            </li>
        </ul> -->
        <div class="question" 
            v-for="item in questions" 
            v-bind:key="item.id"
            @click="expand"
            >
                    <button class="question-accordion">
            <span class="question-num">{{item.id}}</span>
            <span class="question-button">{{item.question}}</span>
        </button>
        <div class="question-panel">
            <!-- <img class="question-icon" src={{item.img}}> -->
            <p>
                <span class="question-answer-num question-rightAnswer">1</span>
                <span class="question-answer">{{item.answers[0]}}</span>
            </p>
            <p>
                <span class="question-answer-num">2</span>
                <span class="question-answer">{{item.answers[1]}}</span>
            </p>
            <p>
                <span class="question-answer-num">3</span>
                <span class="question-answer">{{item.answers[2]}}</span>
            </p>
            <p>
                <span class="question-answer-num">4</span>
                <span class="question-answer">{{item.answers[3]}}</span>
                </p>
            <div class="question-control">
                <button class="field_button">Редактировать</button>
            </div>
        </div>
        </div>
        <!-- <div>{{ questions.true_answer }}</div> -->
    </div>    
</template>
<script>
import style from './question__list.css'

// console.dir(this.$root)

console.log('list');
export default {
    data() {
        return{
            // ind: "",
        }
    },
    props: ['questions', 'ind'],
    methods: {
        expand(event) {
        let target = event.target.closest(".question-accordion");
        target.classList.toggle("active");
        let panel = target.nextElementSibling;
        if (panel.style.maxHeight) {
            panel.style.maxHeight = null;
        } else {
            panel.style.maxHeight = panel.scrollHeight + "px";
        }
    }
        // add () {
        //     // console.log('from QuestionList');
        //     console.log(this.test);
        //     console.log('Testing');
            
        //     // this.questions.push(this.test);
        //     return this.ind = 'this.test';
        // }
    },
}
</script>
