<script setup>
defineProps({
  link: {
    type: Boolean,
    required: false,
    default: false
  },
  to: {
    type: String,
    required: false,
    default: "/"
  },
  mode: {
    type: String,
    required: false,
    default: null
  },
  type: {
    type: String,
    required: false,
    default: "submit"
  }
});
</script>


<template>
  <div class="button">
    <router-link v-if="link" :to="to" :class="mode">
      <slot></slot>
    </router-link>
    <button v-else :type="type" :class="mode">
      <slot></slot>
    </button>
  </div>
</template>


<style scoped>
button,
a {
  text-decoration: none;
  padding: 0.75rem 1.5rem;
  font: inherit;
  background-color: #3a0061;
  border: 1px solid #3a0061;
  color: white;
  cursor: pointer;
  border-radius: 30px;
  margin-right: 0.5rem;
  display: inline-block;
}

a:hover,
a:active,
button:hover,
button:active {
  background-color: #270041;
  border-color: #270041;
}

.flat {
  background-color: transparent;
  color: #3a0061;
  border: none;
}

.outline {
  background-color: transparent;
  border-color: #270041;
  color: #270041;
}

.flat:hover,
.flat:active,
.outline:hover,
.outline:active {
  background-color: #edd2ff;
}
</style>