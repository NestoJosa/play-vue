<template>
  <StatusColumn
    title="To Do"
    :cardsList="todoCards"
    @update:cardsList="updateTodoCards"
  />
  <StatusColumn
    title="Doing"
    :cardsList="doingCards"
    @update:cardsList="updateDoingCards"
  />
  <StatusColumn
    title="Done"
    :cardsList="doneCards"
    @update:cardsList="updateDoneCards"
  />
</template>

<script>
import StatusColumn from './components/StatusColumn.vue';

export default {
  name: 'App',
  components: {
    StatusColumn
  },
  data() {
    return {
      todoCards: [
        {id: 1, title: 'Task Card One', description: 'Aenean commodo ligula eget dolor. Aenean massa. Cum sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus.'},
        {id: 2, title: 'Task Card Two', description: 'Donec quam felis, ultricies nec, pellentesque eu, pretium quis, sem. Nulla consequat massa quis enim.'},
      ],
      doingCards: [
        {id: 3, title: 'Task Card Three', description: 'Donec pede justo, fringilla vel, aliquet nec, vulputate eget, arcu. In enim justo, rhoncus ut, imperdiet a, venenatis vitae, justo.'},
      ],
      doneCards: [
        {id: 4, title: 'Task Card Four', description: 'Nullam dictum felis eu pede mollis pretium. Integer tincidunt. Cras dapibus.'},
      ]
    }
  },
  methods: {
    updateTodoCards(newCards) {
      this.todoCards = newCards;
    },
    updateDoingCards(newCards) {
      this.doingCards = newCards;
    },
    updateDoneCards(newCards) {
      this.doneCards = newCards;
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  display: flex;
  justify-content: space-around;
}
</style>
