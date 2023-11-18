<template>
  <form @submit.prevent class="form">
    <div class="form__input-container">
      <img src="../assets/search-svg.svg" class="form__input-image">
      <input v-bind:value="adress" @input="adress = $event.target.value" class="form__input" placeholder="Введите адрес">
    </div>
    <button @click='searchSubmit' class="form__button">Поиск</button>
  </form>
</template>

<script>
  export default {
  data() {
      return {
        adress: ''
      }
  },
  methods: {
    searchSubmit() {
      this.$emit('searchSubmit', this.adress)
      this.adress = ''
    }
    }
  }
</script>

<style scoped>
*{
  margin: 0;
  padding: 0;
}

.form {
  display: flex;
  flex-direction: column;
  align-items: center;
}

.form__input-container {
  display: flex;
  align-items: center;
  justify-content: center;
  width: 425px;
  padding: 0 10px;
  background-color: #ffffff;
  box-shadow: 3px 3px 7px rgb(207, 207, 207);
  border-radius: 10px;
  height: 75px;
  margin-bottom: 30px;
}

.form__input-image {
  width: 30px;
  height: 30px;
  margin-right: 10px;
}

.form__input {
  border: none;
  outline: none;
  width: 100%;
  font-size: 18px;
  color: rgb(40, 40, 40);
}


.form__button {
  width: 240px;
  height: 50px;
  border-radius: 50px;
  font-size: 18px;
  border: none;
  color: white;
  background-color: #34a8b8;
  box-shadow: 2px 2px 4px #34a8b8;
  transition: opacity .6s ease-in-out;
}

.form__button:hover {
  opacity: .5;
  cursor: pointer;
}

@media screen and (max-width: 1025px) {
  .form__input-container  {
    width: 375px;
    height: 65px
  }

  .form__input  {
    font-size: 16px;
  }

  .form__button  {
    width: 200px;
    height: 40px;
    font-size: 16px;
  }
}

@media screen and (max-width: 800px) {
  .form__input-container  {
    width: 325px;
    height: 60px
  }

  .form__button  {
    width: 180px;
  }
}

@media screen and (max-width: 600px) {
  .form__input-container  {
    width: 280px;
    height: 50px;
    margin-bottom: 20px;
  }

  .form__input-image {
    width: 20px;
    height: 20px;
  }

  .form__button  {
    width: 165px;
    height: 35px;
  }
}
</style>