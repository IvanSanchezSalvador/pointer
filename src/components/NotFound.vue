<template>
  <div class="h-screen flex flex-col justify-center">
    <h1 class="flex justify-center items-center">
      <img src="/static/ellipsis.svg" class="mr-2 h-8" />
      <span class="text-3xl text-black font-normal">404</span>
    </h1>

    <router-link to="/" tag="button" class="mt-8 btn btn-blue self-center no-underline">start a new session</router-link>

    <form class="mt-8 self-center flex">
      <input type="text" id="room" class="login-input w-48 rounded-r-none" v-model="id" placeholder="session-id">
      <router-link v-if="id && id.trim().length > 0" :to="{ name: 'SessionPage', params: { id: id.trim() } }" tag="button" class="btn btn-blue no-underline rounded-l-none">join</router-link>
      <button v-else class="btn btn-blue opacity-50 hover:bg-blue-500 cursor-not-allowed rounded-l-none" disabled>join</button>
    </form>
  </div>
</template>

<script>
import UserItem from './UserItem'

export default {
  components: {
    UserItem
  },
  data () {
    return {
      id: ''
    }
  }
}
</script>
