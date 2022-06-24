<template>
  <li>
    <p>{{ faq.question }}</p>
    <p>{{ faq.answer }}</p>
    <router-link :to="deleteLink" class="yas"> вилучити </router-link>
    <router-link :to="updateLink" class="yas"> редгувати </router-link>
  </li>
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
</style>
