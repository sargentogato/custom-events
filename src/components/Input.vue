<template>
  <input
    type="text"
    class="border"
    v-model="input"
    @keyup.enter="monitorEnterKey"
  />
</template>

<script>
export default {
  name: "Input",
  emits: ["add-note"],
  data() {
    return {
      input: "",
    }
  },
  methods: {
    monitorEnterKey() {
      //código
      this.$emit("add-note", {
        note: this.input,
        timeStamp: new Date().toLocaleString(),
      })

      this.input = ""
    },
  },
}
</script>
