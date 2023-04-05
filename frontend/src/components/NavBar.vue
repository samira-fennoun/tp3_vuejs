<template>
  <nav class="navbar navbar-expand-lg navbar-light bg-light">
    <a class="navbar-brand" href="#">Epices</a>
    <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarSupportedContent" aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
      <span class="navbar-toggler-icon"></span>
    </button>

    <div class="collapse navbar-collapse" id="navbarSupportedContent">
      <ul class="navbar-nav mr-auto">
        <li class="nav-item active">
            <router-link class="nav-link" to="/">Accueil </router-link>
        </li>
        <li class="nav-item">
           <router-link class="nav-link" to="/produits">Produits</router-link>
        </li>
        <li class="nav-item">
           <router-link class="nav-link" to="/new-product">Nouveau produit</router-link>
        </li>
      </ul>
    </div>
  </nav>
</template>
