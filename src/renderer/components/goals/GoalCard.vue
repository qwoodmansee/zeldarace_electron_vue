<template>
  <v-card
  :class="{ completed: goalCompleted, preselected: preselected }"
  class="goal-card no-select" 
  @click.native="goalCardClicked">
    <v-card-title primary-title>
      <div class="headline">{{goalName}}</div>
    </v-card-title>
  </v-card>    
</template>

<script>
  export default {
    props: {
      goalName: {
        type: String,
        required: true
      },
      isCompleted: {
        type: Boolean,
        default: false
      },
      preselected: {
        type: Boolean,
        default: false
      }
    },
    data () {
      return {
        goalCompleted: this.isCompleted
      }
    },
    computed: {
    },
    methods: {
      goalCardClicked () {
        this.goalCompleted = !this.goalCompleted
      }
    }
  }
</script>

<style scoped>
  .goal-card {
    height: 20vh;
    font-size: .9em;
    cursor: pointer;
    background-color: #3f51b5;
    color: white;
  }
  .preselected {
    background-color: #ec407a;
  }
  .completed {
    background-color: #4caf50;
  }
  /*prevents the highlighting of text when clicking over and over again */
  .no-select {
    -webkit-touch-callout: none;
    -webkit-user-select: none;
    -khtml-user-select: none;
    -moz-user-select: none;
    -ms-user-select: none;
    user-select: none;
}
</style>
