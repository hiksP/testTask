<template>
      <li @click="goToHandler" class="adress__element">
        <img @click.stop class="adress__element-image" src="../assets/building-svgrepo-com.svg">
        <div class="adress__element-container">
          <h2 class="adress__element-country">{{ adressItem.country + ', Область: ' + adressItem.region }}</h2>
          <p class="adress__element-value">{{ adressItem.value }}</p>
        </div>
      </li>
</template>

<script>
  export default {
  props: {
      adressItem: {
      type: Object,
      required: true, 
      }
  },
  methods: {
    goToHandler() {
      window.open(`https://www.google.com/search?q=${this.adressItem.value}`);
    }
  }
  }
</script>

<style scoped>
*{
  margin: 0;
  padding: 0;
}

.adress__element {
  display: flex;
  flex-direction: row;
  align-items: center;
  background-color: #ffffff;
  color: rgb(40, 40, 40);
  box-shadow: 3px 3px 7px rgb(207, 207, 207);
  padding: 25px;
  border-radius: 10px;
  margin-top: 20px;
  min-width: 300px;
  max-width: 800px;
  transition: color .4s ease-in-out;
}

.adress__element:hover {
  color: #ffac34;
  opacity: .8;
  cursor: pointer;
}

.adress__element-image {
  width: 40px;
  height: 40px;
  margin-right: 10px;
}

.adress__element-country {
  font-size: 22px;
  font-weight: 700;
}

.adress__element-value {
  font-size: 18px;
}


@media screen and (max-width: 1025px) {
  .adress__element  {
    min-width: 250px;
    max-width: 600px;
  }

  .adress__element-image  {
    width: 30px;
    height: 30px;
  }

  .adress__element-country  {
    font-size: 20px;
  }
}

@media screen and (max-width: 800px) {
  .adress__element  {
    min-width: 220px;
    max-width: 500px;
  }
}

@media screen and (max-width: 625px) {
  .adress__element {
    max-width: 400px;
    padding: 10px;
    margin-top: 15px;
  }

  .adress__element-country  {
    font-size: 16px;
  }

  .adress__element-value {
    font-size: 14px;
  }
}

@media screen and (max-width: 440px) {
  .adress__element {
    min-width: 265px;
    max-width: 280px;
  }
}
</style>