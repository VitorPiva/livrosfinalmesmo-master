<script>
import { v4 as uuid} from "uuid";
export default {
  data() {
    return {
      novo_jogador: "",
      novo_time: "",
      novo_categoria: "",
      novo_editora: "",
      novo_quantidade:"",
      novo_preço:"",
      jogadores: [
        { id: "9a7c7c02-874d-4556-8a13-4a33c56571d1", name: "Los Frutinhas", nome: "9781234567897", nime: "163", nome2:"1562", nome3:"20", nome4:"50,90"},
        { id: "475f6d39-5a56-4442-8a2d-5ceba6b4b807", name: "As Crônicas de Nârnia", nome: "1462648219568", nime: "156", nome2:"6271", nome3:"15", nome4:"99,80"},
        { id: "874b37b6-3546-4c05-bc54-5d0fdb886d16", name: "Diário de um banana", nome: "3428591641356", nime: "98", nome2:"0156", nome3:"90", nome4:"20,50"},
        { id: "9b35ce67-a4ec-45a0-be67-1983e37bd723", name: "A arte da guerra", nome: "4541022161621", nime: "813", nome2:"7192", nome3:"69", nome4:"60,90"},
      ],
    };
  },
  methods: {
    salvar() {
      if (this.novo_jogador !== ""){
      const novo_id=uuid();
      this.jogadores.push({
        id: novo_id,
        name: this.novo_jogador,
        nome: this.novo_time,
        nime: this.novo_categoria,
        nome2: this.novo_editora,
        nome3: this.novo_quantidade,
        nome4: this.novo_preço

      });
        this.novo_jogador = "";
        this.novo_time = "";
        this.novo_categoria = "";
        this.novo_editora = "";
        this.novo_quantidade = "";
        this.novo_preço = "";
      }
    },
    excluir(jogador){
      const indice = this.jogadores.indexOf(jogador);
      this.jogadores.splice(indice, 1);
    },
  },
};
</script>
<template>
  <div class="container">
    <div class="title">
      <h2>Livros</h2>
    </div>
    <div class="form-input">
      <input type="text" placeholder="Editora" v-model="novo_jogador" @keypress.enter="salvar" />
      <input type="text" placeholder="ISBN" v-model="novo_time" @keypress.enter="salvar" />
      <input type="text" placeholder="CategoriaID" v-model="novo_categoria" @keypress.enter="salvar" />
      <input type="text" placeholder="EditoraID" v-model="novo_editora" @keypress.enter="salvar" />
      <input type="text" placeholder="Quantidade" v-model="novo_quantidade" @keypress.enter="salvar" />
      <input type="text" placeholder="Preço" v-model="novo_preço" @keypress.enter="salvar" />
      <button @click="salvar">Salvar</button>
    </div>
    <div class="list-items">
      <table>
        <thead>
          <tr>
            <th>ID</th>
            <th>Editora</th>
            <th>ISBN</th>
            <th>Categoria ID</th>
            <th>Editora ID</th>
            <th>Quantidade</th>
            <th>preço</th>
            <th>Ação</th>
          </tr>
        </thead>
        <tbody>
          <tr v-for="jogador in jogadores" :key="jogador.id">
            <td>{{jogador.id}}</td>
            <td>{{jogador.name}}</td>
            <td>{{jogador.nome}}</td>
            <td>{{jogador.nime}}</td>
            <td>{{jogador.nome2}}</td>
            <td>{{jogador.nome3}}</td>
            <td>{{jogador.nome4}}</td>
            <td>
              <button>Editar</button>
              <button @click="excluir(jogador)">Excluir</button>
            </td>
          </tr>
        </tbody>
      </table>
    </div>
  </div>
</template>
<style></style>