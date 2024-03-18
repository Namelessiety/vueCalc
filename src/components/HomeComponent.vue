<template>
  <Teleport to="body"
    ><div>
      <div class="flex justify-center">
        <input
          type="text"
          disabled
          v-model="Calc"
          class="border border-green-600 text-black w-[95vw] rounded-md p-5 text-4xl mt-7"
        />
      </div>
      <div class="grid grid-cols-4 gap-2 mt-10 mx-3 lg:mx-10">
        <button
          @click="addSth(btnValue[0])"
          class="border border-green-600 bg-green-400 text-white rounded-md p-4 text-4xl"
        >
          {{ btnValue[0] }}
        </button>
        <button
          @click="addSth(btnValue[1])"
          class="border border-green-600 bg-green-400 text-white rounded-md p-4 text-4xl"
        >
          {{ btnValue[1] }}
        </button>
        <button
          @click="addSth(btnValue[2])"
          class="border border-green-600 bg-green-400 text-white rounded-md p-4 text-4xl"
        >
          {{ btnValue[2] }}
        </button>
        <button
          @click="addSth(btnValue[3])"
          class="border border-green-600 bg-green-400 text-white rounded-md p-4 text-4xl"
        >
          {{ btnValue[3] }}
        </button>
        <button
          @click="addSth(btnValue[4])"
          class="border border-green-600 bg-green-400 text-white rounded-md p-4 text-4xl"
        >
          {{ btnValue[4] }}
        </button>
        <button
          @click="addSth(btnValue[5])"
          class="border border-green-600 bg-green-400 text-white rounded-md p-4 text-4xl"
        >
          {{ btnValue[5] }}
        </button>
        <button
          @click="addSth(btnValue[6])"
          class="border border-green-600 bg-green-400 text-white rounded-md p-4 text-4xl"
        >
          {{ btnValue[6] }}
        </button>
        <button
          @click="addSth(btnValue[7])"
          class="border border-green-600 bg-green-400 text-white rounded-md p-4 text-4xl"
        >
          {{ btnValue[7] }}
        </button>
        <button
          @click="addSth(btnValue[8])"
          class="border border-green-600 bg-green-400 text-white rounded-md p-4 text-4xl"
        >
          {{ btnValue[8] }}
        </button>
        <button
          @click="addSth(btnValue[9])"
          class="border border-green-600 bg-green-400 text-white rounded-md p-4 text-4xl"
        >
          {{ btnValue[9] }}
        </button>
        <button
          @click="addSth(btnValue[10])"
          class="border border-yellow-600 bg-yellow-400 text-white rounded-md p-4 text-4xl"
        >
          {{ btnValue[10] }}
        </button>
        <button
          @click="addSth(btnValue[11])"
          class="border border-yellow-600 bg-yellow-400 text-white rounded-md p-4 text-4xl"
        >
          {{ btnValue[11] }}
        </button>
        <button
          @click="addSth(btnValue[12])"
          class="border border-yellow-600 bg-yellow-400 text-white rounded-md p-4 text-4xl"
        >
          {{ btnValue[12] }}
        </button>
        <button
          @click="addSth(btnValue[13])"
          class="border border-yellow-600 bg-yellow-400 text-white rounded-md p-4 text-4xl"
        >
          {{ btnValue[13] }}
        </button>
        <button
          @click="addSth(btnValue[14])"
          class="border border-yellow-600 bg-yellow-400 text-white rounded-md p-4 text-4xl"
        >
          {{ btnValue[14] }}
        </button>
        <button
          @click="calculate"
          :disabled="Calc === ''"
          class="border border-blue-600 bg-blue-400 text-white rounded-md p-4 text-4xl"
        >
          =
        </button>
        <button
          @click="rmSth"
          class="border border-red-600 bg-red-600 text-white rounded-md p-4 text-4xl"
        >
          del
        </button>
        <button
          @click="rmAll"
          class="border border-red-600 bg-red-600 text-white rounded-md p-4 text-4xl"
        >
          AC
        </button>
      </div>
    </div>
  </Teleport>
</template>
<script setup>
import { ref } from 'vue'

let result = ''
let Calc = ref('')
let btnValue = ref(['1', '2', '3', '4', '5', '6', '7', '8', '9', '0', '/', '*', '-', '+', '.'])
let addSth = function (value) {
  const isLastOperate = /[-+*./%]$/.test(Calc.value)
  if ((isLastOperate && /[-+*./%]$/.test(value)) || (Calc.value === '' && /[+*./]$/.test(value))) {
    return
  } else {
    Calc.value += value
  }
}

let rmLast = Calc.value.slice(0, -1)
let calculate = () => {
  result = eval(Calc.value)
  Calc.value = result
}
let rmSth = () => {
  Calc.value = rmLast
}

let rmAll = () => {
  Calc.value = ''
}
</script>
