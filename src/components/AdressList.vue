<template>
  <div v-if:="this.found" class="adress"> 
    <h2 v-bind:hidden="this.adressItems.length <= 0" class="adress__results">Результаты:</h2>
    <ul class="adress__list">
      <AdressItem 
      v-for="adressItem in adressItems"
      :adressItem="adressItem"
      :key="adressItem.value"
      ></AdressItem>
    </ul>
  </div>
  <NotFound v-else></NotFound>
</template> 

<script>
import AdressItem from './AdressItem.vue';
import NotFound from '../UI/NotFound.vue';

  export default {
    props: {
        adressItems: {
            type: Array,
            required: true
      },
        found: {
          type: Boolean,
      },
  },
    components: { AdressItem, NotFound }
}
</script>

<style scoped>
*{
  margin: 0;
  padding: 0;
}

.adress {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}

.adress__results {
  font-size: 24px;
  color: black;
  font-weight: 600;
  margin: 25px 0;
}

.adress__list {
  display: flex;
  flex-direction: column;
  list-style: none;
}

.adress__list:last-child {
  padding-bottom: 40px;
}

@media screen and (max-width: 1025px) {
  .adress__results  {
    font-size: 20px;
  }
}

@media screen and (max-width: 800px) {
  .adress__results  {
    font-size: 18px;
    margin: 15px 0;
  }
}

@media screen and (max-width: 440px) {
  .adress__results  {
    font-size: 16px;
  }
}
</style>