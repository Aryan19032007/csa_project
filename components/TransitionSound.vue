<script setup>
import { watch, onMounted } from 'vue'
import { useNav } from '@slidev/client'

const props = defineProps({
  page: { type: Number, required: true },
  src: { type: String, required: true }
})

let audio = null

onMounted(() => {
  audio = new Audio(props.src)
  const nav = useNav()

  watch(
    () => nav.currentPage.value,
    (current) => {
      if (current === props.page && audio) {
        audio.currentTime = 0
        audio.play().catch(() => {})
      }
    }
  )
})
</script>

<template>
  <span style="display:none" aria-hidden="true"></span>
</template>
