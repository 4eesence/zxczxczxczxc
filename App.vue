<!-- <template>
  <div>
    <input type="text" v-model="newItemText">
    <button @click="addItem">Жмякай</button>
    <ul>
      <li v-for="(item, index) in items" :key="index">{{ item }}</li>
    </ul>
  </div>
</template>

<script>
export default {
  data() {
    return {
      newItemText: '',
      items: ['я 1', 'я 2', 'я 3']
    };
  },
  methods: {
    addItem() {
      if (this.newItemText.trim() !== '') {

        this.items.unshift(this.newItemText);
      }
    }
  }
};
</script> -->



<template>
  <div :class="{ 'card': true, 'favorite': isFavorite }">
    <img :src="product.image" :alt="product.name" />
    <h3>{{ product.name }}</h3>
    <p>{{ product.description }}</p>
    <button @click="toggleFavorite">
      {{ isFavorite ? 'Remove from Favorites' : 'Add to Favorites' }}
    </button>
  </div>
</template>

<script>
import { ref } from 'vue';

export default {
  props: {
    product: Object,
  },
  setup(props) {
    const isFavorite = ref(false);

    const toggleFavorite = () => {
      isFavorite.value = !isFavorite.value;
      // Здесь можно добавить логику для добавления в избранное в родительском компоненте
    };

    return { isFavorite, toggleFavorite };
  }
};
</script>

<style>
.card {
  border: 1px solid #ccc;
  padding: 10px;
  margin: 10px;
}

.favorite {
  background-color: lightyellow;
}
</style>