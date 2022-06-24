<template >
  <div class="container">
    <p class="question">{{ faq.question }}</p>
    <p class="answer">{{ faq.answer }}</p>
    <router-link :to="deleteLink" class="btn"> вилучити </router-link>
    <router-link :to="updateLink" class="btn"> редгувати </router-link>
  </div>
</template>

<script>
export default {
  props: {
    faq: Object,
  },
  name: "FaqList",
  data() {
    return {};
  },
  computed: {
    deleteLink() {
      return `/delete/${this.faq.id}`;
    },
    updateLink() {
      return `/update/${this.faq.id}`;
    },
  },
};
</script>

<style>
.btn {
    display: inline-flex;
    margin: 10px;
    text-decoration: none;
    position: relative;
    font-size: 20px;
    line-height: 20px;
    padding: 12px 30px;
    color: #FFF;
    font-weight: bold;
    text-transform: uppercase;
    font-family: 'Roboto Condensed', Тahoma, sans-serif;
    background: #337AB7;
    cursor: pointer;
    border: 2px solid #BFE2FF;
    outline: 1px solid;
    outline-color: #337AB7;
    outline-offset: 0px;
    text-shadow: none;
    transition: all 1.5s cubic-bezier(0.19, 1, 0.22, 1); 
}
.btn:hover,
.btn:active,
.btn:focus {
    box-shadow: inset 0 0 20px #BFE2FF;
    outline-color: rgba(255, 255, 255, 0);
    outline-offset: 15px;
    color: #FFF;
}
.container{
  border: 3px rgb(0, 153, 223) solid;
  width: 600px;
  margin-left: 400px;
  margin-top: 10px;
}
.question{
  font-size: 18px;
  font-family: 'Gill Sans', 'Gill Sans MT', Calibri, 'Trebuchet MS', sans-serif;
  margin-left: 25px;
}
.answer{
  font-size: 18px;
  font-family: 'Gill Sans', 'Gill Sans MT', Calibri, 'Trebuchet MS', sans-serif;
  margin-left: 25px;
}
</style>
