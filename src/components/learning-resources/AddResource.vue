<template>
    <base-dialog v-if="inputIsInvalid" title="invalid Input" @close="confirmError">
    <template #default>
     <p>unfortunateley,at lease one input valid is invalid.</p>
     <p>plase,check all your input and entered data in all you input</p>
    </template>
    <template #actions>
        <base-button @click="confirmError">okay</base-button>
    </template>
    </base-dialog>
    <base-card>
  <form @submit.prevent="submitData()">
    <div class="form-control">
    <label for="title">Title</label>
    <input type="text" id="title" name="title" ref="titleInput">
    </div>
    <div class="form-control">
    <label for="description">Description</label>
    <textarea name="description" id="description" cols="30" rows="3" ref="descInput"></textarea>
    </div>
    <div class="form-control">
    <label for="link">Link</label>
    <input type="url" id="link" name="link" ref="linkInput">
    </div>
    <div>
        <base-button type="submit ">Add Resource</base-button>
    </div>
  </form>
    </base-card>
</template>

<script>
export default {
  inject:['addResource'],
  data(){
    return{
        inputIsInvalid:false
    }
  },
 methods:{
 submitData(){
 const enteredTitle=this.$refs.titleInput.value;
 const enteredDescription=this.$refs.descInput.value;
 const enteredUrl=this.$refs.linkInput.value;
 if(enteredTitle === ''||enteredDescription === ''||enteredUrl === '')
 {
    this.inputIsInvalid = true;
    return;
 }
//   this.$emit(senddata,'enteredtitle,enteredDes')
this.addResource(enteredTitle,enteredDescription,enteredUrl)
 },
 confirmError(){
    this.inputIsInvalid = false
 }
 }
}
</script>

<style scoped>
label{
    font-weight:bold;
    display:block;
    margin-bottom:0.5rem;
}
input,textarea{
width:100%;
display:block;
padding:0.15rem;
border:1x solid #ccc
}
.form-control{   
    margin-bottom:16px;
}

</style>