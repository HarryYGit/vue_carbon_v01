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
                        <h6>The Global Impact of Carbon Emissions</h6>
                        <p>
                            This article delves into the pressing issue of global carbon emissions and their detrimental effects on the environment. It highlights key contributors like the burning of fossil fuels, deforestation, and industrial processes, all of which drive climate change. The article also explores potential solutions such as transitioning to renewable energy, carbon capture technology, and adopting eco-friendly policies. It emphasizes the role of global cooperation and individual action in mitigating emissions to achieve a sustainable future.
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
                        <h6>The Future of Clean Energy</h6>
                        <p>
                            This article explores the pivotal role of renewable energy sources such as solar, wind, hydro, and geothermal power in reducing carbon footprints globally. It discusses advancements in technology that make these energy sources more viable, scalable, and affordable. Furthermore, it assesses the transition away from fossil fuels and the challenges faced by industries and governments in adopting clean energy. The article concludes by underscoring the importance of innovation and global policy support in fostering a carbon-neutral energy future.
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