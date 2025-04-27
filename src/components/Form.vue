<script setup>
import { Field, useForm, ErrorMessage } from 'vee-validate'
import * as yup from 'yup'
import InputText from '../components/InputText.vue'
import { ref } from 'vue'

const schema = {
  gender: (value) => {
    if (value) {
      return true
    }

    return 'Gender is required'
  },
}

const { handleSubmit, resetForm } = useForm({
  validationSchema: yup.object({
    firstName: yup.string().required('First Name is required').min(1),
    lastName: yup.string().required('Last Name is required').min(2),
    email: yup.string().required('Email is required').email(),
    phone: yup.string().required('Phone Number is required').min(10),
    gender: yup.string().required('Gender is required').notOneOf([''], 'Gender is required'),
    birthday: yup.string().required('Birthday is required').notOneOf([''], 'Birthday is required'),
    dateTime: yup
      .string()
      .required('Appointment time is required')
      .notOneOf([''], 'Appointment time is required'),
    insurance: yup
      .string()
      .required('Insurance is required')
      .notOneOf([''], 'Insurance is required'),
    annualVisit: yup
      .string()
      .required('Annual Visit is required')
      .notOneOf([''], 'Annual Visit is required'),
  }),
})
const formSuccess = ref(false)
const onSubmit = handleSubmit((values) => {
  formSuccess.value = true
  resetForm()
})
</script>

<template>
  <!-- Form Container-->
  <div class="formData">
    <div class="formDataContainer">
      <p class="booktingTitle">Book an appointment for free</p>
      <p class="bookingSubTitle">
        The office partners with Baylor Scott & White Health to schedule appointments
      </p>

      <form :validation-schema="schema" @submit="onSubmit">
        <div class="topInputs">
          <!-- First Name -->
          <div class="firstName topSectionInputs">
            <label class="lableTitle" for="fname">First Name</label>
            <InputText name="firstName" />
          </div>

          <!-- Last Name -->
          <div class="lastName topSectionInputs">
            <label class="lableTitle" for="lname">Last Name</label>
            <InputText name="lastName" />
          </div>

          <!-- Phone Number -->
          <div class="phoneNumber topSectionInputs">
            <label class="lableTitle" for="phone">Phone Number</label>
            <InputText name="phone" />
          </div>

          <!-- Email -->
          <div class="emailInput topSectionInputs">
            <label class="lableTitle" for="email">Email</label>
            <InputText name="email" type="email" />
          </div>

          <!-- Gender -->
          <div class="sexOption topSectionInputs">
            <div class="sexOptionBttn sexTitle">
              <label>Gender:</label>
            </div>
            <div class="sexOptionBttn">
              <Field type="radio" name="gender" value="Male" class="sexRadioBttns" />
              <label>Male</label>
            </div>
            <div class="sexOptionBttn">
              <Field type="radio" name="gender" value="Female" class="sexRadioBttns" />
              <label>Female</label>
            </div>
          </div>
          <div class="genderErrorContainer">
            <ErrorMessage name="gender" class="errorMess" />
          </div>

          <!-- Birthday -->
          <div class="birthdayContainer topSectionInputs">
            <label>Birthday:</label>
            <Field name="birthday" id="birthday" type="date" rules="required|valid_date" />
            <ErrorMessage name="birthday" class="errorMess" />
          </div>

          <!-- Appointment Time-->
          <div class="topSectionInputs">
            <label class="lableTitle">Choose a time for your appointment:</label>
            <Field type="datetime-local" id="meeting-time" name="dateTime" />
            <ErrorMessage name="dateTime" class="errorMess" />
          </div>

          <!-- Reason for visit-->
          <div class="topSectionInputs">
            <label class="lableTitle">Reason for visit</label>
            <Field as="select" name="annualVisit" id="annualVisit">
              <option value="" disabled selected>Please Select</option>
              <option value="volvo">Annual visit</option>
              <option value="saab">Follow up</option>
              <option value="opel">New patient</option>
              <option value="audi">Tele Medicine</option>
              <option value="other">Other</option>
            </Field>
            <ErrorMessage name="annualVisit" class="errorMess" />
          </div>

          <!-- Insurance -->
          <div class="topSectionInputs">
            <label class="lableTitle">Insurance</label>
            <Field as="select" name="insurance">
              <option value="" disabled selected>Please Select</option>
              <option value="UH">United Healthcare</option>
              <option value="bcbs">Blue Cross Blue Shield</option>
              <option value="humana">Humana Insurance</option>
              <option value="aetna">Aetna</option>
              <option value="other">Other</option>
            </Field>
            <ErrorMessage name="insurance" class="errorMess" />
          </div>
        </div>

        <button id="submitBttn">Submit</button>
        <div class="formSuccessMessage" v-if="formSuccess">
          <p style="text-align: center; color: green; font-size: 20px; margin: 0">
            Your appointment has been scheduled!
          </p>
        </div>
      </form>
    </div>
  </div>
