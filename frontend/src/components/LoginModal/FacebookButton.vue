<template>
  <button class="facebook" @click.prevent="onSigninFacebook">
    <span>
      <font-awesome-icon :icon="facebookIcon" size="2x"/>
    </span>
    <span>페이스북으로 로그인</span>
    <span></span>
  </button>
</template>

<script>
import { FontAwesomeIcon } from "@fortawesome/vue-fontawesome";
import { faFacebook } from "@fortawesome/free-brands-svg-icons";
import firebase from "firebase/app";

export default {
  name: "FacebookButton",
  methods: {
    onSigninFacebook() {
      this.$store.dispatch("signUserInFacebook");
    }
  },
  computed: {
    facebookIcon() {
      return faFacebook;
    }
  },
  components: {
    FontAwesomeIcon
  }
};
</script>

<style>
.facebook {
  all: unset;
  display: flex;
  justify-content: space-around;
  align-items: center;
  background-color: #3b5998;
  height: 50px;
  color: white;
  font-weight: bold;
  border-radius: 5px;
  cursor: pointer;
}
</style>

