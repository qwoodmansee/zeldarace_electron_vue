<template>
  <div>
    <div class="inventory-image-container" @click="inventoryItemClicked">
      <img 
      :src="require(`@/assets/icons/${imageFileName}`)" 
      :class="{ collected: itemCollected }"
      class="inventory-item-image"/>
      <span class="weight-label">{{pointValue}}</span>
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
      isCollected: {
        type: Boolean,
        default: false
      }
    },
    data () {
      return {
        itemCollected: this.isCollected
      }
    },
    computed: {
      imageFileName () {
        return this.itemName + '.png'
      }
    },
    methods: {
      inventoryItemClicked () {
        // TODO(quinton): consider passing this changed value down from the parent in the handler for the event we
        // will eventually emit.
        this.itemCollected = !this.itemCollected
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

  .inventory-item-image { 
    opacity: .25;
  }

  /* Bottom left text */
  .weight-label {
      font-size: 1em;
      opacity: 1;
      margin-left: -.75em;
  }

  .collected {
    opacity: 1;
  }

</style>
