<template>
  <form class="send-form" @submit.prevent>
    <textarea
      v-model="text"
      class="send-form__textarea"
      @keydown.enter.ctrl="onSubmitRewiew"
    ></textarea>
    <button class="send-form__btn" type="submit" @click="onSubmitRewiew">
      Send a message
    </button>
  </form>
</template>

<script>
export default {
  name: "ReviewForm",
  props: {
    reviews: {
      type: Array,
      required: true,
    },
  },
  emits: ["add-review"],
  data() {
    return {
      text: "",
    };
  },
  methods: {
    getDate() {
      const date = {
        day: "numeric",
        year: "numeric",
        month: "short",
      };
      return new Date().toLocaleString("en-GB", date);
    },
    onSubmitRewiew() {
      if (!this.text) {
       return alert('Enter review!!')
      }
      this.$emit("add-review", {
        author: "Somebody",
        text: this.text,
        date: this.getDate(),
      });
      this.text = "";
    },
  },
};
</script>

<style lang="scss" scoped>
.send-form {
  display: flex;
  flex-direction: column;
  align-items: center;
  padding: 28px 21px 34px 21px;
  background-color: #f2f2f2;

  &__textarea {
    max-width: 100%;
    width: 100%;
    min-height: 63px;
    margin-bottom: 23px;
    padding: 4px;
    border: 1px solid #000000;
    border-radius: 1px;
    resize: none;
  }

  &__btn {
    font-family: "PT Sans", sans-serif;
    font-weight: 700;
    font-size: 16px;
    padding: 12px 48px;
    background-color: #fdd639;
    border-radius: 23px;
  }
}
</style>
