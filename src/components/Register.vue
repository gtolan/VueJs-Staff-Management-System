<template>
  <div>
    <div class="container">
      <div class="row">
        <div class="col s12 m8 offset-m2">
          <div class="login card-panel grey lighten-4 white-text center">
            <h3 class="black-text">Register</h3>
            <form action="index.html">
              <div class="input-field">
                <i class="material-icons prefix black-text">email</i>
                <input type="email" id="email" v-model="email">
                <label class="black-text" for="email">Email Address</label>
              </div>
              <div class="input-field">
                <i class="material-icons prefix black-text">lock</i>
                <input type="password" id="password" v-model="password">
                <label class="black-text" for="password">Password</label>
              </div>
              <button
       
                class="btn btn-large btn-extended grey lighten-4 black-text"
              >Login</button>
            </form>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Resgister",
  data: function() {
    return {
      email: "",
      password: ""
    };
  }
};
</script>

<style scoped>
</style>