<template>
  <div class="row grade-row">
    <div class="col-6">
      <input v-model="score" v-on:input="updateWeight()" type="text" class="form-control" placeholder="Score">
    </div>
    <div class="col-6">
      <input v-model="grade" v-on:input="updateWeight()" type="text" class="form-control" placeholder="Weight">
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      grade:0,
      score: 0,
      weightScore: 0
    }
  },
  methods: {
    updateWeight() {
      this.weightScore = (this.grade / 100) * this.score;
      const value = isNaN(this.weightScore) ? 0 : this.weightScore;
      this.$emit("weight-up", value);
    }
  }
}
</script>

<style scoped>

</style>
