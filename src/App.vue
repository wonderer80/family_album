<template lang="html">
  <div class="container-fluid">
    <tbody>
      <div class="row">
        <div v-for="family in families">
          <Family v-bind:family="family"></Family>
        </div>
      </div>
    </tbody>
  </div>
</template>

<script>
import Family from './components/Family.vue'
import Papa from 'papaparse';

export default {
  data() {
    var families = [];

    Papa.parse('/src/assets/list.csv', {
      download:true, delimiter: ",",
      complete: function(results, file) {

         for(var i=0; i < results.data.length;i++) {
           var family = results.data[i];
           var filename;
           var names = [];

           if( family[0] != '') {
             filename = family[0];
           } else {
             filename = 'nothing'
           }

           for(var j=1; j < family.length; j++) {
             if(family[j]!='') {
               names.push(family[j]);
             }
           }
           family = { photo: './src/assets/' + filename + '.jpg', names: names };
           families.push(family);
         }
       },
     });

    return {
      families: families
    }
  },



  components: {
      'Family': Family,
    }
}
</script>

<style lang="css">
</style>
