<template>
  <div>
    <h1>Ma liste de tâches</h1>
    <input type="text" v-model="newTask" @keyup.enter="addTask">
    <button @click="addTask">Ajouter</button>
    <ul>
      <li v-for="task in tasks" :key="task">{{ task }}</li>
    </ul>
  </div>
</template>

<script>
export default {
  data() {
    return {
      tasks: ['Tâche 1', 'Tâche 2', 'Tâche 3'],
      newTask: '',
    };
  },
  methods: {
    addTask() {
      if (this.newTask.trim() !== '') {
        this.tasks.push(this.newTask);
        this.newTask = '';
      }
    },
  },
};
</script>
