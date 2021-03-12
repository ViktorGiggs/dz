<template>
  <div>
    <div
        v-for="(item, key) in subjects"
        :key="key"
    >
      <div
          v-if="item.type === type"
      >
        {{ item.name }}
      </div>
    </div>
    <input
        class="myText"
        type="text"
    />
  </div>
</template>

<script>
export default {
  props: ['subjects'],
  data() {
    return {
      type: '',
    }
  },
  created() {
    console.log(this.subjects);
    console.log(this.$route);
    this.type = this.$route.query.type
  }
}
</script>

<style scoped>
.myText {
  border: 1px solid black;
  border-radius: 10px;
}
</style>