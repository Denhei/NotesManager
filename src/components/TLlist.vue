<template>
  <b-container fluid>
    <b-row>
      <b-col class="task" v-for="(task,index) in tasks" :key="task.id" cols="2">
        <b-card :title="task.title" :img-src="task.imgUrl">
          <b-card-text>{{task.description}}</b-card-text>
          <!-- <b-row>
            <b-form-radio
              class="taskStatusBox"
              name="taskStatus"
              v-model="task.completed"
              value="complete"
            >Complete</b-form-radio>
            <b-form-radio
              class="taskStatusBox"
              name="taskStatus"
              v-model="task.completed"
              value="notcomplete"
            >Not Complete</b-form-radio>
          </b-row>-->
          <b-button href="#" variant="danger" @click="remove(index)">Excluir</b-button>
        </b-card>
      </b-col>
    </b-row>
  </b-container>
</template>

<script>
export default {
  name: "TLlist",
  mounted() {
    this.$root.$on("addNewTask", taskReceived => {
      let taskCreated = {
        title: taskReceived.title,
        description: taskReceived.description
        // completed: taskReceived.completed
      };

      this.tasks.push(taskCreated);
    });
  },
  data() {
    return {
      methods: {
        addNewTask() {}
      },
      tasks: [],
      themeConfig: {
        backgroundColor: "orange",
        color: "white"
      }
    };
  },
  methods: {
    remove(taskIndex) {
      this.tasks.splice(taskIndex, 1);
    }
  }
};
</script>

<style>
.task {
  margin: 10px 0;
  padding: 5px;
}
</style>