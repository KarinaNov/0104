<template>
  <div class="wrapper">
    <UserInfo />
    <Rewiews :reviews="reviews" />
    <SendForm :reviews="reviews" @add-review="addNewReview" />
  </div>
</template>

<script>
import Rewiews from "@/components/Rewiews.vue";
import UserInfo from "../components/UserInfo";
import SendForm from "../components/SendForm";
export default {
  components: {
    UserInfo,
    Rewiews,
    SendForm,
  },
  data() {
    return {
      reviews: [
        {
          author: "Samuel Jackson",
          text: "Hey Eva! You're cool. Nice pic!",
          date: "13 Apr 2022",
        },
        {
          author: "Angela Deimon",
          text: "Thanks for your services! We really liked the ocean view room. We hope to cooperate in the near future. We are sure you will do everything to make our next holiday fantastic.",
          date: "10 Apr 2022",
        },
        {
          author: "Ronald Harris",
          text: "Eva, hello! There is such a question: How can I contact you if I am abroad in roaming?",
          date: "8 Apr 2022",
        },
      ],
    };
  },
  methods: {
    addNewReview(review) {
      this.reviews.push(review);
    },
  },
};
</script>

<style lang="scss">


</style>
