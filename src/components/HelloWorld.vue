<template>
<div class="container my-3">
  <form action="">
    <div class="left-box">
      <div class="header text-center">
        <h1>Register</h1>
      </div>
      <div class="form-group">
        <label for="name">Name</label>
        <input type="text" class="form-control" id="name" placeholder="Enter Name" v-model="name">
      </div>
      <div class="form-group">
        <label for="age">Age</label> 
        <input type="number" class="form-control" id="age" placeholder="Enter Age" v-model="age">
      </div>
      <div class="form-group">
        <label for="province">Province</label>
        <input type="text" class="form-control" id="province" placeholder="Enter Province" v-model="province">
      </div>
    </div>
    
  </form>
    <table class="table table-bordered my-3">
    <thead>
      <tr>
        <th>Name</th>
        <th>Age</th>
        <th>Province</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>{{getName}}</td>
        <td>{{getAge}}</td>
        <td>{{getProvince}}</td>
      </tr>
    </tbody>
  </table>
</div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data(){
    return{
      name: '',
      age: 0,
      province: '',
      add: false,
    }

  },
  computed:{
    getName(){
      return this.name;
    },
    getAge(){
      const age = this.age;
      if (age >0 && age <15){
        return "You are Child";
      }else if (age>=15 && age < 18){
        return "You are young";
      }else if (age>=18 && age <30){
        return "You are Adult";
      }else if (age>30){
        return "You are elder";
      }else{
        return null;
      }
    },
    setColor(){
      const age = this.age
      return {
        color: age>18 && age <30 ? "green" : "red"
      }
    },
    getProvince(){
      return this.province;
    }
  },
  methods:{
    addUser(){
      this.users.push({
        name: this.name,
        age: this.age,
        province: this.province,
      })
    }
  }
      
}

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
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
</style>
