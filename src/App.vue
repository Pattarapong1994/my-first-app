<script setup>
import { reactive } from 'vue'



const genderList = ['ชาย', 'หญิง', 'ไม่ระบุ']
const interestList = ['หนังสือ', 'กีฬา', 'การเมือง', 'เกม']

const formData = reactive({
  interests:[]
})

const submitForm= () => {
  console.log('SUBMIT COMPLETED');
  console.log(formData);
}

</script>

<template>
  <div>
    <div>
      <div>Firstname</div>
      <input type="text" name="firstname" v-model="formData.firstname">
    </div>
    <div>
      <div>Lastname</div>
      <input type="text" name="lastname" v-model="formData.lastname">
    </div>
    <div>Gender</div>
    <div v-for="gender in genderList">
      <input type="radio" name="gender" :value="gender" v-model="formData.gender"> {{ gender }}
    </div>
    <div>Interests</div>
    <div v-for="interests in interestList" >
      <input type="checkbox" name="interests" :value="interests" v-model="formData.interests"> {{ interests }}
    </div>

    <div>
      <div>Description</div>
      <textarea v-model="formData.description"></textarea>
    </div>
    <button @click="submitForm()">Submit Form</button>
  </div>
</template>