<template>
  <div style="background: #ececec; padding: 30px">
    <a-card title="Your Profile" bordered style="width: 85vw">
      <h1> General Settings</h1>
      <a-form :model="form" :label-width="100" label-position="top">
        <a-form-item label="Name">
          <a-input v-model=form.name :default-value=form.name />
        </a-form-item>
        <a-form-item label="Email">
          <a-input v-model="form.email" :default-value=form.email />
        </a-form-item>
        <a-form-item label="Phone">
          <a-input v-model="form.phone"/>
        </a-form-item>
        <a-form-item label="Address">
          <a-input v-model="form.address"/>
        </a-form-item>
        <a-form-item label="City">
          <a-input v-model="form.city"/>
        </a-form-item>
        <a-form-item label="State">
          <a-input v-model="form.state"/>
        </a-form-item>
        <a-form-item label="Zip">
          <a-input v-model="form.zip"/>
        </a-form-item>
        <a-form-item label="Country">
          <a-input v-model="form.country"/>
        </a-form-item>
        <a-form-item label="Website">
          <a-input v-model="form.website"/>
        </a-form-item>
      </a-form>
    </a-card>
  </div>
</template>

<script>
import {defineComponent} from 'vue';

export default defineComponent({
  name: 'ProfileView',
  setup() {
    return {
      form: {
        name: 'Viktor Welbers',
        email: 'default.mail@gmail.com',
        password: '',
        confirmPassword: '',
        phone: '',
        address: '',
        city: '',
        state: '',
        zip: '',
        country: '',
        website: '',
      },
    };
  },
});
</script>