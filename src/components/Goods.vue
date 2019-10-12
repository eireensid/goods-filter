<template>
  <div>
    <div class="container-fluid">
        <h1>Список товаров</h1>
        <div class="row">
            <div class="col-12">
                <div class="card">
                    <div class="card-body">
                        <h5 class="card-title">Фильтры</h5>
                        <div class="card-text">
                            <form>
                                <div class="form-group">
                                    <select class="form-control" v-model="brand">
                                        <option value="">Бренд</option>
                                        <option>Super</option>
                                        <option>Puper</option>
                                        <option>Cool</option>
                                        <option>Like</option>
                                    </select>
                                </div>
                                <div class="form-group">
                                    <select class="form-control" v-model="size">
                                        <option value="">Размер</option>
                                        <option>29</option>
                                        <option>31</option>
                                        <option>35</option>
                                        <option>37</option>
                                        <option>42</option>
                                    </select>
                                </div>
                                <div class="form-group">
                                    <select class="form-control" v-model="color">
                                        <option value="">Цвет</option>
                                        <option>Синий</option>
                                        <option>Красный</option>
                                        <option>Зеленый</option>
                                        <option>Белый</option>
                                        <option>Серый</option>
                                    </select>
                                </div>
                                <div class="text-right">
                                    <button :disabled="isFilterClearBtn" @click="filterClearBtnOnClick" class="btn btn-sm btn-secondary">
                                        Сбросить
                                        <!-- <a class="btn btn-sm btn-secondary" href="#">Сбросить</a> -->
                                    </button>
                                </div>
                            </form>
                        </div>
                    </div>
                </div>
            </div>
        </div>
        <div class="alert alert-light" role="alert">
            {{ findGoodsCountText }}
        </div>
        <div class="row">
          <div v-for="(p, ind) in filteredProducts" :key="'product' + ind" class="col-6 mb-4">
            <GoodCard @buy-good="onBuyGood" :name="p.name" :img="p.img" :category="p.category" :oldPrice="p.oldPrice" :price="p.price" :brand="p.brand" :size="p.size" :color="p.color" />
          </div>
        </div>
    </div>
    <Alert :goodName="buyGoodName"/>
  </div>
</template>

<script>
import GoodCard from './GoodCard.vue'
import Alert from './Alert.vue'

export default {
  name: 'GoodsComponent',
  components: {
    GoodCard, Alert
  },
  data () {
    return {
      products: [],
      brand: '',
      size: '',
      color: '',
      buyGoodName: ''
    }
  },
  computed: {
    findGoodsCountText () {
      let res = `Найдено ${this.filteredProducts.length} товара`
      if (this.filteredProducts.length % 10 === 1) {
        res = `Найден ${this.filteredProducts.length} товар`
      }
      return res
    },
    filteredProducts () {
      let res = []
      for (let i = 0; i < this.products.length; i++) {
        let cur = this.products[i]
        const isColor = !this.color || cur.color.toLowerCase() === this.color.toLowerCase()
        const isBrand = !this.brand || cur.brand.toLowerCase() === this.brand.toLowerCase()
        const isSize = !this.size || String(cur.size).toLowerCase() === this.size.toLowerCase()
        if (isColor && isBrand && isSize) {
          res.push(cur)
        }
      }
      return res
    },
    isFilterClearBtn () {
      return !this.color && !this.brand && !this.size
    }
  },
  created () {
    this.products = [
      {
        id: 1,
        name: 'куртка красная',
        img: 'https://media.istockphoto.com/photos/male-coat-isolated-on-the-white-picture-id163208487',
        category: 'куртки',
        oldPrice: 5880,
        price: 4790,
        brand: 'super',
        size: 31,
        color: 'красный'
      },
      {
        id: 2,
        name: 'куртка большая',
        img: 'https://media.istockphoto.com/photos/red-womans-sports-jacket-picture-id520887025',
        category: 'куртки',
        oldPrice: 5900,
        price: 3790,
        brand: 'super',
        size: 42,
        color: 'зеленый'
      },
      {
        id: 3,
        name: 'куртка модная',
        img: 'https://media.istockphoto.com/photos/male-coat-isolated-on-the-white-picture-id163208487',
        category: 'куртки',
        price: 5550,
        brand: 'puper',
        size: 29,
        color: 'красный'
      },
      {
        id: 4,
        name: 'куртка выгодная',
        img: 'https://media.istockphoto.com/photos/red-womans-sports-jacket-picture-id520887025',
        category: 'куртки',
        oldPrice: 7900,
        price: 1990,
        brand: 'super',
        size: 29,
        color: 'зеленый'
      }
    ]
  },
  methods: {
    filterClearBtnOnClick () {
      this.brand = ''
      this.size = ''
      this.color = ''
    },
    onBuyGood (goodName) {
      this.buyGoodName = goodName
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
