<script setup></script>

<template>
  <section v-show = "unCompletedAssignments.length">
    <h1>Assignment Undone({{ unCompletedAssignments.length }})</h1>
    <ul>
      <li v-for="ret in unCompletedAssignments" :key="ret.id">
        {{ ret.name }} <input type="checkbox" v-model="ret.completed" />
      </li>
    </ul>
  </section>
  <br>
  <section v-if = "completedAssignments.length > 0">
    <h1>Assignment Done({{ completedAssignments.length }})</h1>
    <ul>
      <li v-for="ret in completedAssignments" :key="ret.id">
        {{ ret.name }}
        <input type="checkbox" v-model="ret.completed" />
      </li>
    </ul>
  </section>
</template>

<script>
export default {
  data() {
    return {
      assignment: [
        {id:1, name: "web application", completed: false },
        {id:2, name: "backend developer", completed: false},
        {id:3, name: "Marketing project", completed: false},
        {id:4, name: "Vue Project", completed: false},
      ],
    };
  },
  computed:{
    completedAssignments(){
      return this.assignment.filter((a) => a.completed);
    },
    unCompletedAssignments(){
      return this.assignment.filter((a) => !a.completed);
    },
  }
};
</script>
