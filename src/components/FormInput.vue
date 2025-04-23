<template>
  <div class="inputGroup">
    <input
      :type="type"
      v-model="inputValue"
      @input="$emit('update:modelValue', $event.target.value)"
      :id="id"
      required
      placeholder=" "
      class="inputField"
    />
    <label :for="id" class="inputLabel">
      <p class="labelText">
        {{ inputLabel }}
      </p>
    </label>
  </div>
</template>

<script setup>
import { defineProps } from "vue";
defineProps({
  modelValue: String,
  inputLabel: String,
  id: String,
  type: {
    type: String,
    default: "text",
  },
});
</script>

<style scoped>
.inputGroup {
  position: relative;
  height: 40.32px;
  margin-bottom: 30.96px;
  width: 100%;
}

.inputField {
  height: 100%;
  width: 100%;
  box-sizing: border-box;
  border: 0.72px solid #555552;
  border-radius: 3.6px;
  font-size: 16px;
  background-color: transparent;
  outline: none;
  margin-bottom: 31px;

  padding-left: 19.41px;

  font-family: "ABeeZee";
  font-style: normal;
  font-weight: 400;
  font-size: 15px;
  line-height: 18px;

  color: #555552;
}

.inputLabel {
  position: absolute;
  display: flex;
  flex-direction: row;
  justify-content: center;
  align-items: center;
  padding: 1.2636px 6.318px 0px;
  gap: 6.32px;

  position: absolute;
  width: fit-content;
  height: 17.27px;
  top: -8.5px;
  left: 13.41px;

  background: white;
}

.labelText {
  height: 14px;

  font-family: "ABeeZee";
  font-style: normal;
  font-weight: 400;
  font-size: 12px;
  line-height: 14px;

  color: #006315;
}
</style>
