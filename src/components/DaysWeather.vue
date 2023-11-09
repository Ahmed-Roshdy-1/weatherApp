<template>
 
      <div class="days-tab text-center">
        <div class="loading">Loading...</div>
        <ul class="p-0">
            <li class="li_active">
                <div class="py-3">icon</div>
                <div class="py-3">day</div>
                <div class="py-3">12oc</div>
            </li>
             <li class="li_active">
                <div class="py-3">icon</div>
                <div class="py-3">day</div>
                <div class="py-3">12oc</div>
            </li>
             <li class="li_active">
                <div class="py-3">icon</div>
                <div class="py-3">day</div>
                <div class="py-3">12oc</div>
            </li>
             <li class="li_active">
                <div class="py-3">icon</div>
                <div class="py-3">day</div>
                <div class="py-3">12oc</div>
            </li>
        </ul>
      </div>
     
</template>

<script setup>

</script>

<style scoped>

.days-tab{
    width:90%;
    box-shadow:0 4px 8px #00000031, 0 6px 20px 0 #0000003f;
    border-radius: 20px;
    width: 90%;
    margin: auto;
     
}
.loading{
    color:#fff;
}
ul{
    margin: 0;
}
li{
    display: inline-block;
    list-style: none;
    height: 100%;
    width: 21%;
    background: #641919;
    font-size: 1vw;
    line-height: 1.2;
}

span{
    display: block;
    margin-bottom:5px;
    font: 100% sans-serif;
    height: 35px;
}

.li_active{
    background: #253d5c;
    color: #222833;
    border-radius: 10px;
    margin: 0.3rem;
    color: #fff;
    font-weight: 600;
}

/* .li_active{
    transform: scale(1.2);
    transition: transform 0.1s linear;
    color: #fff;
    transition: background-color 0.5s;
    border-radius: 10px;


} */
.li_active:hover{
    transform: scale(1.2);
    transition: transform 0.1s linear;
}

.li_active_temp{
    display: inline-block;
    background-color: #222833;
    color:#fff;
    transition: background-color 0.5s;
    border-radius: 10px;
}
.li_active_temp:hover{
    transform: scale(1.2);
    transition: transform 0.1s linear;
    background: #fff;
    border-radius: 10px;
    color: #191a1f;
}
</style>
