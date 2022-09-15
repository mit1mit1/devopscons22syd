<script setup lang="ts">
import BeanieMan from '../vue-comic-components/svgs/BeanieMan.vue';
import PanelBox from '../vue-comic-components/components/PanelBox.vue';
import ComicBox from '../vue-comic-components/components/ComicBox.vue';
import AfterComicBox from '../vue-comic-components/components/AfterComicBox.vue';
import ComicTitle from '../vue-comic-components/components/ComicTitle.vue';
import NavigationBar from '../vue-comic-components/components/NavigationBar.vue';
import { availableLimbPositions } from "../vue-comic-components/constants/limbPositions";
import { toRefs } from "vue";
import PackageFigure from "../vue-comic-components/svgs/PackageFigure.vue";
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
    <ComicTitle>Updates from the DORA Research Program</ComicTitle>
    <NavigationBar :comicList="comicList" />
    <ComicBox>
        <PanelBox>
            <BeanieMan :minimumX="60" :minimumY="110" :lengthX="90" :lengthY="360"
                :limbPositions="availableLimbPositions.rightHandWave" :beanieBaseColor="speakerBeanieColor.baseColor"
                :beanieStripeColor="speakerBeanieColor.stripeColor" />
            <text x="180" y="100">HELLO! DAVE FROM</text>
            <text x="180" y="140">GOOGLE HERE, ON A</text>
            <text x="180" y="180">JOURNEY OF SCIENCE!</text>

            <text x="180" y="240">WE'VE HAD SOME COOL</text>
            <text x="180" y="280">STATISTICAL ANALYSIS</text>
            <text x="180" y="320">DONE FOR US, LET'S</text>
            <text x="180" y="360">JUMP INTO THE</text>
            <text x="180" y="400">FINDINGS.</text>
        </PanelBox>
        <PanelBox>
            <text x="50" y="80">THE DORA PROGRAM DOES</text>
            <text x="50" y="120">PREDICTIVE ANALYSIS BETWEEN</text>
            <text x="50" y="160">DEVOPS PRACTICES AND</text>
            <text x="50" y="200">BUSINESS OUTCOMES.</text>

            <text x="50" y="255">IT'S WORTH NOTING THAT A</text>
            <text x="50" y="295">PREDICTIVE LINK IS NOT AS</text>
            <text x="50" y="335">STRONG AS A CAUSAL ONE.</text>
            <text x="50" y="390">I.E. - PRACTICES RECOMMENDED</text>
            <text x="50" y="430">ARE PREDICTORS OF SUCCESS,</text>
            <text x="50" y="470">NOT GUARANTEES OF IT.</text>
        </PanelBox>
        <PanelBox>
            <text x="50" y="80">SO WHAT PREDICTIONS ARE WE</text>
            <text x="50" y="120">MAKING HERE?</text>

            <text x="50" y="180">WE'RE PREDICTING 5 METRICS:</text>

            <text x="50" y="240">1. DEPLOYMENT FREQUENCY</text>
            <text x="50" y="280">2. LEAD TIME TO CHANGES</text>
            <text x="50" y="320">3. TIME TO RESTORE SERVICE</text>
            <text x="50" y="360">4. CHANGE FAILURE RATE</text>
            <text x="50" y="400">5. RELIABILITY OF SOFTWARE</text>
            <text x="170" y="280"></text>
        </PanelBox>
        <PanelBox>
            <BeanieMan :minimumX="60" :minimumY="110" :lengthX="90" :lengthY="360"
                :beanieBaseColor="speakerBeanieColor.baseColor" :beanieStripeColor="speakerBeanieColor.stripeColor" />
            <text x="180" y="90">WE ALL WANT FASTER</text>
            <text x="180" y="130">FEATURES AND FIXES,</text>
            <text x="180" y="170">FEWER BUGS AND</text>
            <text x="180" y="210">LESS DOWNTIME.</text>
    
            <text x="180" y="260">THE 5 METRICS</text>
            <text x="180" y="300">QUANTIFY THESE SO</text>
            <text x="180" y="340">WE CAN STUDY THEM.</text>

            <text x="180" y="390">SO LET'S DEEP DIVE</text>
            <text x="180" y="430">INTO PREDICTORS OF</text>
            <text x="180" y="470">THESE METRICS.</text>
        </PanelBox>
        <PanelBox>
            <text x="50" y="80">- CLOUD COMPUTING PRACTICES</text>
            
            <text x="50" y="130">EVERYONE BUT ONLY SOME</text>
            <text x="50" y="170">WE'RE PREDICTING 5 METRICS:</text>

            <text x="50" y="240">1. DEPLOYMENT FREQUENCY</text>
            <text x="50" y="280">2. LEAD TIME TO CHANGES</text>
            <text x="50" y="320">3. TIME TO RESTORE SERVICE</text>
            <text x="50" y="360">4. CHANGE FAILURE RATE</text>
            <text x="50" y="400">5. RELIABILITY OF SOFTWARE</text>
            <text x="170" y="280"></text>
        </PanelBox>
    </ComicBox>
    <NavigationBar :comicList="comicList" />
    <AfterComicBox>
        <p>Thanks to <a href="https://twitter.com/davidstanke">Dave Stanke</a> of Google Cloud an awesome research deep
            dive at <a href="https://devops.talksplus.com/sydney/devops.html">DevOps Talks Conference 2022</a></p>
        <p>Read the report for yourself <a href="https://cloud.google.com/devops/state-of-devops">here</a>.</p>
        <p>Join the discussion at <a href="https://oneiress.slack.com/archives/C040VRMT64U/p1662099674315709">Slack</a>.
        </p>
    </AfterComicBox>
</template>