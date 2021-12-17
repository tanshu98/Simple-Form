<template>
  <v-container>
    <v-form
     ref="form"
    v-model="valid"
    lazy-validation
    >
      <div class="text-center">
        <v-row class="mb-6">
          <v-col cols="10">
            <div v-for="(namelist,counter) in namelist"
      v-bind:key="counter">
            <v-text-field v-model="namelist.name" label="Name"
             :counter="10"
            :rules="nameRules"
            outlined>
            </v-text-field>
            </div>
          </v-col>
          <v-col cols="2" class="d-flex">
            <v-btn class="mx-2" fab dark color="primary"
             @click="add"
             >
              <v-icon dark> mdi-plus </v-icon>
            </v-btn>
            <v-btn class="mr-2" fab dark color="indigo"
             @click="remove">
              <v-icon dark> mdi-minus </v-icon>
            </v-btn>
          </v-col>
        </v-row>
        <v-row>
          <v-btn
            :disabled="!valid"
            class="ma-2"
            color="success"
            @click="submit"
          >
            Submit
          </v-btn>
          <v-btn
            color="purple lighten-1"
            class="ma-2 white--text"
             @click="clear"
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
  name: "Form",
  props: {
    msg: String
  },
  data() {
    return {
      valid: true,
      name:"",
      namelist: [],
      nameRules: [
        v => !!v || 'Name is required',
        v => (v && v.length <= 10) || 'Name must be less than 10 characters',
      ],
    }
  },
  methods: {
      submit() {
        console.log(this.namelist);
      },
//       clear() {
//         this.$refs.form.clear()
//       },
//     add() {
//         this.namelist.push()
//         console.log(this.namelist.push());
//     },
//     remove() {
//     this.namelist.pop()
//     console.log(this.namelist.splice());
// }
    add(){
    this.namelist.push({
    name: ""
    })
    },
    remove(counter){
        this.namelist.splice(counter,1);
    },
    clear(){
         this.namelist.name= "";
    }
    // this.name.pop()
    },
};
</script> */}