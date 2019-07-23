<template>
  <div class="hello">
    <li class="crop" v-bind:key="item" v-for="item in data">
      <div class="card">
        <img class="image" :src="item.avatar_url || imageDefault" alt="Avatar" style="width:100%">
        <div class="container">
          <h4><b>{{item.name}}</b></h4> 
          <h5><b>{{item.github_url}}</b></h5> 
          <p>{{item.nickName}}</p> 
        </div>
      </div>
    </li>
  </div>
</template>

<script>
import json from '../assets/data.json'
export default {
  name: 'HelloWorld',
  props: {
    msg: String,
  },
  data: function() {
    return{
      imageDefault: require("../assets/nofound.jpg")
    }
  },
  computed:{
  data(){
    return json.users.map((item) => {
        return item;
      })
  }
  }
}
</script>
<style scoped>
h3 {
  margin: 40px 0 0;
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
.card {
  box-shadow: 0 4px 8px 0 rgba(0,0,0,0.2);
  transition: 0.3s;
}

.card:hover {
  box-shadow: 0 8px 16px 0 rgba(0,0,0,0.2);
}

.container {
  padding: 2px 16px;
}
.crop {
 height: 600px;
 width: 400px;
 overflow: hidden;
}
.crop img {
 height: auto;
 width: 400px;
}
</style>
