<script setup lang="ts">
import {ref} from "vue";

const flights = ref<any[]>([])

</script>

<template>
  <pre>{{ flights }}</pre>
</template>