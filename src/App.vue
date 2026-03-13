<script setup>
import { ref, computed } from 'vue'
import Header from './components/Header.vue'
import AddSessionForm from './components/AddSessionForm.vue'
import SessionList from './components/SessionList.vue'

const sessions = ref([])

function addSession(newSession){
  sessions.value.push({
    ...newSession,
    id: Date.now()
  })
}

function deleteSession(id){
  sessions.value = sessions.value.filter(s => s.id !== id)
}

const totalSessions = computed(()=>{
  return sessions.value.length
})
</script>

<template>

<Header :count="totalSessions" />

<div class="container mt-4">

<AddSessionForm
@add-session="addSession"
/>

<SessionList
:sessions="sessions"
@delete-session="deleteSession"
/>

</div>

</template>