</template>

<style>
.input-field[data-v-48a640b5] {
  color: red;
}
.formData {
  background: #fafafa;
  padding: 20px;
}

p.booktingTitle {
  font-size: 23pt;
  text-align: left;
  margin: 15px 15px 0;
}

p.bookingSubTitle {
  margin: 10px 15px 50px;
  color: #666;
}

form {
  width: 100%;
}

.topInputs {
  display: flex;
  flex-wrap: wrap;
  width: 100%;
}

.topSectionInputs {
  width: 45%;
  margin: 15px;
}

.topSectionInputs input,
select {
  width: 100%;
  height: 40px;
  margin: 5px 0 0 0;
}

.firstName.topSectionInputs div input[type='text'],
.lastName.topSectionInputs div input[type='text'],
.phoneNumber.topSectionInputs div input[type='text'],
.emailInput.topSectionInputs div input[type='email'],
input#phone,
input#fname,
input#lname,
input#email,
textarea#AddnlInfo,
input#birthday,
input#meeting-time {
  padding: 0px 0 0 10px;
  border: 1px solid rgba(58, 47, 31, 0.1);
  border-radius: 3px;
  color: #666;
}

.sexContainer {
  width: 96%;
  margin: 15px 15px 15px 18px;
}

select {
  padding: 0px 0 0 10px;
  border: 1px solid rgba(58, 47, 31, 0.1);
  border-radius: 3px;
  color: rgba(102, 102, 102, 0.5);
}

input[type='text'],
textarea {
  background: #fff !important;
}

::placeholder,
option {
  color: #666;
  opacity: 0.5; /* Firefox */
}

.sexRadioBttns {
  width: 16px !important;
}

.sexOption {
  display: flex;
  width: 50%;
}

.sexOptionBttn {
  width: 30%;
  align-items: center;
  display: flex;
}

.sexRadioBttns {
  width: 16px !important;
}

.sexOptionBttn label {
  margin: 5px 0 0 5px;
}

.sexTitle {
  width: 25%;
}

.birthdayContainer {
  width: 44.9%;
  margin-bottom: 14px;
}

.AddnlInfoContainer {
  width: 95%;
}

.AddnlInfoContainerTitle {
  width: 95%;
  margin: 26px 0 0 0;
}

textarea#AddnlInfo {
  width: 100%;
  margin: 15px;
  /* min-height: 100px; */
  min-width: 100%;
  resize: none;
}

label {
  color: #666;
  font-family: arial;
  font-size: 11pt;
}

label#addnlContainerTitle {
  margin: 0 0 0 17px;
}

button#submitBttn {
  background: #2080c6;
  color: #fff;
  font-size: 14pt;
  padding: 10px 50px;
  border: none;
  border: 1px solid rgba(58, 47, 31, 0.1);
  border-radius: 3px;
  margin: 50px 15px;
  cursor: pointer;
}

.errorMess {
  color: red;
  font-family: arial;
  font-size: 11pt;
}

.genderErrorContainer {
  width: 100%;
  margin: -23px 0 0 13px;
}

@media screen and (max-width: 1024px) {
  .topSectionInputs {
    width: 100%;
  }

  .ratingDetails {
    padding-left: 10px;
  }
}

/* 456 screen size */

@media screen and (max-width: 456px) {
  .sexTitle {
    width: 30%;
  }

  .formBox {
    grid-template-columns: 1fr !important;
  }
}
</style>
