<template>
  <div id="wrapper">
    <main>
      <div class="left-side">
        <span class="title">
          In progress components:
        </span>

        <section>
          <h1>Inventory Item</h1>
          <br/>
          <inventory-item
            :itemName="'Bombchu'"
            :pointValue="2">
          </inventory-item>
          <inventory-item
            :itemName="'Bomb'"
            :pointValue="5">
          </inventory-item>
        </section>
        <br/>

        <section>
          <h1>MultiCollectable</h1>
          <br/>
          <multi-collectable
            :itemName="'HeartContainer'"
            :pointValue="1"
            :startingNumber="3">
          </multi-collectable>
        </section>
        <br/>

        <section>
          <h1>Goal Card</h1>
          <br/>
          <goal-card
            :goalName="'Goal #1 (Non-Preselected)'">
          </goal-card>
          <goal-card
            :goalName="'Goal #2 (Preselected)'"
            :preselected="true">
          </goal-card>
        </section>
        <br/>

        <section>
          <h1>Inventory Section</h1>
          <br/>
          <inventory-section
            :items="exampleInventorySection1">
          </inventory-section>
          <br/>
          <inventory-section
            :items="exampleInventorySection2">
          </inventory-section>
        </section>
      </div>
    </main>
  </div>
</template>

<script>
  import InventoryItem from './inventory/InventoryItem'
  import MultiCollectable from './inventory/MultiCollectable'
  import InventorySection from './inventory/InventorySection'
  import GoalCard from './goals/GoalCard'

  export default {
    name: 'landing-page',
    components: { InventoryItem, MultiCollectable, GoalCard, InventorySection },
    methods: {
      open (link) {
        this.$electron.shell.openExternal(link)
      }
    },
    computed: {
      exampleInventorySection1 () {
        return [
          [{'name': 'Bomb', 'value': 5}, {'name': 'Bomb', 'value': 5}, {'name': 'Bomb', 'value': 5}, {'name': 'Bomb', 'value': 5}, {'name': 'Bomb', 'value': 5}, {'name': 'Bomb', 'value': 5}],
          [{'name': 'Bomb', 'value': 5}, {'name': 'Bomb', 'value': 5}, {'name': 'Bomb', 'value': 5}, {'name': 'Bomb', 'value': 5}, {'name': 'Bomb', 'value': 5}, {'name': 'Bomb', 'value': 5}],
          [{'name': 'Bombchu', 'value': 5}, {'name': 'Bombchu', 'value': 5}, {'name': 'Bombchu', 'value': 5}, {'name': 'Bombchu', 'value': 5}, {'name': 'Bombchu', 'value': 5}, {'name': 'Bombchu', 'value': 5}],
          [{'name': 'Bombchu', 'value': 5}, {'name': 'Bombchu', 'value': 5}, {'name': 'Bombchu', 'value': 5}, {'name': 'Bombchu', 'value': 5}, {'name': 'Bombchu', 'value': 5}, {'name': 'Bombchu', 'value': 5}]
        ]
      },
      exampleInventorySection2 () {
        return [
          [{'name': 'Bomb', 'value': 5}, {'name': 'Bomb', 'value': 5}, {'name': 'Bomb', 'value': 5}, {'name': 'Bomb', 'value': 5}, {'name': 'Bomb', 'value': 5}],
          [{'name': 'Bomb', 'value': 5}, {'name': 'Bomb', 'value': 5}, {'name': 'Bomb', 'value': 5}, {'name': 'Bomb', 'value': 5}, {'name': 'Bomb', 'value': 5}],
          [{'name': 'Bombchu', 'value': 5}, {'name': 'Bombchu', 'value': 5}, {'name': 'Bombchu', 'value': 5}, {'name': 'Bombchu', 'value': 5}, {'name': 'Bombchu', 'value': 5}]
        ]
      }
    }
  }
</script>

<style>
  @import url('https://fonts.googleapis.com/css?family=Source+Sans+Pro');

  * {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
    color: white;
  }

  body { font-family: 'Source Sans Pro', sans-serif; }

  #wrapper {
    background: #424242;
    height: 100vh;
    padding: 60px 80px;
    width: 100vw;
  }

  main {
    display: flex;
    justify-content: space-between;
  }

  main > div { flex-basis: 50%; }

  .left-side {
    display: flex;
    flex-direction: column;
  }

  .title {
    color: white;
    font-size: 20px;
    font-weight: bold;
    margin-bottom: 6px;
  }

  .title.alt {
    font-size: 18px;
    margin-bottom: 10px;
  }

  .doc p {
    color: white;
    margin-bottom: 10px;
  }

</style>
