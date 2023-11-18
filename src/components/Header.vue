<template>
  <header class="header">
    <div class="header__container">
      <img src="../assets/address-svgrepo-com.svg" class="header__logo">
      <h1 class="header__title">Найти адрес</h1>
    </div>
  </header>
</template>

<script>
  export default {
    
  }
</script>

<style scoped>
*{
  margin: 0;
  padding: 0;
}

.header {
  display: flex;
  height: 125px;
  background-color: #9cde89;
  margin-bottom: 50px;
}

@media screen and (max-width: 1025px) {
  .header  {
    height: 100px
  }
}

.header__container {
  display: flex;
  justify-content: center;
  flex-direction: row;
  align-items: center;
  margin-left: 5%;
}

.header__logo {
  width: 125px;
  height: 125px;
}

.header__title {
  color: #961246;
  font-size: 32px;
  font-weight: 900;
}

@media screen and (max-width: 1025px) {
  .header__title  {
    font-size: 28px
  }
}

@media screen and (max-width: 600px) {
  .header__container {
    margin-left: 2%;
  }
  .header__logo  {
    width: 75px;
    height: 75px;
  }

  .header__title  {
    font-size: 24px
  }
}

</style>