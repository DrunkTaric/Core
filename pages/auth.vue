<script setup lang="ts">
const items = [
  {
    slot: "signin",
    label: "SignIn"
  },
  {
    slot: "signup",
    label: "SignUp"
  }]
const signinForm = reactive({ email: "", password: "" })
const signupForm = reactive({ referral: "", email: "", password: "" })

function onSubmitSignin() {
}

function onSubmitSignup() {
}
</script>

<template>
  <section class="w-full h-full flex justify-center items-center">
    <UTabs :items="items" class="w-[70rem]">
      <template #signin="{ item }">
        <UCard @submit.prevent="onSubmitSignin">
          <template #header>
            <p class="text-base font-semibold leading-6 text-gray-400 dark:text-white">
              {{ item.label }}
            </p>
          </template>

          <UFormGroup label="Email" name="email" class="mb-3">
            <UInput v-model="signinForm.email" />
          </UFormGroup>
          <UFormGroup label="Password" name="username">
            <UInput v-model="signinForm.password" type="password" />
          </UFormGroup>

          <template #footer>
            <UButton type="submit" color="black">
              Login
            </UButton>
          </template>
        </UCard>
      </template>

      <template #signup="{ item }">
        <UCard @submit.prevent="onSubmitSignup">
          <template #header>
            <p class="text-base font-semibold leading-6 text-gray-400 dark:text-white">
              {{ item.label }}
            </p>
          </template>

          <UFormGroup label="Email" name="email" class="mb-3">
            <UInput v-model="signupForm.email" />
          </UFormGroup>
          <UFormGroup label="Password" name="password" class="mb-3">
            <UInput v-model="signupForm.password" type="password" />
          </UFormGroup>

          <UFormGroup label="Referral Code" name="referral">
            <UInput v-model="signupForm.referral" />
          </UFormGroup>

          <template #footer>
            <UButton type="submit" color="black">
              Register
            </UButton>
          </template>
        </UCard>
      </template>
    </UTabs>
  </section>
</template>
