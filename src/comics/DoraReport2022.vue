<script setup lang="ts">
  import BeanieMan from '../vue-comic-components/svgs/BeanieMan.vue';
  import ManFigure from '../vue-comic-components/svgs/ManFigure.vue';
  import PanelBox from '../vue-comic-components/components/PanelBox.vue';
  import ComicBox from '../vue-comic-components/components/ComicBox.vue';
  import AfterComicBox from '../vue-comic-components/components/AfterComicBox.vue';
  import ComicTitle from '../vue-comic-components/components/ComicTitle.vue';
  import NavigationBar from '../vue-comic-components/components/NavigationBar.vue';
  import { availableLimbPositions } from "../vue-comic-components/svgs/constants/limbPositions";
  import { toRefs } from "vue";
  import CloudComputing from "../vue-comic-components/svgs/CloudComputing.vue";
  import DocumentFigure from "../vue-comic-components/svgs/DocumentFigure.vue";
  import SREFigure from "../vue-comic-components/svgs/SREFigure.vue";
  import PadlockFigure from "../vue-comic-components/svgs/PadlockFigure.vue";
  import LeftPointingArrow from "../vue-comic-components/svgs/LeftPointingArrow.vue";
  import SpannerFigure from "../vue-comic-components/svgs/SpannerFigure.vue";
  const props = defineProps<{
      comicList: Array<string>;
  }>();
  const { comicList } = toRefs(props);
  const speakerBeanieColor = {
      baseColor: "#ade",
      stripeColor: "#dea",
  }
  </script>
        
  <template>
      <ComicTitle>Summary of the DORA Report, 2022</ComicTitle>
      <NavigationBar :comicList="comicList" />
      <ComicBox>
          <PanelBox>
              <BeanieMan :minimumX="60" :minimumY="110" :lengthX="90" :lengthY="360"
                  :limbPositions="availableLimbPositions.rightHandWave" :beanieBaseColor="speakerBeanieColor.baseColor"
                  :beanieStripeColor="speakerBeanieColor.stripeColor" />
              <text x="180" y="100">HELLO! WE'RE HERE ON</text>
              <text x="180" y="140">ANOTHER SCIENTIFIC JOURNEY</text>
              <text x="180" y="180">COURTESY OF GOOGLE.</text>
  
          </PanelBox>
        </ComicBox>
  </template>
  
  <style>
  .comic-box {
      max-width: 900px;
  }
  
  .panel .title-text {
    font-size: 42px;
  }
  </style>