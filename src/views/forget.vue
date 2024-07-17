<template>
    <transition name="fade">
        <div v-if="myshow" class="container">
            <p class="mytext">Enter the your email adress and we'll send you a link to reset your password</p>
            <input autofocus type="email" name="forgot" id="forgot" placeholder="Email">
            <button>Send code</button>
            <p class="mylink" >Don't have account? <router-link to="/register">sign up</router-link></p>
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
.mylink{
    margin-top: 2rem;
    text-align: center;
}
.mytext{
    font-size: 0.9rem;
    text-align: center;
}
.mylink a{
    text-decoration: none;
    color: rgb(57, 73,171);
}
input{
    margin-top: 2.5rem;
    padding: 6px
}
button{
    margin-top: 0.4rem;
    background-color: transparent;
    background-color: rgb(57, 73,171);
    color: white;
    padding:8px 0 7px;
    font-size: 0.9rem;
    border: none;
    cursor: pointer;
}
.container{
    width: 25%;
    display: flex;
    flex-direction: column;
    padding: 10% 3%;
}
</style>