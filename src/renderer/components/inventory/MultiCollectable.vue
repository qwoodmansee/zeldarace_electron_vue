<template>
  <div>
    <div class="inventory-image-container" @click="itemClicked" @contextmenu.prevent="itemRightClicked">
      <img 
      :src="require(`@/assets/icons/${imageFileName}`)" 
      class="inventory-item-image"/>
      <span class="weight-label">{{pointValue}}</span>
    </div>
    <div>
        <p>{{numCollected}}</p>
    </div>
  </div>
</template>

<script>
  export default {
    props: {
      itemName: {
        type: String,
        required: true
      },
      pointValue: {
        type: Number,
        required: true
      },
      startingNumber: {
        type: Number,
        default: 0
      }
    },
    data () {
      return {
        numCollected: this.startingNumber
      }
    },
    computed: {
      imageFileName () {
        return this.itemName + '.png'
      }
    },
    methods: {
      itemClicked () {
        // TODO(quinton): consider passing this changed value down from the parent in the handler for the event we
        // will eventually emit.
        this.numCollected += 1
      },
      itemRightClicked () {
        this.numCollected -= 1
      }
    }
  }
</script>

<style scoped>
  .inventory-image-container {
    position: relative;
    text-align: center;
    color: white;
  }
  /* Bottom left text */
  .weight-label {
      font-size: 1em;
      opacity: 1;
      margin-left: -.75em;
  }

</style>
