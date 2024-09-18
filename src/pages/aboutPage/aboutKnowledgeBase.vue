<template>
    <div>
  
      <!-- modify page title -->
      <Breadcrumbs main="app" :title="setTitle"/>
  
      <div class="container-fluid knowledgebase-page">
        <div class="row">
          <div class="col-12">

          </div>
          <AboutArticlesView />
          <AboutPageFeatures />

          

  
        </div>
      </div>
    </div>
  </template>
    
  <script>
  import { mapState } from 'vuex';
  import pxcard from '../../components/Pxcard.vue'
  import AboutPageFeatures from './aboutPageFeatures/index.vue'
  import AboutArticlesView from './aboutPageArticleViews/aboutArticlesView.vue';

  export default {
  
    // Get receive page title from parent comp
    props:{
      setTitle: String
    },
    components: {
      'px-card': pxcard, AboutArticlesView, AboutPageFeatures, 
    },
    data() {
      return {};
    },
    computed: {
      ...mapState({
        knowledgebasedata: (state) => state.common.knowledgebasedata,
      }),
    },
  };
  </script>
    
  <style>
  .search-form.search-knowledge .form-group {
    position: relative;
  }
  
  .search-form.search-knowledge .form-group:after {
    position: absolute;
    content: "\F002";
    font-family: FontAwesome;
    top: 10px;
    left: 30px;
  }
  </style>