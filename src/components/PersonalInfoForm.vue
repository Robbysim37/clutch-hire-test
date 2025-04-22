<template>
  <div class="formContainer">
    <form class="form" @submit.prevent="submitForm">
      <div class="callToActionContainer">
        <div class="callToAction">Have us reach out</div>
      </div>
      <FormInput
        inputLabel="First Name"
        id="firstName"
        v-model="formData.first"
      />
      <FormInput inputLabel="Last Name" id="lastName" v-model="formData.last" />
      <FormInput inputLabel="Email" id="email" v-model="formData.email" />
      <FormInput
        inputLabel="Phone Number"
        id="phone"
        v-model="formData.phone"
      />
      <FormInput inputLabel="Company" id="company" v-model="formData.company" />
      <div class="continueButtonContainer">
        <button class="continueButton" type="submit">
          <p class="continue">Continue</p>
        </button>
      </div>
    </form>
  </div>
</template>

<script setup>
import { reactive } from "vue";
import FormInput from "./FormInput.vue";
const formData = reactive({
  first: "",
  last: "",
  company: "",
  phone: "",
  email: "",
});

const submitForm = async () => {
  try {
    const response = await fetch(
      "https://dev-api-api.hiring-test.experientialpreview.com/api/lead/4d5e5046-c634-4f6c-9ff0-a235ad0d4a35",
      {
        method: "POST",
        headers: {
          "Content-Type": "application/json",
        },
        body: JSON.stringify(formData),
      }
    );

    if (!response.ok) {
      throw new Error(`Server error: ${response.status}`);
    }

    const result = await response.json();
    console.log("Success:", result);
  } catch (error) {
    console.error("Submission failed:", error);
  }
};
</script>

<style scoped>
.formContainer {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
}
.callToActionContainer {
  width: 100%;
  display: flex;
  justify-content: flex-start;
}
.continueButtonContainer {
  width: 100%;
  display: flex;
  justify-content: flex-end;
}
.form {
  width: 310px;
}
.callToAction {
  font-family: "Roboto", sans-serif;
  font-style: normal;
  font-weight: 400;
  font-size: 25px;
  line-height: 29px;
  margin-top: 138px;
  margin-bottom: 25.95px;

  color: #555552;
}
.continueButton {
  display: flex;
  align-items: center;
  justify-content: center;
  width: 131px;
  height: 34.83px;
  background: #0b476c;
  border-radius: 4px;
  border-width: 0px;
  margin-top: 20.61px;
}
.continue {
  width: 56px;
  height: 16px;

  font-family: "ABeeZee";
  font-style: normal;
  font-weight: 400;
  font-size: 13.4499px;
  line-height: 16px;

  color: #ffffff;
}
</style>
