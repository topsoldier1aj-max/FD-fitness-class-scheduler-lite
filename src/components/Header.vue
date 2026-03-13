<script setup>
defineProps({
  count:Number
})
</script>

<template>

<nav class="navbar bg-primary">

<div class="container text-white">

<h4 class="mb-0">
 FlexZone Fitness Scheduler
</h4>

<span class="badge bg-success fs-6">
Total Classes: {{count}}
</span>

</div>

</nav>

<div class="bg-light text-center py-4">

<h2>Manage Fitness Class Sessions</h2>

<p class="text-muted">
Add, view and manage upcoming gym classes
</p>

</div>

</template>