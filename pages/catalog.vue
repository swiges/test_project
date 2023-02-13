<template>
  <div class="container">
    <div class="navigation global">Lorem ipsum dolor.</div>
    <div class="content">
      <div class="equipment global">
        <div class="product-card" v-for="product in catalog">
          <div class="product-card-picture-wrap">
            <img class="product-card-picture" :src="product.image" :alt="product.name"/>
          </div>
          <h1>{{product.name}}</h1>
          <h2>{{menuCategory.find((el) => el.id === product.category).name}}</h2>
          <p>{{product.description}}</p>
          <div class="button-and-cost-buy">
          <span>{{product.cost}}$</span>
          <button>Хуяк</button>
          </div>
        </div>
      </div>
      <div class="floor global">
        <div class="input-label">
          <span>Картинка</span>
          <input v-model="form.image"></input>
        </div>
        <div class="input-label">
          <span>Категорія</span>
          <input v-model="form.category"></input>
        </div>
        <div class="input-label">
          <span>Назва</span>
          <input v-model="form.name"></input>
        </div>
        <div class="input-label">
          <span>Опис</span>
          <input v-model="form.description"></input>
        </div>
        <div class="input-label">
          <span>Ціна</span>
          <input v-model="form.cost"></input>
        </div>
        <div class="button-add-product">
        <button @click="addProduct">Хуяк</button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "catalog",
  data() {
    return {
      catalog: [
        { image: 'https://picsum.photos/200', category: 25, name: 'Class', description: 'Lorem ipsum dolor.', cost: '100', id: 1 },
        { image: 'https://picsum.photos/200', category: 26, name: 'Woy', description: 'Lorem ipsum dolor sit.', cost: '120', id: 2 },
        { image: 'https://picsum.photos/200', category: 27, name: 'NotBad', description: 'Lorem ipsum.', cost: '80', id: 3 },
        { image: 'https://picsum.photos/200', category: 28, name: 'SoyGood', description: 'Lorem ipsum dolor sit amet.', cost: '180', id: 4 },
        { image: 'https://picsum.photos/200', category: 29, name: 'NoNoNo', description: 'Consectetur adipisicing elit. Sapiente.', cost: '10', id: 5 }
      ],
      form: {
        image: '',
        category: '',
        name: '',
        description: '',
        cost: '',
        id: '',
      },
      menuCategory: [
        {name: 'naturePorn', id: 25},
        {name: 'lesbianPorn', id: 26},
        {name: 'MWMPorn', id: 27},
        {name: 'WMWPorn', id: 28},
        {name: 'geyPorn', id: 29}
      ]
    }
  },
  methods: {
    addProduct() {
      const id = this.catalog[this.catalog.length - 1].id + 1

      this.form.id = id
      this.catalog.push(this.form)

      this.form = {
        image: '',
        category: '',
        name: '',
        description: '',
        cost: '',
        id: '',
      }
    }
  }
}




</script>

<style scoped>


.container {
  display: flex;
  flex-direction: row;
  align-content: flex-start;
  padding: 5px;
  box-sizing: border-box;
}
.global {
  border: 1px solid black;
  border-radius: 10px;
  box-sizing: border-box;
}
.navigation {
  width: 30%;
  max-width: 400px;
  min-width: 300px;
}

.content {
  width: auto;
  flex-grow: 1;
  padding-left: 5px;
}
.equipment {
  width: 100%;
  display: flex;
  flex-direction: row;
  gap: 10px;
}
.floor {
  margin-top: 5px;
  width: 100%;
}
.product-card {
  min-width: 240px;
  border: 1px solid black;
  padding: 0 5px 5px 5px;
}
.product-card-picture {
  border-radius: 30%;
}
.product-card-picture-wrap {
  display: flex;
  justify-content: center;
  padding-top: 5px;
}
.button-and-cost-buy {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
}
.input-label {
  display: flex;
  flex-direction: column;
  max-width: 400px;
  margin: 0 0 5px 10px;
}
.button-add-product {
  display: flex;
  flex-direction: column;
  max-width: 150px;
  margin: 0 0 5px 10px;
}
.button-add-product button {
  background-color: chartreuse;
}

</style>
