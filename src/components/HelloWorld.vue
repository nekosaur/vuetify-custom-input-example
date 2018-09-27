<template>
  <v-app>
    <v-content>
      <v-container>
        <v-layout column wrap>
          <v-form v-model="valid">
            <custom-input label="Custom input" v-model="value" :rules="rules"></custom-input>
          </v-form>
          <h3>Form is {{ valid ? 'valid' : 'not valid' }}</h3>
        </v-layout>
      </v-container>
    </v-content>
  </v-app>
</template>

<script>
import CustomInput from './CustomInput'

export default {
  name: 'HelloWorld',
  components: {
    CustomInput
  },
  data: () => ({
    valid: false,
    value: '0',
    rules: [v => Number(v) >= 0 || 'Value is less than zero!']
  })
}
</script>
