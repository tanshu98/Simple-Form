<template>
  <v-container>
    <v-form>
      <div class="text-center">
        <v-row class="mb-6">
          <v-col cols="10">
            <v-text-field v-model="name" label="Name" outlined></v-text-field>
          </v-col>
          <v-col cols="2" class="d-flex">
            <v-btn class="mx-2" fab dark color="primary">
              <v-icon dark> mdi-minus </v-icon>
            </v-btn>
            <v-btn class="mr-2" fab dark color="indigo">
              <v-icon dark> mdi-plus </v-icon>
            </v-btn>
          </v-col>
        </v-row>
        {{name}}
        <v-row>
          <v-btn
            class="ma-2"
            color="secondary"
          >
            Submit
          </v-btn>
          <v-btn
            color="blue-grey"
            class="ma-2 white--text"
          >
            Clear
          </v-btn>
        </v-row>
      </div>
    </v-form>
  </v-container>
</template>
<script>
export default {
  data() {
    return {
      name: ""
    }
  },
};
</script>