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

                    <th scope="col">Id</th>
                    <th scope="col">Distance</th>
                    <th scope="col">MPG</th>
                    <th scope="col">AFEC</th>
                    <th scope="col">Emission Factor</th>
                    <th scope="col">Result</th>

                  </tr>
                </thead>
                <tbody>
                  <tr v-for="(item, index) in Responsive" :key="index">
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
  import { mapState } from 'vuex';
  export default {
    computed: {
      ...mapState({
        sizing: state => state.bootsrap.sizingTablesXl,
        Responsive: state => state.bootsrap.Responsive,
      })
    },
  }
  </script>