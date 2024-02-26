<template>
  <div>
    <div v-for="(command, index) in submittedCommands" :key="index">
      <Results v-if="command !== ''" :filterCommand="command" />
    </div>

    <div class="search-container">
      <div class="search-holder">
        <p>visitor@christosad.github.io/terminal:~$ </p>
        <input type="text" name="search" id="search" v-model="inputText" autocomplete="off" @keyup.enter="submit">
      </div>
    </div>
  </div>
</template>

<script>
import Results from './Results.vue';

window.onload = function() {
  document.getElementById("search").focus();
}

export default {
  data() {
    return {
      inputText: '',
      submittedCommands: [],
    };
  },
  methods: {
    submit() {

      if(this.inputText === 'clear') {

        this.submittedCommands.splice(0, this.submittedCommands.length);
        this.inputText = '';
        return;
      }

      if(this.inputText === 'email') {
        
        var email = "mailto:xristosad97@gmail.com";
        window.location.href = email;

        this.inputText = '';
        return;
      }

      this.submittedCommands.push(this.inputText);
      this.inputText = '';
    },
  },
  components: {
    Results,
  },
};
</script>
  

<style scoped>
 p {
    color: #8DA101;
 }

 .search-holder {
    display: flex;
 }

 input {
    outline: none;
    border: 0;
    background-color: transparent;
    min-width: unset;
    width: unset;
    color: #F85552;
    font-family: var(--terminal-font);
    font-weight: 400;
    font-size: 15px;
    padding-left: 10px;
 }

</style>