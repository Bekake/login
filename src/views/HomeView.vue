<template>
    <transition name="fade">
        <div v-if="myshow" class="container">
            <h1>Welcome</h1>
            <div class="myinp">
                <div>
                    <img src="@/assets/mail.png" alt="Mail">
                    <input type="text" placeholder="Email" id="mail">
                </div>
                <div>
                    <img src="@/assets/lock.png" alt="Mail">
                    <img v-if="myeye" id="forimg" src="@/assets/closeeye.png" alt="Eye" @click="mypass">
                    <img v-else id="forimg" src="@/assets/eye.png" alt="Eye" @click="mypass">
                    
                    <input :type="myeye ? 'text' : 'password' " placeholder="Password" id="pass">
                </div>
            </div>
            <router-link to="/forget" class="mya">Forgot password?</router-link>
            <button class="log">Log in</button>
            <div class="forhr">
                <p class="same">Or</p>
                <hr>
            </div>
            <div class="mybut">
                <button><img src="@/assets/google.png" alt="Google"><span>Google</span></button>
                <button><img src="@/assets/gitlab.png" alt="Gitlab"><span>Gitlab</span></button>
            </div>
            <p class="same">Have no account yet</p>
            <router-link to="/register" class="reg">Registration</router-link>
        </div>
    </transition>
    
    
</template>
<script>
export default {
  name: 'HomeView',
  data(){
    return{
        myeye: false,
        myshow:false,
    }
  },
  methods:{
    mypass(){
        this.myeye =!this.myeye
    }
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
}
</script>
<style scoped>

.forhr{
    width: 100%;
    position: relative;
}
.mya{
    font-size: 0.8rem;
    letter-spacing: 0.5px;
    text-decoration: none;
    
    text-decoration: none;
    color: rgb(111,116,221);
    text-align: right;
}
.log{
    background-color: rgb(57,73,171);
    color: white;
}
.same{
    font-size: 0.9rem;
    font-weight: 500;
    letter-spacing: 0.3px;

}
.forhr hr{
    opacity: 0.5;
}
.forhr>p{
    position: absolute;
    left: 50%;
    transform: translate(-50%, -50%);
    background-color: white;
    z-index: 2;
    padding: 4px;
}

.log, .reg{
    font-size: 1rem;
    padding: 9px;
    letter-spacing: 0.5px;
    border: none;
    border-radius: 1rem;
    font-family: Open, Sans;
    font-weight: 500;
}
.reg{
    background-color: transparent;
    color: rgb(57,73,171);
    border: 1.4px solid rgb(57,73,171);
    text-align: center;
    text-decoration: none
}
.mybut img{
    width: 1.2rem;
}
.mybut span{
    font-size: 0.8rem;
    font-weight: 500;
    letter-spacing: 0.5px;
}
.mybut{
    width: 100%;
    display: flex;
    gap: 1rem;
}
.mybut>button{
    flex: 1;
    display: flex;
    gap: 4px;
    align-items: center;
    justify-content: center;
    padding: 7px;
    background-color: transparent;
    border: 1.3px solid rgb(57,73,171);
    color: rgb(57,73,171);
    border-radius: 16px;
}
.container>button, .container>a{
    width: 100%;
}

.myinp{
    width: 100%;
    display: flex;
    margin-top: 1.5rem;
    flex-direction: column;
}
.myinp>div{
    position: relative;
}
.myinp input{
    flex: 1;
    width: 100%;
    padding: 8px 28px;
    border-radius: 3px;
    border: 1px solid rgb(187, 187, 187);
}
.myinp img{
    position: absolute;
    left: 0;
    width: 1.2rem;
    transform: translate(4px, 6px);
}
#forimg{
    right: 5px;
    transform: translateY(7px);
    left: auto;
}
.myinp{
    display: flex;
    flex-direction: column;
    gap: 10px;
}
.container{
    padding: 6% 3%;
    width: 25%;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: space-around;
}
</style>