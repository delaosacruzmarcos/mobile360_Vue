<template>
        <form @submit="changePage">
          <div class="form-group">
            <label for="exampleInputEmail1">Email address</label>
            <input type="email" class="form-control" id="exampleInputEmail1" aria-describedby="emailHelp">
          </div>
          <div class="form-group">
            <label for="exampleInputPassword1">Password</label>
            <input type="password" class="form-control" id="exampleInputPassword1">
          </div>
          <button type="submit" class="btn btn-success">Sign in</button>
          <p>
              <small>
                  Don't have an account yet?
              </small>
              <small style="color:green" class="clickable" @click="register">Register here</small>
          </p>
        </form>
</template>

<script>
export default {
    name:'Login',
    methods:{
        register(){
            this.$emit('register')
        },
        changePage(){
            this.$emit('changepage')
        }
    }
}
</script>

<style scoped>
.clickable{
    cursor: pointer;
}
</style>