<template>
  <forms @submit="submitForm">
   <div> 
     <label for="name">Name </label>
     <input type="text" id="name" placeholder="your name" v-model="formValues.name">
   </div>

   <div>
     <label for="profile">Profile Summary</label>
     <textarea id="profile" />
   </div>
   <div>
     <label for="country">Country</label>
     <select id="country" row="3" col="3" v-model="formValues.country">
       <option value="">Select a country</option>
       <option value="india">India</option>
       <option value="america">USA</option>
       <option value="ussr">Russia</option>
       <option value="UK">England</option>
     </select>
   </div>

   <div>
     <label for="job-location">Job Location</label>
     <select id="job-location" multiple v-model="formValues.jobLocation">
       <option value="germany">Germany</option>
       <option value="india">India</option>
       <option value="america">USA</option>
       <option value="ussr">Russia</option>
       <option value="UK">England</option>
     </select>
   </div>
   <div>
     <input type="checkbox" id="remoteWork" v-model="formValues.remoteWork" true-value='yes' false-value='no' />
     <label for="remoteWork">Open to Remote Work ?</label>
   </div>
   <div>
     <label>Skill Set</label>
     <input type="checkbox" id="html" value="html" v-model="formValues.skillSet"/>
     <label for="html">HTML</label>
     <input type="checkbox" id="css" value="css" v-model="formValues.skillSet"/>
     <label for="css">CSS</label>
     <input type="checkbox" id="javascript" value="javascript" v-model="formValues.skillSet"/>
     <label for="javscript">JAVASCRIPT</label>
   </div>
   <div>
     <label>Years of Experience</label>
     <input type="radio" id="0-2" value="0-2" v-model="formValues.yearsOfExp"/>
     <label for="0-2">0-2</label>
     <input type="radio" id="0-3" value="0-3" v-model="formValues.yearsOfExp"/>
     <label for="0-3">0-3</label>
     <input type="radio" id="" value="3 or above" v-model="formValues.yearsOfExp"/>
     <label for="3 or above">3 or above</label>
   </div>

   <button>Submit</button>
  </forms>

</template>

<script>
export default {
 name: 'HelloWorld',
 props: {
   msg: String
 },
 data() {
   return {
     formValues: {
       name: '',
       profileSummary: '',
       country: '',
       jobLocation: [],
       remoteWork: false,
       skillSet:[],
       yearsOfExp:''
     }
   }
 },
 methods:{
   submitForm(event) {
     event.preventDefault()
     console.log('Form values', this.formValues)
   }
 }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
label  {
 font-weight: bold;
 display:flex;
 margin-bottom: 10px;
 margin-top: 10px;
}
input + label{
 display: inline-flex;
 margin-right: 20px;
}
input[type='text'],
textarea,
select{
 display: block;
}
</style>
