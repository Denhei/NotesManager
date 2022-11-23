<template>
  <b-container id="TLheaderContainer">
    <b-form>
      <b-row>
        <b-col cols="3">
          <b-form-group>
            <b-form-input
              id="taskName"
              placeholder="Informe o título da tarefa"
              v-model="newTask.title"
              required
            ></b-form-input>
          </b-form-group>
        </b-col>
        <b-col cols="3">
          <b-form-group>
            <b-form-input
              id="taskDescription"
              placeholder="Informe a descrição da tarefa"
              v-model="newTask.description"
              required
            ></b-form-input>
          </b-form-group>
        </b-col>
        <!-- <b-col style="display:flex; align-items:center;" cols="3">
          <b-form-group>
            <b-form-checkbox-group style="display:flex; align-items:center;">
              <b-form-radio
                class="taskStatusBox"
                name="taskStatus"
                value="complete"
                v-model="newTask.completed"
              >Complete</b-form-radio>
              <b-form-radio
                class="taskStatusBox"
                name="taskStatus"
                value="notcomplete"
                v-model="newTask.completed"
              >Not Complete</b-form-radio>
            </b-form-checkbox-group>
          </b-form-group>
        </b-col>-->
        <b-col
          cols="3"
          style="
    justify-content: space-around;
    display: flex;
    align-items: center;
"
        >
          <!-- <b-form-group style="display:flex; justify-content:space-between;">-->
          <b-button variant="success" @click="addNewTask()">Adicionar Tarefa</b-button>
          <b-button variant="warning" @click="limparCampos()">Limpar Campos</b-button>
          <!-- </b-form-group>-->
        </b-col>
      </b-row>
    </b-form>
  </b-container>
</template>

<script>
export default {
  name: "TLheader",
  data() {
    return {
      newTask: {
        title: "",
        description: ""
        // completed: false
      }
    };
  },
  methods: {
    addNewTask() {
      this.$root.$emit("addNewTask", this.newTask);
      this.limparCampos();
    },
    limparCampos() {
      this.newTask.title = "";
      this.newTask.description = "";
    }
  }
};
</script>

<style>
#TLheaderContainer {
  margin: 50px auto;
}

.taskStatusBox {
  margin: 10px;
}
</style>