<template>
  <div class="container p-5">
    <b-row align-h="center">
      <b-col md="7">
        <!-- title with green Divider -->
        <b-row align-h="center" class="mb-5">
          <b-col lg="11" md="12" sm="7" xs="1">
            <div class="p-0 position-relative">
              <h1 style="font-family: Poppins; font-weight: 700; font-size: 36pt;">
                Sign Up
              </h1>
              <b-row>
                <b-col xs="1" sm="6" md="4" lg="5" class="mx-5">
                  <div style="height: 10px; background: #19E995;" />
                </b-col>
              </b-row>
            </div>
          </b-col>
        </b-row>
        <!-- google signup button -->
        <div class="mt-4 mb-5">
          <b-button variant="light" pill class="shadow pl-4 pr-4">
            <img src="@/assets/img/google-icon.png" alt="google icon">
            <span class="mx-2" style="color: #A3BEC9;">
              sign up with google
            </span>
          </b-button>
        </div>
        <Divider>
          OR
        </Divider>
        <Form ref="formInline" :model="formInline" :rules="ruleInline">
          <FormItem label="Name" prop="username">
            <Input v-model="formInline.username" type="text" size="large" placeholder="Elon Musk" />
          </FormItem>
          <FormItem label="E-mail Address" prop="email">
            <Input v-model="formInline.email" size="large" placeholder="elonmusk@gmail.com" />
          </FormItem>
          <FormItem label="Password" prop="password">
            <Input v-model="formInline.password" type="password" size="large" placeholder="Password" />
          </FormItem>
          <FormItem>
            <Button class="custom-btn mt-2" long shape="circle" @click="handleSubmit('formInline')">
              <span class="text-white" style="font-family: Roboto; font-weight: bold; font-size: 15pt;">
                Sign Up
              </span>
            </Button>
          </FormItem>
        </Form>
        <span>
          Already have account?
        </span>
        <a>
          <strong>
            <u style="color: #0CA1F6">
              LogIn
            </u>
          </strong>
        </a>
      </b-col>
    </b-row>
  </div>
</template>

<script>
export default {
  data () {
    return {
      formInline: {
        username: '',
        email: '',
        password: ''
      },
      ruleInline: {
        username: [{
          required: false,
          message: 'Please fill in the user name',
          trigger: 'blur'
        }],
        email: [
          { required: false, message: 'Mailbox cannot be empty', trigger: 'blur' },
          { type: 'email', message: 'Incorrect email format', trigger: 'blur' }
        ],
        password: [{
          required: false,
          message: 'Please fill in the password.',
          trigger: 'blur'
        },
        {
          type: 'string',
          min: 6,
          message: 'The password length cannot be less than 6 bits',
          trigger: 'blur'
        }]
      }
    }
  },
  methods: {
    handleSubmit (name) {
      this.$refs[name].validate((valid) => {
        if (valid) {
          this.$Message.success('Success!')
        } else {
          this.$Message.error('Fail!')
        }
      })
    }
  }
}

</script>

<style lang="css" scoped>
  /* css here */
</style>
