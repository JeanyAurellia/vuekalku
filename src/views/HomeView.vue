<template>
<div id="app">
<div id="calWrap">
    <div class="top">
        <input type="text" v-model="total" />
    </div>
    <div id="keys">
        <div v-on:click="key(7)">7</div>
        <div v-on:click="key(8)">8</div>
        <div v-on:click="key(9)">9</div>
        <div v-on:click="key('+')">+</div>
        <div v-on:click="key(4)">4</div>
        <div v-on:click="key(5)">5</div>
        <div v-on:click="key(6)">6</div>
        <div v-on:click="key('-')">-</div>
        <div v-on:click="key(1)">1</div>
        <div v-on:click="key(2)">2</div>
        <div v-on:click="key(3)">3</div>
        <div v-on:click="key('*')">*</div>
        <div v-on:click="key(0)">0</div>
        <div v-on:click="clear()" class="clear">c</div>
        <div v-on:click="equal()">=</div>
        <div v-on:click="key('/')">/</div>
    </div>
</div> 
</div> 
</template>

<script>
export default {
  data() {
    return {
      total: '',
    };
  },
  methods: {
    key(value) {
      this.total += value;
    },
    clear() {
      this.total = '';
    },
    equal() {
      try {
        this.total = eval(this.total);
      } catch (error) {
        this.total = 'Error';
      }
    },
  },
};
</script>
