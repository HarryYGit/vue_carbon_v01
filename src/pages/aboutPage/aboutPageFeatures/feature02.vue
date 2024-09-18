<template>
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
                <h6>Innovations Driving a Low-Carbon Economy</h6>
                <p>
                    This article focuses on the industrial sector, one of the largest sources of global carbon emissions. It explores innovative technologies and practices, such as carbon capture and storage (CCS), energy efficiency improvements, and the use of green hydrogen in manufacturing processes. The article also highlights the role of circular economy principles, recycling, and sustainable material sourcing in reducing industrial carbon footprints. By showcasing examples from leading companies, it illustrates how industries can transition to a low-carbon economy while maintaining profitability and competitiveness.
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
                <h6>Carbon Emission Reduction Strategies in Transportation</h6>
                <p>
                    Focusing on the transportation sector, this article examines how electric vehicles (EVs) and other sustainable technologies are reshaping the future of mobility. It discusses the benefits of EVs in cutting emissions, the development of hydrogen-powered vehicles, and the importance of improving public transportation systems. The article also touches on carbon offset programs, urban planning for greener cities, and the need for infrastructure investments to support the growing demand for alternative fuel vehicles.
                </p>
            </template>
            <template v-slot:footer>
                <span>Dec 15, 2019</span><span class="pull-right"><i class="fa fa-star font-primary"></i><i
                        class="fa fa-star font-primary"></i><i class="fa fa-star font-primary"></i><i
                        class="fa fa-star font-primary"></i><i class="fa fa-star font-primary"></i></span>
            </template>
        </px-card>
    </div>
</template>

<script>
import { mapState } from 'vuex';
import pxcard from '../aboutPxcard.vue'
export default {
    components: {
        'px-card': pxcard
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