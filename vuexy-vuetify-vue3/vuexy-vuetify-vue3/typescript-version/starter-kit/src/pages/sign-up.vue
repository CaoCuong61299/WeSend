<script setup lang="ts">
const step = ref<number>(1)
const firstName = ref<string>('Roger')
const lastName = ref<string>('Kadama')
const email = ref<string>('John')
const phone = ref<string>('John')
const isVerify = ref<boolean>(false)
const credit = ref<string>('XXXX XXXX XXXX XXXX')
const card = ref<string>('John')
const expiry = ref<string>('MM/YYYY')
const cvv = ref<string>('XXX')

const router = useRouter()

function changeStep(index: number) {
  step.value = index
}

function showVerify() {
  isVerify.value = true
}

function changeRouter() {
  router.push('/login')
}
</script>

<template>
  <div class="layout-bg" />
  <div
    class="layout-sign-up"
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
      align-content="center"
      justify="center"
      class="login-content"
    >
      <div class="flex">
        <div
          class="step"
          :class="{ 'step-active': step === 1, 'step-complelte': step > 1 }"
        >
          <div
            v-if="step > 1"
            class="icon-check-white-small"
          />
          <span v-else>1</span>
        </div>
        <div class="divider">
          <div class="divider-line" />
        </div>
        <div
          class="step"
          :class="{ 'step-active': step === 2, 'step-complelte': step > 2 }"
        >
          <div
            v-if="step > 2"
            class="icon-check-white-small"
          />
          <span v-else>2</span>
        </div>
        <div class="divider">
          <div class="divider-line" />
        </div>
        <div
          class="step"
          :class="{ 'step-active': step === 3, 'step-complelte': step > 3 }"
        >
          <div
            v-if="step > 3"
            class="icon-check-white-small"
          />
          <span v-else>3</span>
        </div>
      </div>
    </VRow>
    <VRow
      v-if="step === 1"
      align-content="center"
      justify="center"
      class="login-content-step-1"
    >
      <div class="content-block">
        <div class="block-header">
          <strong>Select your package and Sign Up</strong>
        </div>
        <div class="block-content">
          <div class="block-content-1 m-r-30">
            <div class="block-content-title">
              Bronze
            </div>
            <div class="block-content-money">
              $12.99
            </div>
            <div class="block-content-item m-t-16">
              <div class="icon-check-small m-r-4" />Lorem ipsum dolar sit efelsd
            </div>
            <div class="block-content-item">
              <div class="icon-check-small m-r-4" />Lorem ipsum dola
            </div>
            <div class="block-content-item">
              <div class="icon-check-small m-r-4" />Lorem ipsum dolar sit ef
            </div>
            <div class="block-content-item">
              <div class="icon-check-small m-r-4" />Lorem ipsum do
            </div>
            <div class="block-content-item">
              <div class="icon-check-small m-r-4" />Lorem ipsum dolar sit ef
            </div>
            <div>
              <VBtn
                class="submit-btn"
                min-height="48"
                width="227"
                color="#111827"
                rounded="5"
                @click="changeStep(2)"
              >
                Chose
              </VBtn>
            </div>
          </div>
          <div class="block-content-2 m-r-30">
            <div class="block-content-title">
              Premium
            </div>
            <div class="block-content-money">
              $12.99
            </div>
            <div class="block-content-item m-t-16">
              <div class="icon-check-small m-r-4" />Lorem ipsum dolar sit efelsd
            </div>
            <div class="block-content-item">
              <div class="icon-check-small m-r-4" />Lorem ipsum dola
            </div>
            <div class="block-content-item">
              <div class="icon-check-small m-r-4" />Lorem ipsum dolar sit ef
            </div>
            <div class="block-content-item">
              <div class="icon-check-small m-r-4" />Lorem ipsum do
            </div>
            <div class="block-content-item">
              <div class="icon-check-small m-r-4" />Lorem ipsum dolar sit ef
            </div>
            <div>
              <VBtn
                class="submit-btn"
                min-height="48"
                width="227"
                color="#111827"
                rounded="5"
                @click="changeStep(2)"
              >
                Chose
              </VBtn>
            </div>
          </div>
          <div class="block-content-1">
            <div class="block-content-title">
              Expert
            </div>
            <div class="block-content-money">
              $12.99
            </div>
            <div class="block-content-item m-t-16">
              <div class="icon-check-small m-r-4" />Lorem ipsum dolar sit efelsd
            </div>
            <div class="block-content-item">
              <div class="icon-check-small m-r-4" />Lorem ipsum dola
            </div>
            <div class="block-content-item">
              <div class="icon-check-small m-r-4" />Lorem ipsum dolar sit ef
            </div>
            <div class="block-content-item">
              <div class="icon-check-small m-r-4" />Lorem ipsum do
            </div>
            <div class="block-content-item">
              <div class="icon-check-small m-r-4" />Lorem ipsum dolar sit ef
            </div>
            <div>
              <VBtn
                class="submit-btn"
                min-height="48"
                width="227"
                color="#111827"
                rounded="5"
                @click="changeStep(2)"
              >
                Chose
              </VBtn>
            </div>
          </div>
        </div>
      </div>
    </VRow>
    <VRow
      v-if="step === 2"
      align-content="center"
      justify="center"
      class="login-content-step-2"
    >
      <div
        v-if="!isVerify"
        class="content-block"
      >
        <div class="block-header">
          <strong>Add your details</strong>
        </div>
        <div
          class="block-content"
        >
          <div class="flex">
            <div class="m-r-10">
              <div class="w-600 s-16">
                First name
              </div>
              <VTextField
                v-model="firstName"
                class="input-name m-t-8"
                type="text"
                bg-color="#F3F4FB"
              />
            </div>
            <div>
              <div class="w-600 s-16">
                Last name
              </div>
              <VTextField
                v-model="lastName"
                class="input-name m-t-8"
                type="text"
                bg-color="#F3F4FB"
              />
            </div>
          </div>
          <div class="m-t-20">
            <div class="w-600 s-16">
              Email
            </div>
            <VTextField
              v-model="email"
              class="input-text m-t-8"
              type="text"
              bg-color="#F3F4FB"
            />
          </div>
          <div class="m-t-20">
            <div class="w-600 s-16">
              Phone
            </div>
            <VTextField
              v-model="phone"
              class="input-text m-t-8"
              type="text"
              bg-color="#F3F4FB"
            />
          </div>
          <div class="block-content-submit">
            <VBtn
              class="submit-btn"
              min-height="48"
              width="131"
              color="#111827"
              rounded="50"
              @click="showVerify"
            >
              Sign up
            </VBtn>
          </div>
        </div>
      </div>
      <div
        v-else
        class="content-verify-block"
      >
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
            @click="changeStep(3)"
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
      v-if="step === 3"
      align-content="center"
      justify="center"
      class="login-content-step-3"
    >
      <div
        class="content-block"
      >
        <div class="block-header">
          <strong>Payment Details</strong>
        </div>
        <div class="block-content">
          <div class="m-t-20">
            <div class="w-600 s-16">
              Credit Card Number
            </div>
            <VTextField
              v-model="credit"
              class="input-text m-t-8"
              type="text"
              bg-color="#F3F4FB"
            />
          </div>
          <div class="m-t-20">
            <div class="w-600 s-16">
              Name on Card
            </div>
            <VTextField
              v-model="card
              "
              class="input-text m-t-8"
              type="text"
              bg-color="#F3F4FB"
            />
          </div>
          <div class="flex m-t-20">
            <div class="m-r-10">
              <div class="w-600 s-16">
                Expiry Date
              </div>
              <VTextField
                v-model="expiry"
                class="input-name m-t-8"
                type="text"
                bg-color="#F3F4FB"
              />
            </div>
            <div>
              <div class="w-600 s-16">
                CVV
              </div>
              <VTextField
                v-model="cvv"
                class="input-name m-t-8"
                type="text"
                bg-color="#F3F4FB"
              />
            </div>
          </div>
          <div class="block-confirm">
            <VCheckbox class="m-r-4" />
            <span class="confirm-text">By signing up I agree to <span class="text-privacy">Terms & Condtions</span> and
              <span class="text-privacy">Privacy policy</span></span>
          </div>
          <div class="block-verify">
            <VBtn
              class="verify-btn"
              min-height="48"
              width="122"
              color="#111827"
              rounded="rounded-pill"
              @click="changeStep(1)"
            >
              Continue
            </VBtn>
          </div>
        </div>
      </div>
    </VRow>
    <VRow
      v-if="step !== 3"
      no-gutters
      align-content="center"
      justify="center"
      class="login-sign-up"
    >
      <span>Already a member. <span
        class="sign-up-line"
        @click="changeRouter"
      >Sign in</span></span>
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
@use "@core/scss/template/pages/sign-up.scss";
</style>

<route lang="yaml">
meta:
  layout: blank
  action: read
  subject: Auth
  redirectIfLoggedIn: true
</route>
