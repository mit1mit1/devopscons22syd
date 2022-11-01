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
    <ComicTitle>Updates from the DORA Research Program, 2021</ComicTitle>
    <NavigationBar :comicList="comicList" />
    <ComicBox>
        <PanelBox>
            <BeanieMan :minimumX="60" :minimumY="110" :lengthX="90" :lengthY="360"
                :limbPositions="availableLimbPositions.rightHandWave" :beanieBaseColor="speakerBeanieColor.baseColor"
                :beanieStripeColor="speakerBeanieColor.stripeColor" />
            <text x="180" y="100">HELLO! WE'RE HERE ON</text>
            <text x="180" y="140">A SCIENTIFIC JOURNEY</text>
            <text x="180" y="180">COURTESY OF GOOGLE.</text>

            <text x="180" y="240">WE'VE HAD SOME COOL</text>
            <text x="180" y="280">STATISTICAL ANALYSIS</text>
            <text x="180" y="320">DONE FOR US IN THE</text>
            <text x="180" y="360">2021 <a href="https://cloud.google.com/devops/state-of-devops">DORA REPORT</a>.</text>

            <text x="180" y="420"> LET'S JUMP INTO THE</text>
            <text x="180" y="460">FINDINGS.</text>
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
    </ComicBox>
    <ComicBox>
        <PanelBox>
            <text x="140" y="120">CLOUD COMPUTING</text>
            <text x="188" y="160">PRACTICES</text>
            <g transform="scale(1.7 1.7) translate(50, 75)">
                <CloudComputing />
            </g>
        </PanelBox>
    </ComicBox>
    <ComicBox>
        <PanelBox>
            <text x="50" y="80">DORA FOUND THAT CLOUD</text>
            <text x="50" y="120">ADOPTION IS RISING, WHICH IS</text>
            <text x="50" y="160">ALREADY A GOOD START.</text>

            <text x="50" y="220">BUT MORE IMPORTANT IS IF</text>
            <text x="50" y="260">CLOUD IS IMPLEMENTED WELL.</text>
            <text x="50" y="300">ONLY 1/3 OF CLOUD USERS MET</text>
            <text x="50" y="340">ALL 5 NIST CLOUD STANDARDS.</text>

            <text x="50" y="400">THE ONES THAT DID MEET THE</text>
            <text x="50" y="440">STANDARDS WERE 3x MORE</text>
            <text x="50" y="480">LIKELY TO SMASH THE METRICS.</text>
        </PanelBox>
        <PanelBox>
            <text x="50" y="80">THE FIVE STANDARDS ARE:</text>
            <text x="50" y="130">1. AUTOMATICALLY PROVISIONED</text>
            <text x="80" y="170">RESOURCES</text>
            <text x="50" y="210">2. WORLDWIDE ACCESS ON ANY</text>
            <text x="80" y="250">DEVICE TYPE</text>
            <text x="50" y="290">3. MULTI-TENANCY POOLING</text>
            <text x="80" y="330">OF RESOURCES</text>
            <text x="50" y="370">4. RAPID SCALING OF</text>
            <text x="80" y="410">CAPABILITIES</text>
            <text x="50" y="450">5. MEASURE AND OPTIMISE</text>
            <text x="80" y="490">SERVICE</text>
        </PanelBox>
        <PanelBox>
            <BeanieMan :minimumX="60" :minimumY="110" :lengthX="90" :lengthY="360"
                :limbPositions="availableLimbPositions.handsFolded" :beanieBaseColor="speakerBeanieColor.baseColor"
                :beanieStripeColor="speakerBeanieColor.stripeColor" />

            <text x="180" y="90">THAT'S A VERY, VERY</text>
            <text x="180" y="130">BRIEF VERSION OF THE</text>
            <text x="180" y="170">CLOUD STANDARDS.</text>
            <text x="180" y="230">FOR A PROPER</text>
            <text x="180" y="270">EXPLANATION, PLUS</text>
            <text x="180" y="310">PITFALLS AND</text>
            <text x="180" y="350">SUGGESTIONS, SEE</text>
            <text x="180" y="390">
                <a
                    href="https://cloud.google.com/architecture/devops/devops-tech-cloud-infrastructure">cloud.google.com/.../infra</a></text>
        </PanelBox>
    </ComicBox>
    <ComicBox>
        <PanelBox>
            <text x="140" y="120">SRE PERFORMANCE</text>
            <g transform="scale(1.7 1.7) translate(60, 55)">
                <SREFigure />
            </g>
        </PanelBox>
    </ComicBox>
    <ComicBox>
        <PanelBox>
            <text x="50" y="80">THESE SRE METRICS GAVE</text>
            <text x="50" y="120">1.8x PERFORMANCE:</text>

            <text x="50" y="170">1. DEFINE RELIABILITY AS</text>
            <text x="80" y="210">USER-FACING BEHAVIOR</text>
            <text x="50" y="250">2. PRIORITISE WORK USING</text>
            <text x="80" y="290">SLIs/SLOs + ERROR BUDGETS</text>
            <text x="50" y="330">3. AUTOMATE <a href="https://sre.google/sre-book/eliminating-toil/">TOIL</a></text>
            <text x="50" y="370">4. DEFINE PROTOCOLS+DRILLS</text>
            <text x="80" y="410">FOR INCIDENT RESPONSE.</text>
            <text x="50" y="450">5. SHIFT LEFT ON RELIABILITY</text>
        </PanelBox>
        <PanelBox>
            <BeanieMan :minimumX="60" :minimumY="110" :lengthX="90" :lengthY="360"
                :beanieBaseColor="speakerBeanieColor.baseColor" :beanieStripeColor="speakerBeanieColor.stripeColor" />

            <text x="180" y="90">THE REPORT COVERS</text>
            <text x="180" y="130">THE BENEFITS OF SRE</text>
            <text x="180" y="170">IN MORE DETAIL.</text>

            <text x="180" y="230">GOOGLE ALSO</text>
            <text x="180" y="270">PROVIDES A WHOLE</text>
            <text x="180" y="310">BUNCH OF SRE</text>
            <text x="180" y="350"> RESOURCES AT</text>
            <text x="180" y="390">
                <a href="https://sre.google/resources/">sre.google/resources</a></text>
        </PanelBox>
    </ComicBox>
    <ComicBox>
        <PanelBox>
            <text x="200" y="120">INTERNAL</text>
            <text x="145" y="160">DOCUMENTATION</text>
            <g transform="scale(1.2 1.2) translate(139, 160)">
                <DocumentFigure />
            </g>
        </PanelBox>
    </ComicBox>
    <ComicBox>
        <PanelBox>
            <text x="50" y="80">THESE INTERNAL DOC METRICS</text>
            <text x="50" y="120">GAVE 2.5x PERFORMANCE:</text>

            <text x="50" y="180">- DOCS HELP READERS</text>
            <text x="80" y="220">ACCOMPLISH GOALS</text>
            <text x="50" y="260">- DOCS ARE ACCURATE, UP TO</text>
            <text x="80" y="300"> DATE, AND COMPREHENSIVE</text>
            <text x="50" y="340">- DOCS ARE FINDABLE,</text>
            <text x="80" y="380"> WELL-ORGANISED AND CLEAR</text>
        </PanelBox>
        <PanelBox>
            <text x="50" y="80">SOME PRACTICES WERE SHOWN</text>
            <text x="50" y="120">HELP MEET THE METRICS:</text>

            <text x="50" y="180">1. DOCUMENT CRITICAL USE</text>
            <text x="80" y="220">CASES</text>
            <text x="50" y="260">2. CREATE GUIDELINES FOR,</text>
            <text x="80" y="300">MAINTAINING DOCS</text>
            <text x="50" y="340">3. DEFINE DOC OWNERS</text>
            <text x="50" y="380">4. MAKE DOCUMENTATION PART</text>
            <text x="80" y="420">OF THE DEV PROCESS</text>
            <text x="50" y="460">5. RECOGNISE DOCUMENT-ERS</text>
        </PanelBox>
        <PanelBox>
            <BeanieMan :minimumX="60" :minimumY="110" :lengthX="90" :lengthY="360"
                :limbPositions="availableLimbPositions.excited" :beanieBaseColor="speakerBeanieColor.baseColor"
                :beanieStripeColor="speakerBeanieColor.stripeColor" />
            <text x="180" y="90">THERE'S A LOT MORE</text>
            <text x="180" y="130">DETAIL ON THE DOCS</text>
            <text x="180" y="170">PRACTICES IN THE</text>
            <text x="180" y="210">REPORT!</text>

            <text x="180" y="270">PLUS, REFERENCES</text>
            <text x="180" y="310">TO EARLIER COST-</text>
            <text x="180" y="350">BENEFIT ANALYSIS'</text>
            <text x="180" y="390">ON DOCUMENTATION.</text>
        </PanelBox>
    </ComicBox>
    <ComicBox>
        <PanelBox>
            <text x="165" y="120">SHIFT LEFT ON</text>
            <text x="195" y="160">SECURITY</text>
            <g transform="translate(155, 120)">
                <PadlockFigure />
            </g>
            <g transform="translate(155, 260)">
                <LeftPointingArrow />
            </g>
        </PanelBox>
    </ComicBox>
    <ComicBox>
        <PanelBox>
            <text x="50" y="80">SHIFTING LEFT IN THESE WAYS</text>
            <text x="50" y="120"> GAVE 1.6x PERFORMANCE:</text>

            <text x="50" y="170">1. TEST FOR SECURITY IN YOUR</text>
            <text x="80" y="210">AUTOMATED TEST SUITES</text>
            <text x="50" y="250">2. INTEGRATE INFOSEC IN THE</text>
            <text x="80" y="290">WHOLE SOFTWARE LIFECYCLE</text>
            <text x="50" y="330">3. DO SECURITY REVIEWS ON</text>
            <text x="80" y="370">ALL MAJOR FEATURES</text>
            <text x="50" y="410">4. MAKE TOOLS AVAILABLE WHICH</text>
            <text x="80" y="450">ARE INFOSEC PRE-APPROVED</text>
        </PanelBox>
        <PanelBox>
            <BeanieMan :minimumX="60" :minimumY="110" :lengthX="90" :lengthY="360"
                :limbPositions="availableLimbPositions.rightHandPointingNorthEast"
                :beanieBaseColor="speakerBeanieColor.baseColor" :beanieStripeColor="speakerBeanieColor.stripeColor" />

            <text x="180" y="100">AGAIN, THERE'S A</text>
            <text x="180" y="140">BUNCH MORE DETAIL</text>
            <text x="180" y="180">AND LINKS TO SOME</text>
            <text x="180" y="220">CASE STUDIES IN </text>
            <text x="180" y="260"><a href="https://cloud.google.com/devops/state-of-devops">THE REPORT</a></text>
        </PanelBox>
    </ComicBox>
    <ComicBox>
        <PanelBox>
            <text class="title-text" x="65" y="120">TECHNICAL PRACTICES</text>
            <text class="title-text" x="200" y="160">(MISC.)</text>
            <g transform="scale(1.3 1.3) translate(130, 100)">
                <SpannerFigure />
            </g>
        </PanelBox>
    </ComicBox>
    <ComicBox>
        <PanelBox>
            <BeanieMan :minimumX="60" :minimumY="110" :lengthX="90" :lengthY="360"
                :beanieBaseColor="speakerBeanieColor.baseColor" :beanieStripeColor="speakerBeanieColor.stripeColor" />

            <text x="180" y="100">THE REPORT LISTS A</text>
            <text x="180" y="140">WHOLE BUNCH MORE</text>
            <text x="180" y="180">TECHNICAL PRACTICES</text>
            <text x="180" y="220">THAT PREDICT GOOD</text>
            <text x="180" y="260">BUSINESS OUTCOMES.</text>

            <text x="180" y="320">WE'LL LOOK AT THE</text>
            <text x="180" y="360">TWO STRONGEST</text>
            <text x="180" y="400">PREDICTORS.</text>
        </PanelBox>
        <PanelBox>
            <text x="50" y="80">1. LOOSELY COUPLED</text>
            <text x="80" y="120">ARCHITECTURE</text>

            <text x="50" y="170">AVOID COMPLEX DEPENDENCIES</text>
            <text x="50" y="210">BETWEEN SERVICES, AND </text>
            <text x="50" y="250">BETWEEN TEAMS.</text>

            <text x="50" y="300">THIS WILL UNBLOCK CONTINUOUS</text>
            <text x="50" y="340">DELIVERY. IT WILL ALLOW TEAMS</text>
            <text x="50" y="380">WORK INDEPENDENTLY, WHICH</text>
            <text x="50" y="420">WILL SPEED UP EVERY BIT OF</text>
            <text x="50" y="460">THEIR DEVELOPMENT PROCESS.</text>
        </PanelBox>
        <PanelBox>
            <text x="50" y="80">2. CONTINUOUS TESTING</text>

            <text x="50" y="130">START TESTING EARLY IN THE</text>
            <text x="50" y="170">DELIVERY PROCESS; TEST</text>
            <text x="50" y="210">OFTEN; HAVE TESTERS WORK</text>
            <text x="50" y="250">WITH DEVS ALL THE WAY</text>
            <text x="50" y="290">THROUGH.</text>

            <text x="50" y="340">THIS WILL ALLOW TEAMS TO</text>
            <text x="50" y="380">ITERATE AND MAKE CHANGES</text>
            <text x="50" y="420">QUICKER - MEANING BETTER</text>
            <text x="50" y="460">VALUE GETS OUT FASTER.</text>
        </PanelBox>
    </ComicBox>
    <ComicBox>
        <PanelBox>
            <text x="128" y="120">CULTURE AND COVID</text>
            <BeanieMan :minimumX="150" :minimumY="230" :lengthX="30" :lengthY="120"
                :limbPositions="availableLimbPositions.handsDown" beanieBaseColor="#afd" beanieStripeColor="#aad" />
            <ManFigure :minimumX="190" :minimumY="240" :lengthX="30" :lengthY="120"
                :limbPositions="availableLimbPositions.handsDown" />
            <BeanieMan :minimumX="230" :minimumY="240" :lengthX="30" :lengthY="120"
                :limbPositions="availableLimbPositions.handsDown" beanieBaseColor="#ee0" beanieStripeColor="#eef" />
            <BeanieMan :minimumX="270" :minimumY="210" :lengthX="30" :lengthY="120"
                :limbPositions="availableLimbPositions.handsDown" beanieBaseColor="#fa3" beanieStripeColor="#3af" />
            <ManFigure :minimumX="310" :minimumY="270" :lengthX="30" :lengthY="120"
                :limbPositions="availableLimbPositions.handsDown" />
            <BeanieMan :minimumX="350" :minimumY="220" :lengthX="30" :lengthY="120"
                :limbPositions="availableLimbPositions.handsDown" beanieBaseColor="#e11" beanieStripeColor="#1ee" />
        </PanelBox>
    </ComicBox>
    <ComicBox>
        <PanelBox>
            <text x="50" y="80">COVID WAS ROUGH - FOR</text>
            <text x="50" y="120">EVERYONE. BUT EVEN IN COVID,</text>
            <text x="50" y="160">A POSITIVE WORKPLACE CULTURE</text>
            <text x="50" y="200">WAS LINKED TO BOTH BETTER</text>
            <text x="50" y="240">PERFORMANCE, AND LESS</text>
            <text x="50" y="280">EMPLOYEE BURNOUT.</text>

            <text x="50" y="330">THERE IS A VERY, VERY HELPFUL</text>
            <text x="50" y="370">ARTICLE ON WHAT THIS LOOKS</text>
            <text x="50" y="410">LIKE, AND HOW TO BUILD IT, AT</text>
            <text x="50" y="450"><a
                    href="https://cloud.google.com/architecture/devops/devops-culture-westrum-organizational-culture">cloud.google.com/.../westrum</a></text>
        </PanelBox>
        <PanelBox>
            <text x="50" y="100">HOWEVER, IN A FINAL SUMMARY:</text>

            <text x="50" y="160">- SHARE RESPONSIBILITIES AND</text>
            <text x="80" y="200">RISKS, BUT REMOVE BLAME</text>
            <text x="50" y="240">- ENCOURAGE COLLABORATION,</text>
            <text x="80" y="280">AND BRIDGE BETWEEN SILOS</text>
            <text x="50" y="320">- PROMOTE PSYCHOLOGICAL</text>
            <text x="80" y="360">SAFETY</text>
            <text x="50" y="400">- VALUE AND CELEBRATE</text>
            <text x="80" y="440">EVERYONE'S WHOLE SELVES</text>
        </PanelBox>
    </ComicBox>
    <NavigationBar :comicList="comicList" />
    <AfterComicBox>
        <p>Thanks to <a href="https://twitter.com/davidstanke">Dave Stanke</a> of Google Cloud for an awesome research
            deep
            dive at <a href="https://devops.talksplus.com/sydney/devops.html">DevOps Talks Conference 2022</a></p>
        <p>Read the report for yourself <a href="https://cloud.google.com/devops/state-of-devops">here</a>.</p>
        <p>Join the discussion at <a href="https://oneiress.slack.com/archives/C040VRMT64U/p1662099674315709">Slack</a>.
        </p>
    </AfterComicBox>
</template>

<style>
.comic-box {
    max-width: 900px;
}

.panel .title-text {
  font-size: 42px;
}
</style>