<template>
  <div class="options-container">
    <ul @click="validateOptions" v-if="!this.options">
      <li  class="uppercase" v-for="pokemon in pokemons" :key="pokemon.id" @click="$emit('selection', pokemon.id)">
        {{ pokemon.name }}
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  props: {
    pokemons: {
      type: Array,
      required: true,
    },
  },
  data() {
    return {
      options: false,
    };
  },
  methods: {
    validateOptions() {
      this.options = true;
    }

  },
  };
</script>

<style scoped>
/* Pokemon Options */
.uppercase{
  text-transform: capitalize;
}
ul {
  list-style-type: none;
}
li {
  background-color: white;
  border-radius: 5px;
  border: 1px solid rgba(0, 0, 0, 0.2);
  cursor: pointer;
  margin-top: 10px;
  margin-bottom: 15px;
  width: 250px;
  font-size: 20px;
  
}

li:hover {
  background-color: rgba(0, 0, 0, 0.05);
}

.options-container {
  display: flex;
  justify-content: center;
}
</style>