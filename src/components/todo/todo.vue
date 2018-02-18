<template>
  <div class="todo-wrapper">
    <div>
      <todo-header>All</todo-header>
      <todo-list>
        <todo-list-item v-for="(task, index) in tasks" :key="index">
          {{ task.description }}
        </todo-list-item>
      </todo-list>
    </div>
    <div>
      <todo-header>Incomplete</todo-header>
      <todo-list>
        <todo-list-item v-for="(task, index) in incompleteTasks" :key="index">
          {{ task.description }}
          <todo-button @completeTask="task.completed = true">x</todo-button>
        </todo-list-item>
      </todo-list>
    </div>
    <div>
      <todo-header>Completed</todo-header>
      <todo-list>
        <todo-list-item v-for="(task, index) in completedTasks" :key="index">
          {{ task.description }}
        </todo-list-item>
      </todo-list>
    </div>
  </div>
</template>

<script>
import TodoHeader from './todo-header';
import TodoList from './todo-list';
import TodoListItem from './todo-list-item';
import TodoButton from './todo-button';

export default {
  components: {
    TodoHeader,
    TodoList,
    TodoListItem,
    TodoButton,
  },
  data() {
    return {
      tasks: [
        {
          description: 'Go to Costo',
          completed: false,
        },
        {
          description: 'Go to Aldi',
          completed: false,
        },
        {
          description: 'Fold Clothes',
          completed: true,
        },
        {
          description: 'Do Dishes',
          completed: false,
        },
        {
          description: 'Empty Dishwasher',
          completed: true,
        },
        {
          description: 'Feed Cats',
          completed: false,
        },
        {
          description: 'Feed baby',
          completed: false,
        },
        {
          description: 'Put baby to bed',
          completed: false,
        },
      ],
    };
  },
  computed: {
    incompleteTasks() {
      return this.tasks.filter(task => !task.completed);
    },
    completedTasks() {
      return this.tasks.filter(task => task.completed);
    },
  },
};
</script>

<style scoped>
.todo-wrapper {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  padding: 10px;
}
</style>
