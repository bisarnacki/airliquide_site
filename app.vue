// App.vue
<template>
  <div>
    <AppHeader :user="user" @logout="logOut" @login="logIn" />
    <HomePage :user="user" />
  </div>
</template>

<script>
import { getUser } from './api'

export default {
  data () {
    return {
      user: {}
    }
  },
  methods: {
   logOut () {
     this.user = null
   },
   logIn () {
     this.user = await getUser()
   }
  } 
}
</script>


/* Router-view
<template>
  <div>
    <AppHeader :user="user" @logout="logOut" @login="logIn" />
    <router-view :user="user" />
  </div> */
</template>
