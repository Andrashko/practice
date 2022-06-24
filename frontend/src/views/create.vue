<template>
    <h1 class="header">Створення</h1>
    <form v-on:submit.prevent class="createCont">
        <label class="createQue">
            Запитання
            <input name="question"  v-model="faq.question">
        </label>
        <br>
        <label class="createAns">
            Відповідь
            <input name="answer"  v-model="faq.answer">
        </label>
        <br>
        <button @click="createFaq" class="btn">
            Створити
        </button>
    </form>
</template>

<script>
import network from '@/network';
export default {
    name: "CreateFaq",
    data() {
        return {
            faq: {
                question: "",
                answer: ""
            }
        }
    },
    methods: {
        async createFaq() {
            this.faq = await network.makeRequest("faq", "POST", this.faq );
            alert("Додано");
            setTimeout(() => this.$router.push("/"), 1000);
        }
    }
};
</script>

<style>
.createCont{
    font-size: 18px;
  font-family: 'Gill Sans', 'Gill Sans MT', Calibri, 'Trebuchet MS', sans-serif;
  margin-left: 650px;
}

</style>