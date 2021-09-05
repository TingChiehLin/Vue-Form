<template>
  <div id="VModel">
    <input type="text" v-model.trim="inputValue" />
    <div>
      {{inputValue}}
    </div>
  </div>
</template>

<script>
export default {
  name: "VModel",
  data: () => {
    return {
      inputValue: ''
    }
  },
  methods: {
      setValue() {
        console.log(this.inputValue)
      }
  }

}
</script>

<style scoped>

</style>
