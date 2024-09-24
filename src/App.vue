<script setup>
import { reactive } from "vue";
const genderList = ["ชาย", "หญิง", "ไม่ระบุ"];
const interestList = [
  "เทคโนโลยี",
  "การเงิน",
  "การศึกษา",
  "สุขภาพ",
  "การท่องเที่ยว",
];

const formData = reactive({
  interests: [],
});

const submitForm = () => {
  console.log(formData);
};
</script>

<template>
  <div>
    <div>
      <div>Firstname</div>
      <input type="text" name="firstname" v-model="formData.firstname" />
    </div>

    <div>
      <div>Lastname</div>
      <input type="text" name="lastname" v-model="formData.lastname" />
    </div>

    <div>
      <div>Gender</div>
      <div v-for="gender in genderList" :key="gender">
        <input
          type="radio"
          name="gender"
          :value="gender"
          v-model="formData.gender"
        />{{ gender }}
      </div>
    </div>

    <div>
      <div>Interest</div>
      <div v-for="interest in interestList" :key="interest">
        <input
          type="checkbox"
          name="interest"
          :value="interest"
          v-model="formData.interests"
        />{{ interest }}
      </div>
    </div>

    <div>
      <div>Description</div>
      <textarea
        type="text"
        name="description"
        v-model="formData.description"
      ></textarea>
    </div>

    <button @click="submitForm()">Submit</button>
  </div>
</template>
