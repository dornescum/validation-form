<template>
  <div class="container">
    <form>
      <h2>Login</h2>
      <label for v-for="(item, key, index) in form" :key="key">

        {{key}}
        <input  type="text" v-model="form[key]"
               :ref="types[index]"
               :id="types[index]"
               @keypress.enter="oFunctie(types[index + 1])" :placeholder="key"/>


        <br />
        <br />
      </label>

   

      <br />
      <br />
  
      <a href="#/about"  class="Button">login</a>
      <br />
      <br />
    </form>
  </div>
</template>

<script>
export default {
  data() {
    return {
      types: ["email", "parola"],
      form: {
        email: undefined,
        parola: undefined,
      },
      
    };
  },
  methods: {
    oFunctie(ceva){
      // console.log(ceva);
      ceva && this.$refs[ceva][0].focus()
    }
    
  }
};
</script>
<style scoped>
.container {
  display: inline-block;
  width: 80vh;
  border: 1px solid #ccc;
}
.Button {
  box-shadow: 0px 10px 14px -7px #3e7327;
  background: linear-gradient(to bottom, #77b55a 5%, #72b352 100%);
  background-color: #77b55a;
  border-radius: 4px;
  border: 1px solid #4b8f29;
  display: inline-block;
  cursor: pointer;
  color: #ffffff;
  font-family: Arial;
  font-size: 19px;
  font-weight: bold;
  padding: 6px 12px;
  text-decoration: none;
  text-shadow: 0px 2px 0px #5b8a3c;
  width: 70%;
}
.Button:hover {
  background: linear-gradient(to bottom, #72b352 5%, #77b55a 100%);
  background-color: #72b352;
}
.Button:active {
  position: relative;
  top: 1px;
}
</style>