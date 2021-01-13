<template>
<v-container>
    
  <v-form v-model="valid">
    
      <v-row class="mt-30">
        <v-col cols="12" md="4">
           <v-text-field class="mt-5"
            label="First name"
            placeholder="Placeholder"
            outlined
          ></v-text-field>
        </v-col>

        <v-col cols="12" md="4">
          <v-text-field
            label="Last name"
           placeholder="Placeholder"
            outlined 
          ></v-text-field>
        </v-col>
      </v-row>

     <v-row>
          <v-flex xs8 class="mt-5">
          <v-text-field
          label="Email"
          placeholder="Placeholder"
            outlined 
        ></v-text-field>
      </v-flex>
     </v-row>

     <v-row>
          <v-flex xs6 class="mt-5">
          <v-text-field 
          label="Password"
          placeholder="Placeholder"
            outlined 
        ></v-text-field>
      </v-flex>
     </v-row>
     <v-row class="mt-30"
    align="center"
    justify="space-around" 
  >
  <v-flex xs4 class="ml-10">
  
   <v-btn color="pink"
    depressed
      
      
    >
      Sign Up
    </v-btn>
  
  </v-flex>
  <v-flex xs4 class="ml-10">
    
    <v-btn class="ml-9"
      depressed
      
    >
      Login
    </v-btn>
   
  </v-flex>
     </v-row>
    
  </v-form>
</v-container>
</template>

<script>
export default {};
</script>
<style lang="scss" scoped>

</style>
 