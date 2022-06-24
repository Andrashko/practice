<template>
  <div v-if="faq">
    <div v-if="!isDeleted">
      Хочете вилучити запитання
      {{ faq.question }}
      <button @click="deleteFaq" class="yas">так</button>
      <button @click="returnToHomepage" class="yas">ні</button>
    </div>
    <div v-else>
      запитання вилучено
      {{ faq.question }}
    </div>
  </div>
  <div v-else>йде завантаження даних</div>
</template>

<script>
import network from "@/network";
export default {
  name: "DeleteFaq",
  data() {
    return {
      id: parseInt(this.$route.params.id),
      faq: null,
      isDeleted: false,
    };
  },
  async mounted() {
    await this.loadData();
  },
  methods: {
    async loadData() {
      this.faq = await network.makeRequest(`faq/${this.id}`);
    },
    async deleteFaq() {
      this.faq = await network.makeRequest(`faq/${this.id}`, "DELETE");
      this.isDeleted = true;
      setTimeout(() => this.returnToHomepage(), 3000);
    },
    returnToHomepage() {
      this.$router.push("/");
    },
  },
};
</script>

<style>
.yas{
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
.yas:hover {
  background: #2EE59D;
  box-shadow: 0 15px 20px rgba(46, 229, 157, .4);
  color: white;
  transform: translateY(-7px);
}

</style>