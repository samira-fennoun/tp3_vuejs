<template>
    <div class="product-add">
      <!-- Section-->
      <section class="py-5">
        <div class="container px-4 px-lg-5 mt-5">
          <div
            class="
              row
              gx-4 gx-lg-5
              row-cols-2 row-cols-md-3 row-cols-xl-2
              justify-content-center
            "
          >
            <div class="col-sm-12">
              <h4 class="mb-3">Ajouter un nouveau produit</h4>
              <div class="alert alert-danger" v-show="message">{{ message }}</div>
              <div class="needs-validation" novalidate>
                <div class="row g-2">
                  <div v-if="!submitted">
                  <div class="col-12">
                    <label for="productName" class="form-label"
                      >Nom du produit</label
                    >
                    <input
                      type="text"
                      class="form-control"
                      id="productName"
                      placeholder=""
                      v-model = "product.name"
                      required
                    />
                    <div class="invalid-feedback">Un nom valide est obligatoire</div>
                  </div>
                  <div class="col-12">
                    <label for="productPhoto" class="form-label"
                      >Photo du produit</label
                    >
                    <input
                      type="text"
                      class="form-control"
                      id="productPhoto"
                      placeholder=""
                      v-model="product.photo"
                      required
                    />
                    <div class="invalid-feedback">
                     Une photo valide est obligatoire
                    </div>
                  </div>
                  <div class="col-12">
                    <label for="productPrice" class="form-label">Prix</label>
                    <div class="input-group has-validation">
                      <span class="input-group-text">CAD</span>
                      <input
                        type="text"
                        class="form-control"
                        id="productPrice"
                        placeholder=""
                        v-model.number="product.price"
                        required
                      />
                      <div class="invalid-feedback">un prix valide est obligatoire</div>
                    </div>
                  </div>
                  <div class="col-12">
                    <label for="productDescription" class="form-label"
                      >Description du produit</label
                    >
                    <textarea
                      class="form-control"
                      id="productDescription"
                      placeholder=""
                      v-model="product.description"
                    ></textarea>
                    <div class="invalid-feedback">Description Valid est obligatoire</div>
                  </div>
                  <div class="col-12">
                    <label for="productType" class="form-label"
                      >Catégorie de produit</label
                    >
                    <select
                      class="form-control"
                      id="productType"
                      placeholder=""
                      v-model="product.category"
                      required
                    >
                      <option value="">Select</option>
                      <option value="salee">salee</option>
                      <option value="sucrée">sucrée</option>
                      <option value="orientale">orientale</option>
                      <option value="indienne">indienne</option>
                      <option value="asiatique">asiatique</option>
                    </select>
                    <div class="invalid-feedback">
                      Valid photo path is required.
                    </div>
                  </div>
                  <button class="w-100 btn btn-secondary btn-lg mt-3" type="button" @click="saveProduct">Enregister</button>
                  </div>
                  <div v-else>
                    <div  class="alert alert-success alert-dismissible fade show" role="alert">
                    <strong> Vous avez soumis avec succès!</strong>
                    <button type="button" class="btn-close" data-bs-dismiss="alert" aria-label="Close"></button>
                    </div>
                    <button class="w-100 btn btn-success btn-lg mt-3" type="button" @click="newProduct">Nouveau produit </button>
                  </div>
                  <hr class="my-4">
                </div>
              </div>
            </div>
          </div>
        </div>
      </section>
    </div>
  </template>

<script>
import ProductDataService from '@/services/ProductDataService'
export default {
  props: ['addInv'],
  data () {
    return {
      message: null,
      submitted: false,
      product: {
        name: '',
        photo: '',
        price: '',
        description: '',
        category: ''
      }
    }
  },
  methods: {
    saveProduct () {
      ProductDataService.create(this.product)
        .then(response => {
          // console.log(response.data)
          this.product.id = response.data.id
          this.addInv(this.product)
          this.message = null
          this.submitted = true
          // this.$router.push({ name: 'home' })
          // console.log(this.submitted)
        })
        .catch(e => {
          console.log(e.response.data.message)
          this.message = e.response.data.message
        })
    },
    newProduct () {
      this.submitted = false
      this.product = {}
    }
  }
}
</script>
