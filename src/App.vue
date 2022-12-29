<template>

  <!-- <p>
    <router-link to="/">Home</router-link>
    <router-link to="/about">About</router-link>
  </p> -->
  
  <router-view></router-view>

</template>

<script>
  export default {
    name: 'show',
    data(){
      return {
        count: 0,
        students: [
          {
            id: '01',
            name: 'Shamim',
            address: 'Faridpur'
          },
          {
            id: '02',
            name: 'Nasir',
            address: 'Madaripur'
          },
          {
            id: '03',
            name: 'Mahbub',
            address: 'Rajshahi'
          }
        ]
    }
  },
  methods: {
      counted(){
        this.count++
        if(this.count > 100)
        {
          this.count = "Congratulations!"
        }
      }
    }
}

</script>

