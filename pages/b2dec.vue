<template>
  <v-container class="lighten-5">
    <v-row
      class="mb-6 justify-center align-center"
      no-gutters>

      <v-form
        class="d-flex flex-column align-center"
        ref="form"
        v-model="valid"
        lazy-validation
      >
        <v-text-field
          @keydown.enter.stop.prevent
          class="mb-6"
          v-model="binary"
          :rules="[rules.required, rules.regex]"
          label="Binary Number"
          counter
          maxlength="8"
          required
        ></v-text-field>
        
        <v-btn
          :disabled="!valid"
          color="success"
          class="mb-8"
          @click="convertBinToDec"
        >
          Convert
        </v-btn>

        <div class="d-flex flex-column align-center">
          <h1 class="mb-6">The Binary</h1>
            <h2 class="font-weight-bold purple darken-2 mb-6"> {{ binary }} </h2>
          <h1 class="mb-6">to Decimal</h1>
            <h2 class="font-weight-bold purple darken-2"> {{ decimal }} </h2>
        </div>

      </v-form>

    </v-row>
  </v-container>
</template>

<script>
    export default {
    data () {
      return {
        valid: true,
        binary: '01010101',
        decimal: '',
        email: '',
        rules: {
          required: value => !!value || 'Required.',
          regex: value => {
            const pattern = /^([+-]?(?=\.\d|\d)(?:\d+)?(?:\.?\d*))(?:[eE]([+-]?\d+))?[0-1]$/
            return pattern.test(value) || 'Type a binary number to proceed'
          },
        },
      }
    },
    methods: {
      convertBinToDec () {
      this.decimal = parseInt(this.binary, 2);
      }
    }
  }

</script>