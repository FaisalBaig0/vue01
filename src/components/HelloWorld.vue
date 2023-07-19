<template>
  <!-- // for html -->
  <div class="hello">
    <h1 v-once>{{ name }}</h1>
    <h1>{{ name }}</h1>
    <h1>{{ value ? "Yes" : "No" }}</h1>
    <!-- //v-bind:disabled="disable"  -->
    <button v-on:click="update()">Click</button>
    <p v-html="htmlValue"></p>
    <h3>{{ message }}</h3>
    <h2>{{ getResult }}</h2>
    <h2>{{ getResultM() }}</h2>
  </div>
</template>

<script>
// import func from 'vue-editor-bridge';
export default {
  name: "HelloWorld",
  props: {
    message: String,
  },
  data() {
    // define state
    return {
      name: "Faisal",
      value: false,
      htmlValue: "<h1>Template In Vue js</h1>",
      disable: true,
      userName: "Sam",
      dollar: 300,
      pkr: 10,
      discount: 100,
    };
  },
  methods: {
    // function
    update() {
      this.name = "Baig";
    },
    getResultM() {
      return this.dollar * this.pkr - this.discount;
    },
  },
  computed: {
    // for complex store value/state in cache
    getResult() {
      return this.dollar * this.pkr - this.discount;
    },
  },
  beforeCreate() {
    console.log("Before Create");
  },
  beforeMount() {
    console.log("Before Mount");
  },
  created() {
    console.log("Created");
  },
  mounted() {
    console.log("Mounted");
  },
  unmounted() {
    console.log("Unmounted");
  },
  beforeUnmount() {
    console.log("Before Unmount");
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
.hello{
  background: #67d6a4;
}
</style>
