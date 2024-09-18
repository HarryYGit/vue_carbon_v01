<template>
    <h1>Carbon Calculator</h1>
    <inputForm />
    <resultTable />
    <historyTable />
</template>

<script>
import inputForm from './form/input-form.vue';
import historyTable from './table/history-table.vue';
import resultTable from './table/result-table.vue';

    export default {
        components:{
            inputForm,
            resultTable,
            historyTable

        }
    }
</script>