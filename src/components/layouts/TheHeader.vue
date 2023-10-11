<template>
<header>
    <h1>{{title}}</h1>
</header>
</template>
<script>
export default{
    data(){
        return{
            title:'RememberMe'
        }
    }
}
 </script>

<style scoped>
header{
    width:100%;
    height:5rem;
    background-color: rgb(49, 2, 58);
    display:flex;
    justify-content: center;
    align-items: center;
    color:white
}
 </style>
