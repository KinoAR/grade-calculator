<template>
  <div>
    <h2> Grade Calculator </h2>
    <div class="row justify-content-center">
      <form>
        <div class="row grade-row">
          <div class="col-6">
            <label for="formScoreInput"> Score </label>
            <input v-model="score" v-on:input="onScoreUp" type="text" class="form-control" placeholder="Score">
          </div>
          <div class="col-6">
            <label for="formWeightInput"> Weight </label>
            <input v-model="grade" v-on:input="onScoreUp" type="text" class="form-control" placeholder="Weight">
          </div>
        </div>
        <GradeRow v-on:weight-up="onScoreUp"/>
        <GradeRow v-on:weight-up="onScoreUp"/>
      </form>
    </div>
    <div class="row grade-area justify-content-center">
        <h2> Total Grade: {{totalGrade}}</h2>
      </div>
  </div>
</template>

<script>
import GradeRow from "./GradeRow";
export default {
  components: {
    GradeRow
  },
  data() {
    return {
      grade: 0,
      score: 0,
      totalGrade: 0,
    }
  },
  methods: {
    updateGrade(el) {

    },
    onScoreUp(value) {
      this.totalGrade = this.$children.reduce((prev, curr) => {
        console.log(prev.weightScore + curr.weightScore);
        return prev.weightScore + curr.weightScore;
      }) + ((this.grade / 100) * this.score);
    }
  }
}
</script>


<style scoped>
.grade-area {
  margin-top: 15px;
}
</style>
