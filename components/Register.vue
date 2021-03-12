<template>
        <form @submit="goLogin" class="container-fluid">
            <div class="row">
                <div class="col">
                    <label for="fName">First Name</label>
                    <input id="fName" type="text" class="form-control" placeholder="First name">
                </div>
                <div class="col">
                    <label for="lName">Last Name</label>
                    <input id="lName" type="text" class="form-control" placeholder="Last name">
                </div>
            </div>
            <div class="form-group">
                <label for="exampleInputEmail1">Email address</label>
                <input type="email" class="form-control" id="exampleInputEmail1" placeholder="Email">
            </div>
            <div class="row">
                <div class="col">
                    <label for="password">Password</label>
                    <input id="password" type="password" class="form-control" placeholder="Password">
                </div>
                <div class="col">
                    <label for="confirmPassword">Confirm Password</label>
                    <input id="" type="password" class="form-control" placeholder="Re-enter Password">
                </div>
            </div>
            <div class="form-group">
                <label for="dob">Date of Birth</label>
                <input class="form-control" type="date" name="dob" id="dob" placeholder="Date of Birth">
            </div>
            <button type="submit" class="btn btn-warning">Register</button>
            <p>
                <small>
                    Already have an account?
                </small>
                <small style="color:green" @click="signin">
                    Sign in
                </small>
            </p>
        </form>
</template>

<script>
export default {
    name:'Register',
    methods:{
        signin(){
            this.$emit('signin')
        }
    }
}
</script>

<style scoped>
small{
    cursor: pointer;
}
</style>