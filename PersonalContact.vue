<template>
  <div class="container">
    <div class="container-right">
      <a href>
        <span>
          <b>PROFIL</b>
        </span>
      </a>
      <a href>
        <b>CONTACT</b>
      </a>
    </div>
    <br />
    <h2>Mihai Dornescu</h2>
    <form>
      <br />
      <label for v-for="(item, key, index) in form" :key="key">
        {{key}}
        <input
          type="text"
          v-model="form[key]"
          :ref="types[index]"
          :id="types[index]"
          @keypress.enter="personalFunctie(types[index + 1])"
          :placeholder="key"
        />
        <br />
        <br />
      </label>

      <!-- radio buttons -->
      <div class="container-light">
        <!-- varianta 1 -->

        <input type="radio" id="male" name="gender" value="male" v-on:click="click"  />
        <label for="male">Male</label>
        <br />
        <input type="radio" id="female" name="gender" value="female"  v-on:click="click"/>
        <label for="female">Female</label>

        <!-- varianta 2 -->
          <!-- <label for=''> {{key}}
            <input type="radio" v-model="sex[key]"
          :ref="sex[index]"
          :id="sex[index]"
          @keypress.enter="altaFunctie(sex[index + 1])">
          </label> -->
        <br />
      </div>

      <!-- buton de save  -->
      <br />
      <a href="#/" v-on:click="Button" class="Button">Save</a>
      <br />
      <br />
    </form>
  </div>
</template>


<script>
export default {
  data() {
    return {
      types: ["email", "telefon", "varsta"],
      form: {
        email: undefined,
        telefon: undefined,
        varsta: undefined,
      },
      sex: ["MALE","FEMALE"]
    };
  },
  methods: {
    personalFunctie(ceva) {
      // console.log(ceva);
      ceva && this.$refs[ceva][0].focus();
    },
    altaFunctie(altceva){
      altceva && this.$refs[altceva][0].focus();
    }
  }
};
</script>

<style>
.container {
  display: inline-block;
  width: 80vh;
  border: 1px solid #ccc;
}
.container-right {
  display: flex;
  justify-content: flex-end;
  align-content: space-between;
}
a {
  padding: 20px;
}
.container-light {
  display: flex;
  justify-content: center;
  align-content: center;
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
span {
  color: #3e7327;
}
</style>