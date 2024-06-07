<script setup lang="ts">
const login = false
const props = defineProps({
  variation: {
    type: String,
    required: true
  }
})
</script>

<template>
  <nav v-if="variation == 'h'" class="fixed z-10 grid grid-cols-6 w-full h-auto p-2 items-center justify-center">
    <section class="">
    </section>

    <section class="flex justify-center items-center col-start-3 col-span-2 space-x-4 lg:space-x-6">
      <ULink to="/" class="text-2xl font-bold" active-class="text-primary"
        inactive-class="text-gray-500 dark:text-gray-400 hover:text-gray-700 dark:hover:text-gray-200">
        Home
      </ULink>
      <ULink to="/about" class="text-2xl font-bold" active-class="text-primary"
        inactive-class="text-gray-500 dark:text-gray-400 hover:text-gray-700 dark:hover:text-gray-200">
        About
      </ULink>
      <ULink to="/experience" class="text-2xl font-bold" active-class="text-primary"
        inactive-class="text-gray-500 dark:text-gray-400 hover:text-gray-700 dark:hover:text-gray-200">
        Experience
      </ULink>
      <ULink to="/programs" class="text-2xl font-bold" active-class="text-primary"
        inactive-class="text-gray-500 dark:text-gray-400 hover:text-gray-700 dark:hover:text-gray-200">
        Programs
      </ULink>
      <ULink to="/apply" class="text-2xl font-bold" active-class="text-primary"
        inactive-class="text-gray-500 dark:text-gray-400 hover:text-gray-700 dark:hover:text-gray-200">
        Apply
      </ULink>
    </section>

    <section class="flex">
      <UButton v-if="!login" size="lg" to="/auth" class="mt-auto mb-auto">Login</UButton>
      <UButton v-if="login" :padded="false" :ui="{ rounded: 'rounded-full' }" color="white">
        <UAvatar size="lg" src="https://avatars.githubusercontent.com/u/739984?v=4" alt="Avatar">
        </UAvatar>
      </UButton>
    </section>
  </nav>

  <!--Admin side Navbar-->

  <nav v-if="variation == 'v'" class="w-24 h-screen p-5 flex justify-center items-center">
    <section class="flex flex-col space-y-10 py-6 w-full h-full">
      <div class="flex items-center justify-center rounded-md bg-white p-4 text-blue-600">
        <ULink to="/profile" active-class="text-primary" inactive-class="text-gray-500 hover:text-gray-400">
          <LucideGraduationCap />
        </ULink>
      </div>

      <div class="w-full h-full flex flex-col bg-white p-4 rounded-md">
        <ul class="space-y-9">
          <li>
            <ULink to="/profile/assignments" active-class="text-primary"
              inactive-class="text-gray-500 hover:text-gray-400">
              <LucideNotebookPen />
            </ULink>
          </li>
          <li>
            <ULink to="/profile/videos" active-class="text-primary" inactive-class="text-gray-500 hover:text-gray-400">
              <LucideMonitorPlay />
            </ULink>
          </li>
          <li>
            <ULink to="/profile/calendar" active-class="text-primary"
              inactive-class="text-gray-500 hover:text-gray-400">
              <LucideCalendarDays />
            </ULink>
          </li>
          <li>
            <ULink to="/profile/chat" active-class="text-primary" inactive-class="text-gray-500 hover:text-gray-400">
              <LucideMessageCircle />
            </ULink>
          </li>
          <li>
            <ULink to="/profile/account" active-class="text-primary" inactive-class="text-gray-500 hover:text-gray-400">
              <LucideCircleUserRound />
            </ULink>
          </li>
        </ul>
        <div class="mt-auto mb-0">
          <UButton :padded="false" color="transparent">
            <LucideLogOut class="text-gray-500 hover:text-red-500" />
          </UButton>
        </div>
      </div>
    </section>
  </nav>
</template>
