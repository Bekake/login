<template>
    <div class="umumiy">
        <div class="mycontainer">
            <div class="pic">
                <img src="@/assets/torus.png" alt="Logo">
                <div class="bir">
                    <img src="@/assets/mylogo.png" alt="Logo">
                    <div>
                        <p><span>SPEC</span></p>
                        <p>PROJECTOR</p>
                    </div>
                </div>
                <div class="ikki">
                    <div class="forimg">
                        <img src="@/assets/cosmos.png" alt="Cosmos">
                    </div>
                    <div  class="mytext">
                        <p>Welcome aboard my friend</p>
                        <p>Just a couple of clicks and we start</p>
                    </div>
                    <nav>
                        <router-link to="/"><div></div></router-link>
                        <router-link to="/forget"><div></div></router-link>
                        <router-link to="/register"><div></div></router-link>
                    </nav>
                </div>
            </div>
            <router-view/>
        </div>
    </div>
</template>
<script>

</script>
<style scoped>
.pic>img{
    position: absolute;
    top: 30%;
    left: -17.5%;
}
.umumiy{
    width: 100%;
    height: 100vh;
    padding-top: 30px;
}

.mycontainer{
    display: flex;
    justify-content: center;
}
.mytext>p:first-child{
    font-size: 24px;
    text-align: center;
    font-weight: 600;
}
.mytext>p:last-child{
    font-size: 14px;
    text-align: center;
    font-weight: 400;
    margin-top: 6px;
}
nav{
    display: flex;
    gap: 10px;
    align-items: center;
}
nav div{
    width: 12px;
    height: 12px;
    background-color: rgb(0, 34,123);
    border-radius: 50%;
    cursor: pointer;
}
nav > a.router-link-exact-active > div{
    width: 1rem;
    height: 1rem;
    background-color: rgb(143, 154, 234);
    position: relative;
}
nav > a.router-link-exact-active > div::before{
    content: "";
    width: 8px;
    height: 8px;
    background-color: white;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    border-radius: 50%;
    position: absolute;
}
.ikki img{
    width: 12rem;
    z-index: 3;
    position: relative;
}
.forimg{
    position: relative;
}
.forimg::before{
    content: "";
    position: absolute;
    width: 120%;
    aspect-ratio: 1/1;
    top: -2rem;
    left: -9%;
    background-color: rgb(0, 34,123);
    border-radius: 50%;
    z-index: 1;
}
.ikki{
    height: 100%;
    display: flex;
    padding-top: 2rem;
    flex-direction: column;
    align-items: center;
    justify-content: space-around;
}
.bir>div{
    display: flex;
    flex-direction: column;
    justify-content: space-evenly
}
.bir>div>p:last-child{
    margin-top: 3px;
}
.bir>div>p>span:first-child{
    border-radius: 1.2rem;
    background-color: rgb(0,34,123);
    font-size: 0.8rem;
    top: 3px;
    padding:4px 6px;
}
.pic{
    position: relative;
    background: rgba(57, 73, 171, 1);
    padding: 3%;
    color: white;
    width: 40%;
    min-width: 524px;
    aspect-ratio: 23/22;
    border-top-left-radius: 20px;
    border-bottom-left-radius: 20px;
}
.bir.img{
    width: 3rem;
}
.bir{
    display: flex;
    gap: 10px;
}

</style>