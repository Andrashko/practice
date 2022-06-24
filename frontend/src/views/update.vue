<template>
  <h1>Редагування</h1>
  <form v-on:submit.prevent>
    <label>
      Запитання
      <input name="question" v-model="faq.question" />
    </label>
    <br />
    <label>
      Відповідь
      <input name="answer" v-model="faq.answer" />
    </label>
    <br />
    <button @click="updateFaq" class="rgd">редгувати</button>
  </form>
</template>

<script>
import network from "@/network";
export default {
  name: "UpdateFaq",
  data() {
    return {
      faq: {
        question: "",
        answer: "",
      },
      id: parseInt(this.$route.params.id),
    };
  },
  async mounted() {
    await this.loadData();
  },
  methods: {
    async loadData() {
      this.faq = await network.makeRequest(`faq/${this.id}`);
    },
    async updateFaq() {
      this.faq = await network.makeRequest(`faq/${this.id}`, "PUT", this.faq);
      alert("Оновлено");
      setTimeout(() => this.$router.push("/"), 1000);
    },
  },
};
</script>

<style>
.rgd{
  text-decoration: none;
  display: inline-block;
  width: 140px;
  height: 45px;
  line-height: 45px;
  border-radius: 45px;
  margin: 10px 20px;
  font-family: 'Montserrat', sans-serif;
  font-size: 11px;
  text-transform: uppercase;
  text-align: center;
  letter-spacing: 3px;
  font-weight: 600;
  color: #524f4e;
  background: white;
  box-shadow: 0 8px 15px rgba(0, 0, 0, .1);
  transition: .3s;
}
.floating-button:hover {
  background: #2EE59D;
  box-shadow: 0 15px 20px rgba(46, 229, 157, .4);
  color: white;
  transform: translateY(-7px);
}

</style>