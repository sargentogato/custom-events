<template>
  <div class="flex-col">
    <div class="flex gap-4 justify-around">
      <div>
        <h2 class="text-center">Notes</h2>
        <p v-for="note in notes" :key="note">
          {{ note }}
        </p>
      </div>
      <div>
        <h2 class="text-center">timeStamp</h2>
        <div v-for="timeStamp in timeStamps">{{ timeStamp }}</div>
      </div>
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
