<template>
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
</script>
