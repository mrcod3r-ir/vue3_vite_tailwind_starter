<template>
    <h1 class="mb-6 text-3xl font-extrabold">Home</h1>
    <p class="mb-6">Name in store is : {{ name }}</p>
    <input type="text" class="p-2 mr-4 border border-gray-600 rounded" />
    <button class="p-2 text-white bg-indigo-600 rounded" @click="saveName">
        Submit
    </button>
</template>
<script setup>
import { computed, ref } from 'vue'
import { useStore } from 'vuex'
const store = useStore()
const name = computed(() => {
    return store.state.user.name
})
const newName = ref('')
function saveName() {
    store.dispatch('saveName', newName.value)
}
</script>
