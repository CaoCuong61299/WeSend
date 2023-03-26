<script setup lang="ts">
const beforePhone = ref('+972')
const afterPhone = ref('0000000000')
const password = ref('admin')
const rememberMe = ref(false)
const isLogin = ref<boolean>(true)

const router = useRouter()

function submit() {
  isLogin.value = !isLogin.value
}

function changeRouter() {
  router.push('/sign-up')
}
</script>

<template>
  <div class="layout-bg" />
  <div
    v-if="isLogin"
    class="layout-login"
  >
    <VRow
      no-gutters
      align-content="center"
      justify="center"
      class="login-title-logo"
    >
      <span><strong>We</strong>Send</span>
    </VRow>
    <VRow
      no-gutters
      align-content="center"
      justify="center"
      class="login-content"
    >
      <div class="content-block">
        <div class="block-header">
          <strong>Sign In</strong>
        </div>
        <div class="block-title">
          <div class="block-title-text">
            Enter your phone number to Sign in
          </div>
          <div class="block-title-text">
            to your account
          </div>
        </div>
        <div class="block-input">
          <div class="input-before">
            <VTextField
              v-model="beforePhone"
              type="text"
              bg-color="#F3F4FB"
            />
          </div>
          <div class="input-after">
            <VTextField
              v-model="afterPhone"
              type="text"
              bg-color="#F3F4FB"
            />
          </div>
          <div class="input-submit">
            <VBtn
              class="submit-btn"
              min-height="48"
              width="93"
              color="#111827"
              rounded="5"
              @click="submit"
            >
              Sign in
            </VBtn>
          </div>
        </div>
        <div class="block-confirm">
          <VCheckbox />
          <span class="confirm-text">Keep me Sign in</span>
        </div>
      </div>
    </VRow>
    <VRow
      no-gutters
      align-content="center"
      justify="center"
      class="login-sign-up"
    >
      <span>New to WeSend. <span
        class="sign-up-line"
        @click="changeRouter"
      >Sign up</span></span>
    </VRow>
    <VRow
      no-gutters
      align-content="center"
      justify="center"
      class="login-footer"
    >
      <div
        class="footer-tilte"
      >
        <span>Contact Us | Privacy Policy | Terms & Conditions</span>
      </div>
      <div
        class="footer-tilte"
      >
        <span>© 2022 We Send. All Rights Reserved.</span>
      </div>
    </VRow>
  </div>
  <div
    v-else
    class="layout-login verify"
  >
    <VRow
      no-gutters
      align-content="center"
      justify="center"
      class="login-title-logo"
    >
      <span><strong>We</strong>Send</span>
    </VRow>
    <VRow
      no-gutters
      align-content="center"
      justify="center"
      class="login-content"
    >
      <div class="content-block">
        <div class="block-header">
          <strong>Verify</strong>
        </div>
        <div class="block-title">
          <div class="block-title-text">
            Please enter the code send on your
          </div>
          <div class="block-title-text">
            phone for verification
          </div>
        </div>
        <div class="block-input">
          <div>
            <AppOtpInput
              :total-input="4"
              default="0000"
            />
          </div>
        </div>
        <div class="block-verify">
          <VBtn
            class="verify-btn"
            min-height="48"
            width="122"
            color="#111827"
            rounded="rounded-pill"
            @click="submit"
          >
            Verify
          </VBtn>
        </div>
        <div class="block-resend">
          <span>Didn’t received the code. Resend (20s)</span>
        </div>
      </div>
    </VRow>
    <VRow
      no-gutters
      align-content="center"
      justify="center"
      class="login-sign-up"
    >
      <span>New to WeSend. <span
        class="sign-up-line"
        @click="changeRouter"
      >Sign up</span></span>
    </VRow>
    <VRow
      no-gutters
      align-content="center"
      justify="center"
      class="login-footer"
    >
      <div
        class="footer-tilte"
      >
        <span>Contact Us | Privacy Policy | Terms & Conditions</span>
      </div>
      <div
        class="footer-tilte"
      >
        <span>© 2022 We Send. All Rights Reserved.</span>
      </div>
    </VRow>
  </div>
</template>

<style lang="scss">
@use "@core/scss/template/pages/page-auth.scss";
</style>

<route lang="yaml">
meta:
  layout: blank
  action: read
  subject: Auth
  redirectIfLoggedIn: true
</route>
