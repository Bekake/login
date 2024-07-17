<template>
    <pic/>
</template>
<script>
import pic from '@/components/pic.vue'
export default{
    components: {pic},
}
</script>
<style>
*{
    padding: 0;
    margin: 0;
    box-sizing: border-box;
}
@media (max-width: 1300px){
    .forhr{
        display: none;
    }
}


.container{
    box-shadow: 0 0 3px rgb(77, 76, 177);
    border-top-right-radius: 20px;
    border-bottom-right-radius: 20px;
    min-width: 327px;
}
.fade-leave-active {
    animation: leaving 0.4s;
}
.fade-enter-active {
    animation: entering 0.4s;
}
@keyframes leaving {
    0% {
        transform: rotateY(0deg);
    }
    100% {
        transform: rotateY(90deg)
    }
}
@keyframes entering {
    0% {
        transform: rotateY(90deg);
    }
    100% {
        transform: rotateY(0);
    }
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
}
nav a.router-link-exact-active {
  color: #42b983;
}
</style>
