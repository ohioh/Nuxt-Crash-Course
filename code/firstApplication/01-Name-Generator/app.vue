<script setup lang="ts">

enum Gender {
  GIRL = 'Girl',
  BOY = 'Boy',
  UNISEX = 'Unisex'
}

enum Popularity {
  TRENDY = 'Trendy',
  UNIQUE = 'Unique'
}

enum Length {
  LONG = 'Long',
  ALL = 'All',
  SHORT = 'Short'
}

interface OptionsState {
  gender: string;
  popularity: string;
  length: string;
}

const obj: OptionsState = {
  gender: Gender.GIRL,
  popularity: Popularity.TRENDY,
  length: Length.ALL
}

const options = reactive({
  gender: "Unisex",
  popularity: "Trendy",
  length: "Short",
});
</script>

<template>
  <div class="container">
    <h1>Name Generator</h1>
    <p>Find a Name</p>

    <div class="option-container-field">
      <div class="option-container1">
        <h4>1) Choose a gender</h4>
        <div class="option-button-field"></div>
        <div class="option-button">
          <button class="option option-left"
          :class="options.gender === 'Boy' && 'option-active'"
          >Boy</button>
          <button 
            class="option option-middle"
            :class="options.gender === 'Girl' && 'option-active'"
          >
          Girl
          </button>
          <button class="option option-right"
          :class="options.gender === 'Unisex' && 'option-active'"
          >Unisex</button>
        </div>
      </div>

      <div class="option-container1">
        <h4>2) Choose the name's popularity</h4>
        <div class="option-button-field"></div>
        <div class="option-buttons">
          <button class="option option-left"
          :class="options.popularity === 'Trendy' && 'option-active'"
          >Trendy</button>
          <button class="option option-right"
          :class="options.popularity === 'Unique' && 'option-active'"
          >Unique</button>
        </div>
      </div>

      <div class="option-container1">
        <h4>3) Choose the names length </h4>
        <div class="option-button-field"></div>
        <div class="option-buttons">
          <button class="option option-left"
          :class="options.length === 'Long' && 'option-active'"
          >Long</button>
          <button class="option option-middle"
          :class="options.length === 'All' && 'option-active'"
          >All</button>
          <button class="option option-right"
          :class="options.length === 'Short' && 'option-active'"
          >Short</button>
        </div>
      </div>

    </div>
  </div>
</template>

<style scoped>
.container {
  font-family: Arial, sans-serif;
  color: rgb(20, 60, 138);
  max-width: 50rem;
  margin: 0 auto;
  text-align: center;
}

.container h1 {
  font-size: 3rem;
}

.option-container-field {
  background-color: rgb(255, 238, 236);
  border-radius: 2rem;
  padding: 1rem;
  width: 95%;
  margin: 0 auto;
  margin-top: 4rem;
  position: relative;
}

.option-container1 {
  margin-bottom: 2rem;
}

.option {
  background: white;
  outline: 0.15rem solid rgb(233, 121, 123);
  border: none;
  padding: 0.75rem;
  width: 12rem;
  font-size: 1rem;
  color: rgb(27, 60, 138);
  cursor: pointer;
  border-radius: 0.25rem;
  font-weight: 200;
}

.option-left {
  border-radius: 1rem 0 0 1rem;
}

.option-middle {
  border-radius: 0 0 0 0;
}

.option-right {
  border-radius: 0 1rem 1rem 0;
}

.option-active {   
  background: rgb(161, 142, 142);
}
</style>

