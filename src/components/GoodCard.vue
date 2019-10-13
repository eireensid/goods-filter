<template>
  <div>
      <div @click="onClickCard" class="container">
          <div class="row no-gutters">
              <div class="col pl-2">
                  <div class="card text-center border-0 shadow-sm mb-3 bg-white rounded-lg">
                      <img class="card-img-top" :src="img">
                      <div class="card-body p-1 m-1">
                          <h5 class="card-title mb-0">{{ name }}</h5>
                          <div class="card-text">
                              <div>
                                  <small class="card-text text-muted">
                                      {{ category }}
                                  </small>
                              </div>
                              <div>
                                  <del>{{ oldPrice }}</del>
                                  <strong> {{ price }}</strong>
                              </div>
                              <div v-show="isShowAdditionalInfo" class="alert alert-dark p-0 m-0" role="alert">
                                  <div>
                                      <small>
                                          <strong>Бренд</strong> {{ brand }}
                                      </small>
                                  </div>
                                  <div>
                                      <small>
                                          <strong>Размер</strong> {{ size }}
                                      </small>
                                  </div>
                                  <div>
                                      <small>
                                          <strong>Цвет</strong> {{ color }}
                                      </small>
                                  </div>
                              </div>
                          </div>
                          <a @click="onClickBuyBtn" href="#" class="btn btn-primary m-1" data-toggle="modal" data-target="#exampleModal">Купить</a>
                      </div>
                  </div>
              </div>
          </div>
      </div>
  </div>
</template>

<script>
export default {
  name: 'GoodCard',
  data () {
    return {
      isBuyBtnClick: false,
      isShowAdditionalInfo: false
    }
  },
  props: [
    'name', 'img', 'category', 'oldPrice', 'price', 'brand', 'size', 'color'
  ],
  methods: {
    onClickBuyBtn () {
      this.isBuyBtnClick = true
      this.$emit('buy-good', this.name)
    },
    onClickCard () {
      if (!this.isBuyBtnClick) {
        this.isShowAdditionalInfo = !this.isShowAdditionalInfo
      }
      this.isBuyBtnClick = false
    }
  }
}
</script>

<style>

</style>
