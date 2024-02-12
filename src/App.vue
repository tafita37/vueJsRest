<template>
  <HelloWorld @update-name="name => display(name)"/>
  
  <span>
    
  </span>

  <!-- <div :class="[user.age>30? 'text-red' : 'text-green']">
    {{ user.name }}
  </div> -->

  <!-- <div v-if="user.age>15">
    Mon age : 
  </div>

  <div v-else>
    Vous n'avez pas l'age requis
  </div> -->

  <!-- <input type="text" v-model="name" @input="display">
  <input type="text" v-model="user.age" @input="display"> -->
</template>
<script setup>
  import HelloWorld from './components/HelloWorld.vue';
  import { computed, reactive, ref, watch } from 'vue';

  const sentence = computed(() => {
    return `Bonjour je m'appelle ${user.name} j'ai ${user.age}`;
  })
  const user = reactive({
    name : "NordCoders",
    age : 30
  });

  const name=ref("Nordcoders");

  watch(name, (newValue, oldValue) => {
    console.log(newValue, oldValue);
  })

  const display = (name) => {
    console.log('App.vue : ', name);
  }

</script>

<style scoped>
  .text-red {
    color: indianred;
  }

  .text-green {
    color: green;
  }
</style>
