<template>
  <div class="flex h-screen flex-1 flex-col justify-center px-6 py-12 lg:px-8">
    <div class="mt-10 sm:mx-auto sm:w-full sm:max-w-sm border border-gray-300 rounded-lg p-8 bg-white shadow-md  ">
      <form class="space-y-6" action="#" method="POST">
        <h2 class="text-2xl font-bold text-gray-900 mb-6 text-center">Login</h2>
        <div>
          <label for="email" class="block text-sm/6 font-medium text-gray-500">Email</label>
          <div class="mt-2">
            <input type="email" name="email" id="email" autocomplete="email" required=""
              class="block w-full rounded-md bg-white px-3 py-1.5 text-base text-gray-900 outline-1 -outline-offset-1 outline-gray-300 placeholder:text-gray-400 focus:outline-2 focus:-outline-offset-2 focus:outline-indigo-600 sm:text-sm/6" />
          </div>
        </div>

        <div>
          <div class="flex items-center justify-between">
            <label for="password" class="block text-sm/6 font-medium text-gray-500">Password</label>
            <div class="text-sm">
              <a href="#" class="font-semibold text-indigo-600 hover:text-indigo-500">Forgot password?</a>
            </div>
          </div>
          <div class="mt-2">
            <input type="password" name="password" id="password" autocomplete="current-password" required=""
              class="block w-full rounded-md bg-white px-3 py-1.5 text-base text-gray-900 outline-1 -outline-offset-1 outline-gray-300 placeholder:text-gray-400 focus:outline-2 focus:-outline-offset-2 focus:outline-indigo-600 sm:text-sm/6" />
          </div>
        </div>

        <div class="flex items-center justify-between">
          <div class="flex gap-2">
            <div class="flex h-6 shrink-0 items-center">
              <div class="group grid size-4 grid-cols-1">
                <ArrowLeftIcon class=" h-5 w-5 text-violet-900" />
              </div>
            </div>
            <NuxtLink to="/" class="cursor-pointer">
              <a class="block text-sm/6 text-violet-900">Back</a>
            </NuxtLink>
          </div>
        </div>

        <div>
          <button type="submit"
            class="flex w-full justify-center rounded-md bg-indigo-600 px-3 py-1.5 text-sm/6 font-semibold text-white shadow-xs hover:bg-indigo-500 focus-visible:outline-2 focus-visible:outline-offset-2 focus-visible:outline-indigo-600">Sign
            in</button>
        </div>
      </form>

    </div>
  </div>
</template>

<script setup>

import { ArrowLeftIcon } from '@heroicons/vue/20/solid'

</script>