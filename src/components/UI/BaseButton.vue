<template>
<button  :class="mode" >
    <slot></slot>
</button>
</template>

<script>
export default{
    props:['mode'],
    data(){
    return{
        isshow:true,
    }
}
}
</script>

<style scoped>
button{
    background-color: rgb(73, 8, 73);
    color:white;
    /* border-radius: 5px; */
    padding:5px;
    border:1px solid rgb(73, 8, 73);
    width:120px
}
button:hover{
    background-color: blueviolet;
    border:1px solid blueviolet
}
.flat{
    border:none;
    background-color: transparent;
    color:black
}
</style>