<template>
  <h1>add head of the table</h1>
  <input class="input" v-model="input_value"/>
  <button class="btn" @click="add">add</button>
  <table class="table">
    <tr>
      <th v-for="el in input_value_arr" :key="el">{{el}}</th>
    </tr>
    <tr>
      <td v-for="el in input_value_arr" :key="el"><input class="input"/></td>
    </tr>
    <tr class="toadd" v-for="el in arr" :key="el">
      <td v-for="el in input_value_arr" :key="el"><input class="input"/></td>
    </tr>
  </table>
    <button class="btn" @click="addTr">+</button>
</template>

<script>

export default {
  components:{

  },
  data() {
    return {
      input_value:'',
      input_value_arr:[],
      item:'',
      arr:[]
    }
  },
  methods:{
    add() {
      this.input_value_arr.push(this.input_value);
    },
    addTr() {
      this.arr.push(this.item);
    }
  }
}
</script>

<style>
* {
  margin:0;
  padding:0;
}
#app {
  margin:0;
  padding:0;
  width:100vw;
  min-height:100vh;
  display:flex;
  justify-content: flex-start;
  align-items: center;
  flex-direction: column;
  font-family:monospace;
  background-color: peachpuff;
}
h1{
  color:white;
}
.input-box {
  display:flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
}
.btn {
  width:150px;
  height:50px;
  background-color: pink;
  border:2px solid white;
  border-radius:10px;
  color:white;
  font-size:18px;
}
.input{
  width:250px;
  height:50px;
  border:2px solid pink;
  border-radius: 15px;
  margin:5px;
  color:pink;
  font-size: 18px;
}
table {
  margin:5px;
  border:2px solid white;
  border-collapse: collapse;
}
th {
  width:260px;
  height:60px;
  color:white;
  font-size: 18px;
  border:2px solid white;
}
td {
  width:260px;
  height:60px;
  border:2px solid white;
}
</style>
