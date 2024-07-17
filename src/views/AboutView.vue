<template>
    <transition name="fade">
        <div class="container" v-if="myshow">
            <input type="text" placeholder="Username">
            <input type="text" placeholder="Firstname">
            <input type="text" placeholder="Lastname">
            <input type="email" placeholder="Email">
            <input type="password" placeholder="Create password">
            <input type="password" placeholder="Confirm password">
            <button>Sign up</button>
            <p>Already have an account <router-link to="/">log in</router-link></p>
        </div>
    </transition>
    
</template>
<script>
export default {
  data() {
    return {
      myshow: false, 
    };
  },
  beforeRouteEnter(to, from, next) {
    next(vm => {
      setTimeout(() => {
        vm.myshow = true; 
      }, 0); 
    });
  },
  beforeRouteLeave(to, from, next) {
    this.myshow = false;
    setTimeout(() => next(), 400); 
  },
};
</script>
<style scoped>
input{
    background-color: transparent;
    border: 1.2px solid black;
    padding: 10px;
}
button{
    background-color: rgb(57,73,171);
    color: white;
    padding: 10px;
    border-radius: 14px;
    border: none;
    margin-top: 4px;
    cursor: pointer;
    letter-spacing: 0.6px;
}
p{
    text-align: center;
}
p a{
    text-decoration: none;
    color:  rgb(57,73,171);
}
.container{
    width: 25%;
    border:   black;
    display: flex;
    flex-direction: column;
    padding: 5% 3%;
    gap: 0.8rem;
}
</style>