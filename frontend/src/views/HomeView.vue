<template>
  <main>
  <div id="carouselExampleIndicators" class="carousel slide" data-ride="carousel">
    <ol class="carousel-indicators">
      <li data-target="#carouselExampleIndicators" data-slide-to="0" class="active"></li>
      <li data-target="#carouselExampleIndicators" data-slide-to="1"></li>
      <li data-target="#carouselExampleIndicators" data-slide-to="2"></li>
    </ol>
    <div class="carousel-inner">
      <div class="carousel-item active">
        <img class="d-block w-100 img-cover" src="@/assets/images/banner4.jpg" alt="First slide" style="max-height: 500px;">
      </div>
      <div class="carousel-item">
        <img class="d-block w-100 img-cover" src="@/assets/images/banner2.jpg" alt="Second slide" style="max-height: 500px;">
      </div>
      <div class="carousel-item">
        <img class="d-block w-100 img-cover" src="@/assets/images/banner3.jpg" alt="Third slide" style="max-height: 500px;">
      </div>
    </div>
    <a class="carousel-control-prev" href="#carouselExampleIndicators" role="button" data-slide="prev">
      <span class="carousel-control-prev-icon" aria-hidden="true"></span>
    </a>
    <a class="carousel-control-next" href="#carouselExampleIndicators" role="button" data-slide="next">
      <span class="carousel-control-next-icon" aria-hidden="true"></span>
    </a>
  </div>
  <div class="container mt-4">
    <div class="row">
      <div class="col-12 text-center">
        <h1>Présentation de Ma Boutique d'Épices</h1>
      </div>
    </div>
    <div class="row mt-4">
      <div class="col-md-8 offset-md-2">
        <p class="lead text-center">Nous sommes une boutique spécialisée dans la vente d'épices de qualité pour sublimer vos plats.</p>
        <p>Nous offrons une large sélection d'épices du monde entier, allant des épices les plus courantes aux épices les plus rares.</p>
        <p>Nos épices sont soigneusement sélectionnées et emballées à la main pour garantir leur fraîcheur et leur qualité.</p>
        <p class="text-center"><router-link class="btn btn-info" to="/produits">Découvrez nos produits</router-link></p>
      </div>
    </div>
  </div>

  </main>
</template>
