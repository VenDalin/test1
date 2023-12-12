<script setup></script>

<template>
  <section>
    <h1>Assignment Undone({{ assignment.filter((a) => !a.completed).length }})</h1>
    <ul>
      <li v-for="ret in assignment.filter((a) => !a.completed)" :key="ret.id">
        {{ ret.name }} <input type="checkbox" v-model="ret.completed" />
      </li>
    </ul>
  </section>

  <section>
    <h1>Assignment Done({{ assignment.filter((a) => a.completed).length }})</h1>
    <ul>
      <li v-for="ret in assignment.filter((a) => a.completed)" :key="ret.id">
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
};
</script>
