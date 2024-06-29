<script setup lang="ts">
import { computed } from 'vue'
import { useStore } from 'vuex'

// Define props
defineProps<{ msg: string }>()

// Get the Vuex store
const store = useStore()

// Create a computed property to access the Vuex state
const count = computed(() => store.state.count)

// Method to commit the increment mutation
const increment = () => {
  store.commit('increment')
}

</script>

<template>
  <h1>{{ msg }}</h1>

  <div class="card">
    <button type="button" @click="increment">count is {{ count }}</button>
    <p>
      Edit
      <code>components/HelloWorld.vue</code> to test HMR
    </p>
  </div>
</template>

<style scoped>
.read-the-docs {
  color: #888;
}
</style>
