<template>
<base-card>
    <base-button @click="setSelectedTab('stored-resources')" :mode="storedResButtonMode">StoredResources</base-button>
    <base-button @click="setSelectedTab('add-resource')" :mode="addResButtonMode">AddResources</base-button>
</base-card>
<keep-alive>
<component :is="selectedTab"></component>
</keep-alive>
</template>

<script>
import BaseButton from '../UI/BaseButton.vue';
import AddResource from './AddResource.vue';
import StoredResources from './StoredResources.vue';

export default{
    components:{BaseButton,StoredResources,AddResource},
    data(){
        return{
          selectedTab:'stored-resources',
          storedResources:[
           {
             id:'official-guide',
             title:'officialGuide',
             description:'the official vue.js documnetation',
             link:'https://vuejs.org'
            },
           {
             id:'google',
             title:'Google',
             description:'learn to google',
             link:'https://google.com'
            },
            {
             id:'yahoo',
             title:'Yahoo',
             description:'learn to Yahoo',
             link:'https://Yahoo.com'
            }
          ]
        }
    },
    provide(){
        return{
            resources:this.storedResources,
            addResource:this.addResource,
            deleteResource:this.deleteResource
        }
    },
    methods:{
        setSelectedTab(tab){
            this.selectedTab=tab
        },
        addResource(title,description,url){
            const newResource={
                id:new Date().toISOString(),
                title:title,
                description:description,
                link:url
            };
            this.storedResources.unshift(newResource);
            this.selectedTab='stored-resources'
        },
        deleteResource(resId){
            const resIndex=this.storedResources.findIndex(res=>res.id=resId);
            this.storedResources.splice(resIndex,1)
        }
    },
        computed:{
            storedResButtonMode(){
             return this.selectedTab==='stored-resources' ? null : 'flat';
            },
            addResButtonMode(){
                return this.selectedTab==='add-resource'? null : 'flat';
            }
        }
}
    
</script>

<style>
</style>   