<script>
import { v4 as uuid} from "uuid";
export default {
  data() {
    return {
      novo_time: "",
      times: [
        { id: "f93ccdb8-f79e-11ec-b939-0242ac120002", name: "Nome 1" },
        { id: "016c4cf2-f79f-11ec-b939-0242ac120002", name: "Nome 2" },
        { id: "0a77ef18-f79f-11ec-b939-0242ac120002", name: "Nome 3" },
        { id: "12b621fe-f79f-11ec-b939-0242ac120002", name: "Nome 4" },
      ],
    };
  },
  methods: {
    salvar() {
      if (this.novo_time !== ""){
        const novo_id=uuid();
        this.times.push({
          id: novo_id,
          name: this.novo_time,
        });
        this.novo_time = "";
      }
    },
    excluir(time){
      const indice = this.times.indexOf(time);
      this.times.splice(indice, 1);
    },
  },
};
</script>
<template>
  <div class="container">
    <div class="title">
      <h2>Descrição dos Livros</h2>
    </div>
    <div class="form-input">
      <input type="text" v-model="novo_time" @keypress.enter="salvar" />
      <button @click="salvar">Salvar</button>
    </div>
    <div class="list-items">
      <table>
        <thead>
          <tr>
            <th>ID</th>
            <th>Nome</th>
            <th>Ação</th>
          </tr>
        </thead>
        <tbody>
          <tr v-for="time in times" :key="time.id">
            <td>{{ time.id }}</td>
            <td>{{ time.name }}</td>
            <td>
              <button>Editar</button>
              <button @click="excluir(time)">Excluir</button>
            </td>
          </tr>
        </tbody>
      </table>
    </div>
  </div>
</template>

<style></style>


