<template>
  <!-- <GreetVue name="John" place="np" />
  <GreetVue name="Doe" place="uk" />
  <GreetVue :name="name" :place="place" /> -->
  <hr />
  <!-- <ArticleComp id="my-article" :likes="50" :isPublished="true" /> -->

  <!-- Component Provide and Inject -->
  <!-- <h2>Provider {{ name }}</h2> -->
  <!-- <CompC /> -->

  <!-- Components Events -->
  <!-- <button @click="showPop = true">Show pop up</button> -->

  <!-- closePop from child -> parent -->
  <!-- <PopUp v-show="showPop" @close="closePop" /> -->

  <!-- Components with v-model -->
  <InputELement v-model="name" />
</template>

<script>
// import ArticleComp from "./components/Article.vue";
// import CompC from "./components/CompC.vue";
import InputELement from "./components/Input.vue";
// import PopUp from "./components/Popup.vue";

// import GreetVue from "./components/Greet.vue";

export default {
  name: "MainVue",
  components: {
    // GreetVue,
    // ArticleComp,
    // CompC,
    // PopUp,
    InputELement,
  },
  data() {
    return {
      name: "JOhn",
      place: "us",
      showPop: false,
    };
  },
  provide() {
    return {
      name: this.name,
    };
  },

  methods: {
    closePop(name) {
      this.showPop = false;
      console.log(name);
    },
  },
};
</script>

<style></style>
