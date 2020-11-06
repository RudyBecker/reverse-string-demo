<template>
  <div id="app">
    <h1 class="my-2">Reverse String Three Ways</h1>
    <div>
      <b-form-input
        v-model="inputWord"
        placeholder="Enter your word to reverse"
        class="w-50 mx-auto my-5"
      ></b-form-input>
      <div>
        <b-button v-b-toggle.collapse-1 class="m-1"
          >Reverse a String With Built-In Functions</b-button
        >
        <b-collapse id="collapse-1" class="w-50 mx-auto">
          <b-card>{{ reverseBuiltIn(inputWord) }}</b-card>
        </b-collapse>
      </div>
      <div>
        <b-button v-b-toggle.collapse-2 class="m-1"
          >Reverse a String With a Decrementing For Loop</b-button
        >
        <b-collapse id="collapse-2" class="w-50 mx-auto">
          <b-card>{{ reverseDecrementLoop(inputWord) }}</b-card>
        </b-collapse>
      </div>
      <div>
        <b-button v-b-toggle.collapse-3 class="m-1"
          >Reverse a String With Recursion</b-button
        >
        <b-collapse id="collapse-3" class="w-50 mx-auto">
          <b-card>{{ reverseRecursion(inputWord) }}</b-card>
        </b-collapse>
      </div>

      <h5 class="my-5">Coded by Rudy Becker for Delivery Hero</h5>
    </div>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      inputWord: "",
    };
  },
  methods: {
    reverseBuiltIn: function(word) {
      return word
        .split("")
        .reverse()
        .join("");
    },
    reverseDecrementLoop: function(str) {
      var newString = "";
      for (var i = str.length - 1; i >= 0; i--) {
        newString += str[i];
      }
      return newString;
    },

    reverseRecursion: function reverseString(str) {
      if (str === "") return "";
      else return reverseString(str.substr(1)) + str.charAt(0);
    },
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
</style>
