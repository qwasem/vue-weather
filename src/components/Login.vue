<script lang="ts" setup>
import axios from "axios";
import {ref} from "vue";

    // const count = ref(0)
const username = ref("")
const password = ref("")
const is_login = ref(false);
const login = () => {

  const query1 = "http://" + "www.alihaddadi.sadrazkh.ir" + ":" + '8001' + "/auth/jwt/create"
  axios
      .post(query1,
          {
            username: username.value,
            password: password.value
          }).then((res) => {is_login.value = true})
}


</script>

<template>
  <div class="min-h-full flex items-center justify-center py-12 px-4 sm:px-6 lg:px-8">
    <div class="max-w-md w-full space-y-8">
      <div>
        <img
            alt="Workflow"
            class="mx-auto h-12 w-auto"
            src="https://tailwindui.com/img/logos/workflow-mark-indigo-600.svg"
        />
        <h2 class="mt-6 text-center text-3xl font-extrabold text-gray-900">
          Login to your account
        </h2>
        <p class="mt-2 text-center text-sm text-gray-600">
          Or
          <router-link
              class="font-medium text-indigo-600 hover:text-indigo-500"
              to="/signup"
          >
            Sign up here.
          </router-link>
        </p>
      </div>
      <input name="remember" type="hidden" value="true"/>
      <div class="rounded-md shadow-sm -space-y-px">
        <div>
          <label class="sr-only" for="email-address">username</label>
          <input
              id="email-address"
              v-model="username"
              autocomplete="email"
              class="appearance-none rounded-none relative block w-full px-3 py-4 border border-gray-300 placeholder-gray-500 text-gray-900 rounded-t-md focus:outline-none focus:ring-indigo-500 focus:border-indigo-500 focus:z-10 sm:text-sm"
              name="username"
              placeholder="username"
              required
              type="username"
          />
        </div>
        <div>
          <label class="sr-only" for="password">Password</label>
          <input
              id="password"
              v-model="password"
              autocomplete="current-password"
              class="appearance-none rounded-none relative block w-full px-3 py-4 border border-gray-300 placeholder-gray-500 text-gray-900 rounded-b-md focus:outline-none focus:ring-indigo-500 focus:border-indigo-500 focus:z-10 sm:text-sm"
              name="password"
              placeholder="Password"
              required
              type="password"
          />
        </div>
      </div>

      <div class="flex items-center justify-between">
        <div class="flex items-center">
          <input
              id="remember-me"
              checked
              class="h-4 w-4 text-indigo-600 focus:ring-indigo-500 border-gray-300 rounded"
              name="remember-me"
              type="checkbox"
          />
          <label class="ml-2 block text-sm text-gray-900" for="remember-me">
            Remember me
          </label>
        </div>

        <div class="text-sm">
        </div>
      </div>

      <div>
        <button
            class="group relative w-full flex justify-center py-3 px-6 border border-transparent font-medium rounded-md shadow-sm text-white bg-indigo-600 hover:bg-indigo-700 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-indigo-500"
            type="submit"
            @click="login"
        >
          Login
        </button>
      </div>
    </div>
  </div>
</template>

<style scoped></style>
