<template>
  <div id="app">
      <NavBar />
        <Router-view
        :inventory = "inventory"
        :addTo = "addToCart"
        :addInv = "addInventory"
        :removeInv = "removeInventory"
        :remItem = "removeItem"
        :updateInv = "updateInventory"
        />
        <FooterView />
 </div>
</template>

<script>
import NavBar from '@/components/NavBar.vue'
import FooterView from '@/components/FooterView.vue'
import ProductDataService from '@/services/ProductDataService'

export default {
  name: 'App',
  components: {
    NavBar,
    FooterView
  },
  data: () => {
    return {
      showSideBar: false,
      inventory: [],
      cart: {}
    }
  },
  methods: {
    toggleSideBar () {
      this.showSideBar = !this.showSideBar
    },
    addToCart (product, index) {
      if (!this.cart[product]) this.cart[product] = 0
      this.cart[product] += this.inventory[index].quantity
      this.inventory[index].quantity = 0
    },
    removeItem (name) {
      delete this.cart[name]
    },
    addInventory (product) {
      this.inventory.push(product)
    },
    removeInventory (index) {
      this.inventory.splice(index, 1)
    },
    updateInventory (index, data) {
      this.inventory[index].name = data.name
      this.inventory[index].photo = data.photo
      this.inventory[index].price = data.price
      this.inventory[index].description = data.description
      this.inventory[index].category = data.category
    }
  },
  computed: {
    totalQuantity () {
      return Object.values(this.cart).reduce((acc, curr) => {
        return acc + curr
      }, 0)
    }
  },
  mounted () {
    ProductDataService.getAll()
      .then(response => {
        this.inventory = response.data
        console.log(response.data)
      })
  }
}
</script>
