<template>
    <div class="col-lg-12">
        <div class="header-faq">
            <h5 class="mb-0">Featured Tutorials</h5>
        </div>
        <div class="row">
            <div class="col-xl-3 xl-50 col-md-6 box-col-6">
                <px-card :actions="false" class="features-faq product-box">
                    <template v-slot:headerCustom>
                        <div class="faq-image product-img">
                            <img class="img-fluid" src="../aboutPageData/img/01.webp" alt="" />
                            <div class="product-hover">
                                <ul>
                                    <li><i class="icon-link"></i></li>
                                    <li><i class="icon-import"></i></li>
                                </ul>
                            </div>
                        </div>
                    </template>
                    <template v-slot:with-padding>
                        <h6>Web Design</h6>
                        <p>
                            Lorem ipsum dolor sit amet, consectetuer adipiscing elit.
                            Aenean commodo ligula eget dolor. Aenean massa. Cum sociis
                            natoque penatibus et magnis dis parturient montes, nascetur
                            ridiculus mus.
                        </p>
                    </template>
                    <template v-slot:footer>
                        <span>Dec 15, 2019</span><span class="pull-right"><i class="fa fa-star font-primary"></i><i
                                class="fa fa-star font-primary"></i><i class="fa fa-star font-primary"></i><i
                                class="fa fa-star font-primary"></i><i class="fa fa-star font-primary"></i></span>
                    </template>
                </px-card>
            </div>
            <div class="col-xl-3 xl-50 col-md-6 box-col-6">
                <px-card :actions="false" class="features-faq product-box">
                    <template v-slot:headerCustom>
                        <div class="faq-image product-img">
                            <img class="img-fluid" src="../aboutPageData/img/02.webp" alt="" />
                            <div class="product-hover">
                                <ul>
                                    <li><i class="icon-link"></i></li>
                                    <li><i class="icon-import"></i></li>
                                </ul>
                            </div>
                        </div>
                    </template>
                    <template v-slot:with-padding>
                        <h6>Web Development</h6>
                        <p>
                            Lorem ipsum dolor sit amet, consectetuer adipiscing elit.
                            Aenean commodo ligula eget dolor. Aenean massa. Cum sociis
                            natoque penatibus et magnis dis parturient montes, nascetur
                            ridiculus mus.
                        </p>
                    </template>
                    <template v-slot:footer>
                        <span>Dec 15, 2019</span><span class="pull-right"><i class="fa fa-star font-primary"></i><i
                                class="fa fa-star font-primary"></i><i class="fa fa-star font-primary"></i><i
                                class="fa fa-star font-primary"></i><i class="fa fa-star font-primary"></i></span>
                    </template>
                </px-card>
            </div>
            <Feature02 />
        </div>
    </div>
</template>
<script>
import { mapState } from 'vuex';
import pxcard from '../aboutPxcard.vue'
import Feature02 from './feature02.vue';

export default {
    components: {
        'px-card': pxcard, Feature02
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