<template>
  <div>
    <input @input="onInput" />
  </div>
</template>

<script>
export default {
  name: "SearchBar",
  methods: {
    onInput(e) {
      this.$emit("newSearch", e.target.value);
    }
  }
}
</script>

<style scoped>
input {
  width: 100%;
}
div {
  text-align: center;
  margin: 30px 0px 30px;
}
</style>