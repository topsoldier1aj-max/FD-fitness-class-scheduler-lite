<script setup>
import { ref } from 'vue'

const emit = defineEmits(['add-session'])

const name = ref("")
const coach = ref("")
const date = ref("")
const time = ref("")
const capacity = ref("")
const error = ref("")

function submitForm(){

if(!name.value || !coach.value || !date.value || !time.value || !capacity.value){
error.value = "Please fill in all fields"
return
}

emit('add-session',{
name:name.value,
coach:coach.value,
date:date.value,
time:time.value,
capacity:capacity.value
})

name.value=""
coach.value=""
date.value=""
time.value=""
capacity.value=""
error.value=""
}
</script>

<template>

<div class="card shadow-sm mb-4 rounded-4">

<div class="card-body">

<h5 class="mb-3">Add New Session</h5>

<div v-if="error" class="alert alert-danger">
{{error}}
</div>

<div class="row g-3">

<div class="col-md-4">
<input v-model="name" class="form-control" placeholder="Class Name">
</div>

<div class="col-md-4">
<input v-model="coach" class="form-control" placeholder="Coach Name">
</div>

<div class="col-md-4">
<input v-model="capacity" type="number" class="form-control" placeholder="Capacity">
</div>

<div class="col-md-6">
<input v-model="date" type="date" class="form-control">
</div>

<div class="col-md-6">
<input v-model="time" type="time" class="form-control">
</div>

<div class="col-12">
<button class="btn btn-success w-100" @click="submitForm">
Add Session
</button>
</div>

</div>

</div>

</div>

</template>