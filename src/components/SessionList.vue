<script setup>

const props = defineProps({
sessions:Array
})

const emit = defineEmits(['delete-session'])

function remove(id){
emit('delete-session',id)
}

</script>

<template>

<div>

<div v-if="sessions.length === 0" class="text-center mt-5">

<h5 class="text-muted">
No sessions scheduled
</h5>

<p class="text-muted">
Use the form above to add a class
</p>

</div>

<div v-else class="row g-4">

<div
class="col-md-4"
v-for="session in sessions"
:key="session.id"
>

<div class="card shadow-sm rounded-4 h-100">

<div class="card-body">

<h5 class="card-title">
{{session.name}}
</h5>

<p class="mb-1">
Coach: <strong>{{session.coach}}</strong>
</p>

<p class="mb-1">
Date: {{session.date}}
</p>

<p class="mb-1">
Time: {{session.time}}
</p>

<p class="mb-3">
Capacity: {{session.capacity}}
</p>

<button
class="btn btn-outline-danger w-100"
@click="remove(session.id)"
>
Delete Session
</button>

</div>

</div>

</div>

</div>

</div>

</template>