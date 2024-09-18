<template>
    <div class="card">
      <div class="card-header pb-0">
        <h3>Carbon Emission Calculator</h3>
      </div>

      <!-- Inputs for Calculation -->
      <form class="form theme-form">
        <div class="card-body">
          <div class="row">
            <div class="col">

            <!-- Distance  -->
              <div class="mb-3 row">
                <label class="col-sm-3 col-form-label">Distance</label>
                <div class="col-sm-9">
                  <input class="form-control digits" type="number" placeholder="Input Distance">
                </div>
              </div>

              <!-- MPG  -->
              <div class="mb-3 row">
                <label class="col-sm-3 col-form-label">MPG</label>
                <div class="col-sm-9">
                  <input class="form-control digits" type="number" placeholder="Input MPG">
                </div>
              </div>

              <!-- AFEC  -->
              <div class="mb-3 row">
                <label class="col-sm-3 col-form-label">AFEC</label>
                <div class="col-sm-9">
                  <input class="form-control digits" type="number" placeholder="Input AFEC">
                </div>
              </div>

              <!-- Emission Factor  -->
              <div class="mb-3 row">
                <label class="col-sm-3 col-form-label">Emission Factor</label>
                <div class="col-sm-9">
                  <input class="form-control digits" type="number" placeholder="Input Emission Factor">
                </div>
              </div>


            </div>
          </div>
        </div>
        <div class="card-footer text-end">
          <div class="col-sm-9 offset-sm-3">
            <button class="btn btn-primary m-r-10" type="submit">Calculate</button>
            <input class="btn btn-light" type="reset" value="Cancel">
            <button class="btn btn-primary m-r-10" type="submit">History</button>
          </div>
        </div>
      </form>
    </div>
  </template>