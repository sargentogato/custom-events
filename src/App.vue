<template>
  <div class="flex-col">
    <div class="flex gap-4 justify-around">
      <h2>Notes</h2>
      <p v-for="note in notes" :key="note">
        {{ note }}
      </p>

      <h2>timeStamp</h2>
      <div v-for="timeStamp in timeStamps">{{ timeStamp }}</div>
    </div>

    <Input @add-note="addNote" />
  </div>
</template>

<script>
import Input from "./components/Input.vue"

export default {
  name: "App",
  components: { Input },
  data() {
    return {
      notes: [],
      timeStamps: [],
    }
  },
  methods: {
    addNote(event) {
      this.notes.push(event.note)
      this.timeStamps.push(event.timeStamp)
    },
  },
}
</script>
