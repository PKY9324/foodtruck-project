<template>
  <div class="container__save__button">
    <button class="save__button" @click="cancle">취소</button>
    <button class="cancle__button" @click="save">저장</button>
  </div>
</template>

<script>
import { mapGetters } from "vuex";

export default {
  computed: {
    ...mapGetters(["star", "review", "user"])
  },
  methods: {
    save(e) {
      const payload = {
        star: this.star,
        review: this.review,
        user: this.user,
        objectID: this.$route.params.objectID
      };
      this.$store.dispatch("SubmitSaveButton", payload);
      this.$router.go(-1);
    },
    cancle(e) {
      this.$store.dispatch("CancleButton");
      this.$router.go(-1);
    }
  }
};
</script>

<style>
.save__button {
  all: unset;
  min-width: 140px;
  min-height: 50px;
  margin-right: 34px;
  border: 1px solid #cbcbcb;
  border-radius: 50px;
  font-size: 16px;
  color: #7f7f7f;
  text-align: center;
  background-color: #ffffff;
  cursor: pointer;
}

.cancle__button {
  all: unset;
  position: relative;
  min-width: 140px;
  min-height: 50px;
  border: 1px solid #3498db;
  border-radius: 50px;
  font-size: 16px;
  color: #ffffff;
  text-align: center;
  background-color: #3498db;
  cursor: pointer;
}
</style>
