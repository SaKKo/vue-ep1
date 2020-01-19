<template lang="html">
  <div>
    <ul>
      <li v-for="book in books">
        {{ book.name }}
      </li>
    </ul>
  </div>
</template>

<script>
import axios from 'axios'
export default {
  data() {
    return {
      books: []
    }
  },
  mounted() {
    axios
      .get('http://localhost:3003/books')
      .then((response) => {
        // handle success
        this.books = response.data
        console.log(response)
      })
      .catch((error) => {
        // handle error
        console.log(error)
      })
      .finally(() => {
        // always executed
      })
  }
}
</script>

<style lang="css" scoped></style>
