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
                                    <select class="form-control">
                                        <option>Бренд</option>
                                        <option>Super</option>
                                        <option>Puper</option>
                                        <option>Cool</option>
                                        <option>Like</option>
                                    </select>
                                </div>
                                <div class="form-group">
                                    <select class="form-control">
                                        <option>Размер</option>
                                        <option>29</option>
                                        <option>31</option>
                                        <option>35</option>
                                        <option>37</option>
                                        <option>42</option>
                                    </select>
                                </div>
                                <div class="form-group">
                                    <select class="form-control">
                                        <option>Цвет</option>
                                        <option>Синий</option>
                                        <option>Красный</option>
                                        <option>Зеленый</option>
                                        <option>Белый</option>
                                        <option>Серый</option>
                                    </select>
                                </div>
                                <div class="text-right">
                                    <a href="#" class="btn btn-sm btn-secondary">Сбросить</a>
                                </div>
                            </form>
                        </div>
                    </div>
                </div>
            </div>
        </div>
        <div class="alert alert-light" role="alert">
            Найдено 2 товара
        </div>
        <div class="row no-gutters">
            <div class="col-6 pr-2">
                <div class="card text-center border-0 shadow-sm mb-3 bg-white rounded-lg">
                    <img class="card-img-top"
                        src="https://media.istockphoto.com/photos/male-coat-isolated-on-the-white-picture-id163208487">
                    <div class="card-body p-1 m-1">
                        <h5 class="card-title mb-0">Название</h5>
                        <div class="card-text">
                            <div>
                                <small class="card-text text-muted">
                                    Категория
                                </small>
                            </div>
                            <div>
                                <del>5 900</del>
                                <strong>3 790 ₽</strong>
                            </div>
                        </div>
                        <a href="#" class="btn btn-primary stretched-link m-1">Купить</a>
                    </div>
                </div>
            </div>
            <div class="col-6 pl-2">
                <div class="card text-center border-0 shadow-sm mb-3 bg-white rounded-lg">
                    <img class="card-img-top"
                        src="https://media.istockphoto.com/photos/red-womans-sports-jacket-picture-id520887025">
                    <div class="card-body p-1 m-1">
                        <h5 class="card-title mb-0">Название</h5>
                        <div class="card-text">
                            <div>
                                <small class="card-text text-muted">
                                    Категория
                                </small>
                            </div>
                            <div>
                                <del>5 900</del>
                                <strong>3 790 ₽</strong>
                            </div>
                            <div class="alert alert-dark p-0 m-0" role="alert">
                                <div>
                                    <small>
                                        <strong>Бренд</strong> Super
                                    </small>
                                </div>
                                <div>
                                    <small>
                                        <strong>Размер</strong> 34
                                    </small>
                                </div>
                                <div>
                                    <small>
                                        <strong>Цвет</strong> красный
                                    </small>
                                </div>
                            </div>
                        </div>
                        <a href="#" class="btn btn-primary stretched-link m-1">Купить</a>
                    </div>
                </div>
            </div>
        </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'GoodsComponent',
  created () {
    window.products = [
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
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
