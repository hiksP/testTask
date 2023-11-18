<template>
  <div class="notFound">
    <h2 class="notFound__empty">Адреса не найдены</h2>
    <p class="notFound__text">Попробуйте другой запрос</p>
  </div>
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
.notFound {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}
.notFound__empty {
  font-size: 32px;
  margin-top: 10%;
  color: #961246;
  font-weight: 700;
}

.notFound__text {
  font-size: 18px;
  margin-top: 5px;
  color: rgb(40, 40, 40);
}

@media screen and (max-width: 600px) {
  .notFound__empty {
    font-size: 26px;
  }

  .notFound__text {
    font-size: 16px;
  }
}
</style>