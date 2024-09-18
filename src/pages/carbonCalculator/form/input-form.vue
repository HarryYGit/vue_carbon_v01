<template>
    <div class="card">
      <div class="card-header pb-0">
        <h3>Carbon Emission Calculator</h3>
      </div>

      <!-- Inputs for Calculation -->
      <form @submit.prevent="calculateEmissions" class="form theme-form">
        <div class="card-body">
          <div class="row">
            <div class="col">

            <!-- Distance  -->
              <div class="mb-3 row">
                <label class="col-sm-3 col-form-label">Distance</label>
                <div class="col-sm-9">
                  <input v-model="form.distance" class="form-control digits" type="number"  placeholder="Input Distance" required >
                </div>
              </div>

              <!-- MPG  -->
              <div class="mb-3 row">
                <label class="col-sm-3 col-form-label">MPG</label>
                <div class="col-sm-9">
                  <input v-model="form.mpg" class="form-control digits" type="number" placeholder="Input MPG" required>
                </div>
              </div>

              <!-- AFEC  -->
              <div class="mb-3 row">
                <label class="col-sm-3 col-form-label">AFEC</label>
                <div class="col-sm-9">
                  <input v-model="form.afec" class="form-control digits" type="number" placeholder="Input AFEC" required>
                </div>
              </div>

              <!-- Emission Factor  -->
              <div class="mb-3 row">
                <label class="col-sm-3 col-form-label">Emission Factor</label>
                <div class="col-sm-9">
                  <input v-model="form.emission_factor" class="form-control digits" type="number" placeholder="Input Emission Factor" step="0.01" required>
                </div>
              </div>


            </div>
          </div>
        </div>
        <div class="card-footer text-end">
          <div class="col-sm-9 offset-sm-3">
            <button class="btn btn-primary m-r-10" type="submit">Calculate</button>
            <input class="btn btn-light" type="reset" value="Cancel">
            <button @click="fetchHistory" class="btn btn-primary m-r-10" type="submit">History</button>
          </div>
        </div>
      </form>


    </div>

    <resultTable :result="result.result" :form="form" />
    <historyTable :history="history" />
    

  </template>

  <script>

  import resultTable from '../table/result-table.vue';
  import historyTable from '../table/history-table.vue';

        export default {
            data(){
                return{
                    form: {
                        distance: '',
                        mpg: '',
                        afec: '',
                        emission_factor: 8.89
                    },

                    result: 0,
                    history: []

                }
            },
            methods:{

                async calculateEmissions() {

                    try {
                        const response = await this.axios.post(`http://127.0.0.1:8000/api/tasks/`, this.form);
                        this.result = response.data;
                    } catch (error) {
                        console.error(error);
                    }
                },

                async fetchHistory(){

                    try {

                    const response = await this.axios.get(`http://127.0.0.1:8000/api/tasks/`);
                    this.history = response.data;

                    } catch (error) {
                    console.log("fetch history error: ", error);
                    
                    }

                }
            },
            components: {
                resultTable,
                historyTable
            }
        }

  </script>