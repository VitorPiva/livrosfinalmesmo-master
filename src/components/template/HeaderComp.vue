<template>
  <header class="menu-superior">
    <div class="menu-esquerdo">
      <span> <RouterLink to="/">Autor</RouterLink> </span>
      <span>|</span>
      <span> <RouterLink to="/times">Categorias</RouterLink> </span>
      <span>|</span>
      <span> <RouterLink to="/jogadores">Editora</RouterLink> </span>
      <span>|</span>
      <span> <RouterLink to="/livros">Livros</RouterLink> </span>
    </div>
    <div class="menu-direto">
      <span>Sair</span>
    </div>
  </header>
</template>

<style>
header span {
  padding: 0 20px;
}

.menu-superior {
  justify-content: space-between;
}
</style>
