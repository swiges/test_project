<template>
  <div :class=" ['box', 'bold', error ? 'red' : 'green'].join(' ') ">
    <button @click="runTestEnvironment">Run</button>
  </div>
</template>

<script>
export default {
  name: 'IndexPage',
  data() {
    return {
      error: false,
      classes: ['box', 'bold']
    }
  },
  methods: {
    async runTestEnvironment() {
      // let arr1 = [{ id: '1'}, { id: '2'}, { id: '3', name: 'Car', color: 'red'}, { id: '4'}, { id: '5'}, { id: '6'}]
      //
      // let value = arr1.find(el => {
      //   return el.id === '3'


      // })
      // console.log(value)
      // console.log(value.name)
      // console.log(value.color)



      // let string = '6, 5, 4, 3, 2, 1'
      // let arr = string.split(', ').reverse().join(', ')
      // console.log(arr)

      // let classes = ['green', 'box', 'bold']



      // arr1.forEach((value, index) => {
      //
      //   if(typeof value === 'number'){
      //     arr1[index] = value + 2 // !<==
      //     console.log(value)
      //   }

        // arr1[index] = !<==

      // })

      // console.log(arr1)

    }
  }
}
</script>

<style scoped>
.green {
  background-color: green;
}

.red {
  background-color: red;
}

.box {
  height: 200px;
  width: 200px;
}

.bold {
  border: 10px solid #004600;
}
</style>
