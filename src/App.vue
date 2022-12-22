<script setup>
import { ref } from "vue"

const newDate = ref (null)
const oldDate = ref(null)
//const showValue = ref(false)

const getDate = () => {
  let getNewDate = new Date(newDate.value)
  let getOldDate = new Date(oldDate.value)

  console.log("getNewDate>>", getNewDate)
  console.log("getOldDate>>", getOldDate)

  let getBothDate = Math.abs(getNewDate - getOldDate)
  console.log("getBothDate>>", getBothDate)

  let getDays = Math.ceil(getBothDate/(1000 * (60 * 60) *24 ))
  console.log("getDays>>", getDays)
   let getResult = getDays / 365.25
   console.log("getResult", getResult)

   document.querySelector('#old').innerHTML = `your birth date is:  ${oldDate.value}`
  document.querySelector('#new').innerHTML = `your present date is:  ${newDate.value}`
  document.querySelector('#show').innerHTML =`You are ${Math.round(getResult)} years old`

   // showValue.value = !showValue.value
   
}
</script>

<template>
  
<div>
  <div class="text-center bg-sky-900 py-3 text-3xl text-white">
    <h4 class="">Date Checker</h4>
  </div>

  <h2 class="text-center mt-10">Check Your Age</h2>

  <section class="mt-10">
    <div class="flex justify-center">
      <label for="" class="mt-[20px] mx-2">Birth year</label>
      <input type="date" class="border-2 my-4 py-1 px-3" v-model="oldDate">
    </div>

    <div class="flex justify-center mt-10">
      <label for="" class="mt-[8px] -mx-0">Present year</label>
      <input type="date" class="border-2 py-1 px-3" v-model="newDate">
    </div>

    <div>
     <button @click="getDate" class="flex mx-auto my-16 bg-sky-900 px-4 py-1 rounded-md text-white">
       check date
     </button>
    </div>
  </section>

  
  <div class="bg-indigo-300 mt-10 text-center" >
    <p id="old"></p>
    <p id="new"></p>
    <p id="show"></p>
  </div>
</div> 
</template>

<style scoped>

</style>
