<template>
    <div class="col-sm-12">
      <div class="card">
        <div class="card-header">
          <h3>Calculation History</h3>
        </div>
        
        <div class="card-block row">
          <div class="col-sm-12 col-lg-12 col-xl-12">
            
            <div class="table-responsive">
              
              <table class="table table-light">
                <thead>
                  <tr>

                    <!-- <th scope="col">Id</th> -->
                    <th scope="col">Distance</th>
                    <th scope="col">MPG</th>
                    <th scope="col">AFEC</th>
                    <th scope="col">Emission Factor</th>
                    <th scope="col">Result</th>

                  </tr>
                </thead>
                <tbody>
                  <tr v-for="(item, id) in history" :key="id">
                    <!-- <th scope="row">{{ item.id }}</th> -->

                    <td>{{ item.distance }} </td>
                    <td>{{ item.mpg }}</td>
                    <td>{{ item.afec }}</td>
                    <td>{{ item.emission_factor }} </td>

                    <td>{{ item.result }} 

                      <!-- Delete Button -->
                      <div class="card-footer text-end">
                        <div class="col-sm-9 offset-sm-3">
                          <button @click="deleteHistory(item)" class="btn btn-primary m-r-10" type="submit">Delete</button>
                        </div>
                      </div> 
                    </td>

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

  import { mapState } from 'vuex';

  export default {

    data(){
      return {

      }
    },

    methods: {

      // DELETE delete history by id from server
      async deleteHistory(item){

        const confirmDelete = confirm("Confirm Delete?");

        if(confirmDelete){
          try {

            await this.$http.delete(`http://127.0.0.1:8000/api/tasks/${item.id}/`)

            // re-fetch History after DELETE
            this.refreshHistory();

            console.log("update history")
            
          }catch(error){
            console.log(error);
        }
          
        }
      
      }

    },

    props:{
      history:{
        type: Array
      },

      refreshHistory:{
        type: Function
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