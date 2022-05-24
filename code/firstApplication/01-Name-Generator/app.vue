<script setup lang="ts">
import {Length, Gender, Popularity} from "@/data"
// TS-Classes for the user-choise
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

const options = reactive<OptionsState>({
  gender: Gender.GIRL,
  popularity: Popularity.TRENDY,
  length: Length.ALL
});


//Computing the Result Name 

const name = ref<string[]>([])


</script>


<!-- Visual Content -->
<template>

<!-- Main Box for the user choise -->
  <div class="container">
    <h1>Name Generator</h1>
    <p>Find a Name</p>

    <div class="option-container-field">
<!-- SEX -->
      <div class="option-container1">
        <h4>1) Choose a gender</h4>
        <div class="option-button-field"></div>
        <div class="option-button">
          <button class="option option-left"
          :class="options.gender === Gender.BOY && 'option-active'"
          @click="options.gender = Gender.BOY"
          >Boy</button>
          <button 
            class="option option-middle"
            :class="options.gender === Gender.GIRL && 'option-active'"
            @click="options.gender = Gender.GIRL"
          >
          Girl
          </button>
          <button class="option option-right"
          :class="options.gender === Gender.UNISEX && 'option-active'"
          @click="options.gender = Gender.UNISEX"
          >Unisex</button>
        </div>
      </div>

<!-- Popularity -->
      <div class="option-container1">
        <h4>2) Choose the name's popularity</h4>
        <div class="option-button-field"></div>
        <div class="option-buttons">
          <button class="option option-left"
          :class="options.popularity === Popularity.TRENDY && 'option-active'"
          @click="options.popularity = Popularity.TRENDY"
          >Trendy</button>
          <button class="option option-right"
          :class="options.popularity === Popularity.UNIQUE && 'option-active'"
          @click="options.popularity = Popularity.UNIQUE"
          >Unique</button>
        </div>
      </div>
      
<!-- Length -->
      <div class="option-container1">
        <h4>3) Choose the names length </h4>
        <div class="option-button-field"></div>
        <div class="option-buttons">
          <button class="option option-left"
          :class="options.length === Length.LONG && 'option-active'"
          @click="options.length = Length.LONG"
          >Long</button>
          <button class="option option-middle"
          :class="options.length === Length.ALL && 'option-active'"
           @click="options.length = Length.ALL"
          >All</button>
          <button class="option option-right"
          :class="options.length === Length.SHORT && 'option-active'"
           @click="options.length = Length.SHORT"
          >Short</button>
        </div>
      </div>

<!-- Box for Output based on the user decission -->
      <div class="option-container1">
        <h4>Result </h4>
        <div class="option-button-field"></div>
        <div class="option-buttons">
          <button class="option option-result">
            Result

          </button>
        </div>
      </div>

    </div>
  </div>
</template>

<!-- STYLE -->
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

.option-result {
  border-radius: 1rem 1rem 1rem 1rem;
  background-color: rgb(249,87,89);
  color: white;
  border-radius: 6.5rem;
  font-size: 1rem;
  padding: 0.75rem 4rem;
  margin-top: 1rem;
  cursor: pointer;
}

.option-active {   
  background: rgb(161, 142, 142);
}

</style>

