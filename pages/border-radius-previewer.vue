<template>
  <v-container class=" " >
    <div class="flexRowReverse mb-6">
      <div v-bind:style="defaultStyle"></div>

      <div>
        <v-alert text outlined type="info" >Try to change the following values</v-alert>
        <v-text-field
          v-model="defaultStyle.borderBottomLeftRadius"
          label="Border Bottom Left Radius"
        ></v-text-field>
        <v-text-field
          v-model="defaultStyle.borderBottomRightRadius"
          label="Border Bottom Right Radius"
        ></v-text-field>
        <v-text-field
          v-model="defaultStyle.borderTopLeftRadius"
          label="Border Top Left Radius"
        ></v-text-field>
        <v-text-field
          v-model="defaultStyle.borderTopRightRadius"
          label="Border top Right Radius"
        ></v-text-field>
      </div>
    </div>
    <v-alert
      color="white"
      light
      prominent
      icon="mdi-xml"
      class="alertStyle"
    >
    <div class="ml-4">
      <p >{{'border-top-left-radius: ' + defaultStyle.borderTopLeftRadius}}</p>
      <p>{{'border-top-right-radius: ' + defaultStyle.borderTopRightRadius}}</p>
      <p>{{'border-bottom-left-radius: ' + defaultStyle.borderBottomLeftRadius}}</p>
      <p>{{'border-bottom-right-radius: ' + defaultStyle.borderBottomRightRadius}}</p>
    </div>
    </v-alert>
  </v-container>
  
</template>

<script>

export default {
    components: {  },
    data () {
      return {
        first: '',
        defaultStyle: {
          color: 'red',
          backgroundColor: 'red',
          fontSize: '30px',
          height: '350px',
          width: '350px',
          borderTopLeftRadius: '0px',
          borderTopRightRadius: '0px',
          borderBottomLeftRadius: '0px',
          borderBottomRightRadius: '0px',
        }
      }
    }
}
</script>

<style scoped>
 .flexRowReverse{
    display: flex;
    flex-wrap: nowrap;
    flex-direction: row-reverse;
    justify-content: space-around;
 }
 .alertStyle{
  width: 60%;
  margin-left: 200px;
 }

</style>