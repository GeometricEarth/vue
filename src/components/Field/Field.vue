<template>
    <form class="field" v-on:submit.prevent='save_Question'>
        <h2 class="field_header">Добавить вопрос</h2>

        <img class="field_load_img" v-bind:src="img" >

        <textarea class="field_question" 
            name="question" 
            placeholder="Текст вопроса"
            rows="4" 
            spellcheck 
            autocomplete="off"
            v-model="question">
        </textarea>
        <div>
            <div class="roundedOne">
                <input type="radio" id="roundedOne1" name="true" value="1"/>
                <label for="roundedOne1"></label>
            </div>
            <input name="inp" class="field_answer" id="inp1" placeholder="Вариант ответа 1" type="text" spellcheck autocomplete="off" >
        </div>    
        <div>  
            <div class="roundedOne">
                <input type="radio" id="roundedOne2" name="true" value="2"/>
                <label for="roundedOne2"></label>
            </div>
            <input name="inp" class="field_answer" id="inp2" placeholder="Вариант ответа 2" type="text" spellcheck autocomplete="off">
        </div>
        <div>
            <div class="roundedOne">
                <input type="radio" id="roundedOne3" name="true" value="3"/>
                <label for="roundedOne3"></label>
            </div>
            <input name="inp" class="field_answer" id="inp3" placeholder="Вариант ответа 3" type="text" spellcheck autocomplete="off">
        </div>
        <div>
            <div class="roundedOne">
                <input type="radio" id="roundedOne4" name="true" value="4"/>
                <label for="roundedOne4"></label>
            </div>
            <input name="inp" class="field_answer" id="inp4" placeholder="Вариант ответа 4" type="text" spellcheck autocomplete="off">
        </div>
        <div class="field_control">
        <input type="submit" class="field_submit field_button" value="Отправить" >
        <button type="reset" class="field_button">Очистить</button>
        </div>
    </form>
</template>

<style>
</style>


<script>
import style from "../Field/field.css";

export default {
  name: "Field",
  methods: {
    save_Question: function(event) {
      event.preventDefault();
      let form = event.target;
      let radio_btn = Array.from(form.true);
      let inputs = form.inp;
      let question = {
        question: form.question.value,
        true_answer: "",
        answers: [],
        img: "./src/assets/no-image-icon.png"
      };
      radio_btn.forEach((element, id, arr) => {
        if (element.checked) {
          question.true_answer = element.value;
        }
      });

      inputs.forEach(element => {
        question.answers.push(element.value);
      });
    
      this.$emit("newQuestion", question);
      this.$el.scrollIntoView(false);
    }
  },
  data() {
    return {
        question: null,
        true_answer: null,
        img: "./src/assets/no-image-icon.png",
        answers: [],
    };
  }
};
</script>
