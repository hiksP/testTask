<template>
  <Header></Header>
  <Form @searchSubmit="searchSubmit"></Form>
  <AdressList v-if="!isLoading" :adressItems="adressItems" :found="found" :isLoading="isLoading"></AdressList>
  <Loader v-else></Loader>
</template>

<script>
import Header from './components/Header.vue';
import Form from './components/Form.vue'
import AdressList from './components/AdressList.vue';
import Loader from './UI/Loader.vue';

// тут вставьте свой api ключ
const token = import.meta.env.VITE_API_KEY;

export default {
  components: {
    Header, Form, AdressList, Loader
  },
  data() {
    return {
      adressItems: [],
      found: true,
      isLoading: false,
      }
  },
  methods: {
    async searchSubmit(adress) {
      this.isLoading = true
      const url = "https://suggestions.dadata.ru/suggestions/api/4_1/rs/suggest/address";
      const adressArray = []

      const options = {
          method: "POST",
          mode: "cors",
          headers: {
              "Content-Type": "application/json",
              "Accept": "application/json",
              "Authorization": "Token " + token
          },
          body: JSON.stringify({query: adress})
      }

      try {
      const response = await fetch(url, options)
      const data = await response.text()
      const dataObject = await JSON.parse(data)

      if (dataObject.suggestions.length <= 0) {
        this.found = false
      } else {
        this.found = true
      }

      dataObject.suggestions.forEach((item) => {
        const { value } = item
        const { country, region } = item.data
        adressArray.push({
          country,
          region,
          value
        })
      })
      } catch (e) {
        alert('Произошла ошибка')
      }
      this.adressItems = adressArray
      this.isLoading = false
    }
  }
  }
</script>

<style>

</style>