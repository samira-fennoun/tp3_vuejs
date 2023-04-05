<template>
       <section class="section">
        <section class="overflow-hidden">
        <div class="container">
          <div class="row">
            <div class="col-12 col-md-6 offset-xl-1 order-md-2 section pt-md-0 pb-0">

              <!-- Button -->
              <a href="#modal-video" class="btn btn-lg btn-circle btn-hero ml-4 bg-white shadow text-body d-none d-md-block" data-toggle="modal">
                <i class="fas fa-play"></i>
              </a>

              <!-- Image -->
              <div class="img-half">
                <img src="@/assets/images/img_right.jpg" alt="..." class="img-cover img-incline-left">
              </div>

            </div>
            <div class="col-12 col-md-6 col-xl-5 order-md-1 section">

              <!-- Heading -->
              <h1 class="mb-4 animate" data-toggle="animation" data-animation="fadeUp" data-animation-order="1" data-animation-trigger="load">
                Achetez en toute confiance
              </h1>

              <!-- Subheading -->
              <p class="mb-5 text-muted animate" data-toggle="animation" data-animation="fadeUp" data-animation-order="2" data-animation-trigger="load">
                Dicta itaque ad iusto perspiciatis eum alias quibusdam, odit id pariatur repudiandae ipsum, nostrum nisi laboriosam ex quas eius totam excepturi debitis.
              </p>

            </div>
          </div> <!-- / .row -->
        </div> <!-- / .container -->
        <br>
      </section>
        <div class="container">
          <div class="row"  >
            <div class="col-12 col-md-6 col-lg-4 alert-danger" v-for="(product, i) in inventory" :key="i">

              <!-- Item -->
              <div class=" card position-relative">

                  <!-- Image -->
                  <img :src="require(`@/assets/images/${product.photo}`)" :alt="product.name" class="card-img">

                  <!-- Body -->
                  <div class="card-body">

                    <div class="row align-items-center mb-3">
                      <div class="col">

                        <!-- Heading -->
                        <h4 class="card-title mb-0">
                         {{ product.name }}
                        </h4>

                      </div>
                      <div class="col-auto">

                        <p class="mb-0 text-sm text-muted">
                          $ {{ (product.price).toFixed(2) }}
                        </p>

                      </div>
                    </div> <!-- / .row -->

                    <!-- Text -->
                    <p class="mb-0 text-sm text-muted">

                      <router-link  class="w-100 btn btn-info btn-lg mt-3" :to="{ name: 'product', params: { id: product.name } }">Voir detail</router-link>
                    </p>

                  </div>

              </div>
 <br>
            </div>
          </div> <!-- / .row -->
        </div> <!-- / .container -->
      </section>
</template>

<script>
export default {
  props: ['inventory', 'addTo']
}
</script>
