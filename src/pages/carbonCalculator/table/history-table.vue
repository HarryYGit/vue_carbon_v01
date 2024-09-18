<template>
    <div class="col-sm-12">
      <div class="card">
        <div class="card-header">
          <h3>Calculation History</h3>
        </div>
        
        <div class="card-block row">
          <div class="col-sm-12 col-lg-12 col-xl-12">
            <div class="table-responsive">
              <button @click="fetchHistory" class="btn btn-primary m-r-10" type="submit">History</button>
              <table class="table table-light">
                <thead>
                  <tr>

                    <th scope="col">Id</th>
                    <th scope="col">Distance</th>
                    <th scope="col">MPG</th>
                    <th scope="col">AFEC</th>
                    <th scope="col">Emission Factor</th>
                    <th scope="col">Result</th>

                  </tr>
                </thead>
                <tbody>
                  <tr v-for="(item, id) in history" :key="id">
                    <th scope="row">{{ item.id }}</th>

                    <td>{{ item.distance }} </td>
                    <td>{{ item.mpg }}</td>
                    <td>{{ item.afec }}</td>
                    <td>{{ item.emission_factor }} </td>
                    <td>{{ item.result }}</td>

                  </tr>
                </tbody>
              </table>
            </div>
          </div>
        </div>
      </div>
    </div>

  </template>



  <script>

  import VueAxios from 'vue-axios';
  import { mapState } from 'vuex';

 


  export default {

    

    data(){
      return {

        history: []

      }
    },

    methods: {
      async fetchHistory(){

        try {

          const response = await this.axios.get(`http://127.0.0.1:8000/api/tasks/`);
          this.history = response.data;

        } catch (error) {
          console.log("fetch history error: ", error);
          
        }

      }
    },


   



    computed: {
      ...mapState({
        sizing: state => state.bootsrap.sizingTablesXl,
        Responsive: state => state.bootsrap.Responsive,
      })
    },
  }

  </script>