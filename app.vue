<template>
    <div id="app">
      <!-- 1. Template Syntax -->
      <h2>1. Template Syntax</h2>
      <!-- a. Text Interpolation -->
      <div>{{ message }}</div>
      <!-- b. Raw HTML [v-html] -->
      <div v-html="rawHTML"></div>
      <!-- c. Attribute Bindings [v-bind:id] -->
      <div :id="elementId">This div has a dynamic ID.</div>
      <!-- d. JavaScript expressions inside syntax i.e. {{ }} -->
      <div>{{ count * 2 }}</div>
  
      <!-- 2. Methods -->
      <h2>2. Methods</h2>
      <div>
        <button @click="increment">Increment</button>
        <p>{{ count }}</p>
      </div>
  
      <!-- 3. Reactivity Fundamentals [ref(), <script setup>] -->
      <h2>3. Reactivity Fundamentals</h2>
      <div>
        <p>Counter: {{ counter }}</p>
        <button @click="incrementCounter">Increment</button>
      </div>
  
      <!-- ... other sections ... -->
  
      <!-- 10. Components -->
      <h2>10. Components</h2>
      <CustomComponent :message="componentMessage" />
    </div>
  </template>
  
  <script>
  import { ref } from 'vue';
  import CustomComponent from './CustomComponent.vue';
  
  export default {
    components: {
      CustomComponent,
    },
    setup() {
      // 1. Template Syntax
      const message = ref('Hello, Vue!');
      const rawHTML = '<strong>Rendered as HTML</strong>';
      const elementId = 'dynamic-id';
      const count = ref(5);
  
      // 2. Methods
      const increment = () => {
        count.value++;
      };
  
      // 3. Reactivity Fundamentals
      const counter = ref(0);
      const incrementCounter = () => {
        counter.value++;
      };
  
      // 4. ... Define other data and methods here ...
  
      // 10. Components
      const componentMessage = 'Hello from the component!';
  
      return {
        // 1. Template Syntax
        message,
        rawHTML,
        elementId,
        count,
  
        // 2. Methods
        increment,
  
        // 3. Reactivity Fundamentals
        counter,
        incrementCounter,
  
        // 4. ... Return other data and methods ...
  
        // 10. Components
        componentMessage,
      };
    },
  };
  </script>
  