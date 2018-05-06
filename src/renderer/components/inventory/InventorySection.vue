<template>
  <v-container grid-list-md text-xs-center>
    <v-layout row v-for="(row, rowIndex) in items" :key="`row${rowIndex}`">
      <v-flex v-for="(item, itemIndex) in items[rowIndex]" :key="`item${rowIndex}-${itemIndex}`">
        <inventory-item
          :itemName="`${item.name}`"
          :pointValue="item.value">
        </inventory-item>
      </v-flex> 
    </v-layout>
  </v-container>
</template>

<script>
  import InventoryItem from './InventoryItem'

  export default {
    components: {InventoryItem},
    props: {
      /* should be a 2d array of objects with a name (which corresponds to an image filename,) and a point value. */
      items: {
        type: Array,
        required: true
      }
    },
    data () {
      return {
      }
    },
    computed: {
    },
    methods: {
    }
  }
</script>

<style scoped>

</style>
