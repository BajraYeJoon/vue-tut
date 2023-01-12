<template>
  <!--  1. dynamic value // partial binding -->
  <h1>{{ greet }} {{ name }}</h1>

  <!--  2. text binding using directives -->
  <!-- v-text overrides the value inside the element // full binding-->
  <!-- <div v-text="channel"></div> -->

  <!--  3. binding html // vulnerable to xss -->
  <div v-html="channel"></div>

  <!-- 4 .binding attributes / cannot use {{  }} -->

  <h2 v-bind:id="headingId">Heading</h2>
  <button v-bind:disabled="isDisabled">Disabled Button</button>

  <!--  5. binding classes -->
  <h3 class="underline">Underlined text</h3>
  <h2 class="underline" v-bind:class="status">Danger Status</h2>

  <h3 v-bind:class="isPromote && 'promote'">Promoted</h3>

  <h3 v-bind:class="isSold ? 'sold' : 'new'">Sold Out (conditional render)</h3>

  <!-- 6. binding in arrays -->
  <h2 v-bind:class="['new', 'promote']">New Movie (array class attached )</h2>

  <h2 v-bind:class="[isPromote && 'promote', isSold ? 'sold' : 'new']">
    New Movie (Conditional + ternary) !SOLD
  </h2>

  <!-- 7. binding in objects -->
  <h2
    v-bind:class="{
      promote: isPromote,
      new: !isSold,
      sold: isSold,
    }"
  >
    Object Movies SOLD
  </h2>

  <!--  8. binding styles -->
  <h2
    v-bind:style="{
      color: highlightColor,
      'font-size': fSize + 'px',
      padding: '20px',
    }"
  >
    Inline style
  </h2>

  <h2 v-bind:style="headerStyleObject">Object Style</h2>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      name: "binaya",
      greet: "hello",
      channel: "<b>bajra</b>",
      headingId: "heading",
      isDisabled: true,
      status: "danger",
      isPromote: false,
      isSold: false,
      highlightColor: "orange",
      fSize: 40,
      headerStyleObject: {
        color: "blue",
        fontSize: "50px",
        padding: "30px",
      },
    };
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.underline {
  text-decoration: underline;
}

.promote {
  font-style: italic;
}

.new {
  color: green;
}

.sold {
  color: red;
}
</style>
