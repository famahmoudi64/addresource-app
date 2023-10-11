<template>
    <li> 
    <base-card>
        <header>
            <h3>{{ title }}</h3>
            <base-button mode="flat" @click="deleteResource(id)">Delete</base-button>
        </header>
    <h3>{{ description }}</h3>
    <nav>
        <a :href="link">View Resource</a>
    </nav>
   
</base-card>
  </li>
</template>

<script>

export default {
    props: ["id","title", "description", "link"],
    inject:['deleteResource'],
    data() {
        return {};
    },
   
}
</script>

<style scoped>
li{
    margin:auto;
    max-width:40rem
}
header{
    display:flex;
    justify-content: space-between;
    align-items: center;
}
a:active,a:hover{
    color:#c89300;
}
a{
    text-decoration: none;
}
p{
    margin:0.5rem 0;
    color:#ce5c00
}
h3{
    font-size: 1.25rem;
    margin:0.5rem 0
}

</style>