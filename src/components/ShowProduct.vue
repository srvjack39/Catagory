<template>
  <div class="">
      asdsadsa
  </div>
</template>

<script>
import Firebase from 'firebase'
var config = {
  apiKey: 'AIzaSyCTH8Je0jlsaPAd4BexiN7p3Ase_qkmQUI',
  authDomain: 'catagory-64e94.firebaseapp.com',
  databaseURL: 'https://catagory-64e94.firebaseio.com',
  projectId: 'catagory-64e94',
  storageBucket: 'catagory-64e94.appspot.com',
  messagingSenderId: '633943125984'
}
let app = Firebase.initializeApp(config)
let db = app.database()
let CatagoryRef = db.ref('Catagory')

export default {
  name: 'ShowProduct',
  firebase: {
    Catagory: CatagoryRef
  },
  data () {
    return {
        name: '',
        Total: '',
        Price: '',
        img: ''
    }
  },
  methods: {
    insertNewCatagory () {
      let tmp = ({
        name: this.name,
        Total: this.Total,
        Price: this.Price,
        img: this.img
      })
      CatagoryRef.push(tmp)
      this.name = ''
      this.Total = ''
      this.Price = ''
      this.img = ''
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
