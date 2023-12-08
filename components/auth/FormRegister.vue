<script setup lang="ts">
  import { ref } from "vue"  
  //import AppBtn from "@/components/AppBtn.vue"
  //import AppInput from "@/components/AppInput.vue"  
  //import AppFlashMessage from "@/components/AppFlashMessage.vue"  

  defineProps({
    error: [Object, String],
    sending: Boolean
  })  
  const emit = defineEmits(['submit'])   
  const name = ref(undefined)
  const email = ref(undefined)
  const password = ref(undefined)
  const passwordConfirm = ref(undefined)
  const submit = async () => {
    emit('submit', {
      name: name.value,
      email: email.value,
      password: password.value,
      passwordConfirm: passwordConfirm.value
    })
  }
</script>

<template>
  <form @submit.prevent="submit">  
    <UInput
      type="text"
      label="Nombre completo"
      name="name"
      v-model="name"
      placeholder="Full name"
      class="mb-2"
      data-testid="name-input"
    />
    <UInput
      type="email"
      label="Correo"
      name="email"
      v-model="email"
      placeholder="email@domain.ext"
      class="mb-2"
      data-testid="email-input"
    />
    <UInput
      type="password"
      label="Clave"
      name="password"
      v-model="password"
      placeholder="Password"
      class="mb-2"
      data-testid="password-input"
    />
    <UInput
      type="password"
      label="Confirmar clave"
      name="password-confirm"
      v-model="passwordConfirm"
      placeholder="Confirm password"
      class="mb-4"
      data-testid="confirm-password-input"
    />    
    
    <UButton
        type="submit"
        :isDisabled='sending'
        data-testid="submit-btn"
      >{{ sending ? 'Registrándose...' : 'Registrarse' }}</UButton>
    
    <!--AppFlashMessage :error="error" /-->
  </form>
</template>

