<template>
  <id class="app">
    <input type="text" maxlength="7" v-model="postcode"/>
    <button @click="searchAddress">住所自動入力</button>
      <p>Adderss：{{allAddress}}</p>
  </id>
</template>

<script>
export default {
  data() {
    return {
      postcode:"",
      allAddress: ""
    }
  },
  methods: {
    searchAddress() {
      this.axios.get(`https://apis.postcode-jp.com/api/v3/postcodes?postcode=w8HPtAhnk3waN3B52CFYOXSLzvOYKrWha0b8DCf`)
      .then((response) =>{
        this.allAddress = response.data.allAddress;
      });
    },
  },
};
</script>
