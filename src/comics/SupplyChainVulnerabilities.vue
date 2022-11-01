<script setup lang="ts">
import BeanieMan from '../vue-comic-components/svgs/BeanieMan.vue';
import PanelBox from '../vue-comic-components/components/PanelBox.vue';
import ComicBox from '../vue-comic-components/components/ComicBox.vue';
import AfterComicBox from '../vue-comic-components/components/AfterComicBox.vue';
import ComicTitle from '../vue-comic-components/components/ComicTitle.vue';
import NavigationBar from '../vue-comic-components/components/NavigationBar.vue';
import { availableLimbPositions } from "../vue-comic-components/svgs/constants/limbPositions";
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
  <ComicTitle>Supply Chain Vulnerabilities</ComicTitle>
  <NavigationBar :comicList="comicList" />
  <ComicBox>
    <PanelBox>
      <BeanieMan :minimumX="60" :minimumY="110" :lengthX="90" :lengthY="360"
        :limbPositions="availableLimbPositions.handsFolded" :beanieBaseColor="speakerBeanieColor.baseColor"
        :beanieStripeColor="speakerBeanieColor.stripeColor" />
      <text x="170" y="100">IT WAS ONCE A </text>
      <text x="170" y="140">POSSIBILITY FOR OPEN</text>
      <text x="170" y="180">SOURCE LIBRARIES TO</text>
      <text x="170" y="220">BE COMPROMISED.</text>

      <text x="170" y="300">NOW, IT HAPPENS EVER</text>
      <text x="170" y="340">MORE FREQUENTLY.</text>
    </PanelBox>
    <PanelBox>
      <text x="50" y="100">SOURCE CODE AND BUILD</text>
      <text x="50" y="140">THREATS ARE OLD HAT TO FIX.</text>
      <text x="50" y="180">DEPENDENCY THREATS ARE A</text>
      <text x="50" y="220">NEWER ISSUE.</text>

      <text x="50" y="300">90% OF CODE IS OPEN SOURCE,</text>
      <text x="50" y="340">NORMALLY. SO ARE 90% OF</text>
      <text x="50" y="380">VULNERABILITIES. SO - HOW DO</text>
      <text x="50" y="420">WE KEEP OURSELVES SAFE</text>
      <text x="50" y="460">FROM THEM?</text>
    </PanelBox>
    <PanelBox>
      <BeanieMan :minimumX="60" :minimumY="110" :lengthX="90" :lengthY="360"
        :beanieBaseColor="speakerBeanieColor.baseColor" :beanieStripeColor="speakerBeanieColor.stripeColor" />
      <text x="140" y="100">WELL, THE OBVIOUS WAY</text>
      <text x="170" y="140">IS - DON'T USE OPEN</text>
      <text x="170" y="180">SOURCE. PROBLEM:</text>
      <text x="170" y="220">YOU CAN'T KEEP UP.</text>

      <text x="170" y="300">EVERYONE IS USING</text>
      <text x="170" y="340">OPEN SOURCE. DON'T,</text>
      <text x="170" y="380">AND YOU WILL BE LEFT</text>
      <text x="170" y="420">IN THE DUST.</text>
    </PanelBox>
    <PanelBox>
      <text x="60" y="90">WHAT IF WE STICK TO JUST A </text>
      <text x="60" y="130">FEW OPEN SOURCE PACKAGES </text>
      <text x="60" y="170">AND CHECK THEM CAREFULLY?</text>
      <text x="60" y="210">PROBLEM: PACKAGES USE</text>
      <text x="60" y="250">PACKAGES, WHICH USE</text>
      <text x="60" y="290">PACKAGES. TWO PACKAGES</text>
      <text x="60" y="330">TURNS INTO TOO MANY.</text>

      <g transform="translate(30, 340)">
        <PackageFigure :minimumX="60" :minimumY="400" />
      </g>
      <g transform="scale(0.5 0.5) translate(430, 680)">
        <PackageFigure />
      </g>
      <g transform="scale(0.5 0.5) translate(430, 840)">
        <PackageFigure />
      </g>
      <g transform="scale(0.25 0.25) translate(1430, 1390)">
        <PackageFigure />
      </g>
      <g transform="scale(0.25 0.25) translate(1430, 1540)">
        <PackageFigure />
      </g>
      <g transform="scale(0.25 0.25) translate(1430, 1680)">
        <PackageFigure />
      </g>
      <g transform="scale(0.25 0.25) translate(1430, 1840)">
        <PackageFigure />
      </g>
    </PanelBox>
    <PanelBox>
      <BeanieMan :minimumX="60" :minimumY="110" :lengthX="90" :lengthY="360"
        :limbPositions="availableLimbPositions.shrug" :beanieBaseColor="speakerBeanieColor.baseColor"
        :beanieStripeColor="speakerBeanieColor.stripeColor" />
      <text x="140" y="100">BUT ISN'T OPEN SOURCE</text>
      <text x="170" y="140">TRUSTWORTHY? WELL,</text>
      <text x="170" y="180">WE TRUST OPEN</text>
      <text x="170" y="220">SOURCE BECAUSE:</text>
      <text x="180" y="260">1. ANYONE CAN LOOK</text>
      <text x="180" y="300">2. 'SOMEONE' WILL</text>
      <text x="220" y="340">NOTICE ISSUES</text>
      <text x="180" y="380">3. THERE ARE RATING</text>
      <text x="220" y="420">SYSTEMS (STARS)</text>
    </PanelBox>
    <PanelBox>
      <text x="60" y="100">HOWEVER,</text>
      <text x="80" y="160">1. THERE'S TOO MANY</text>
      <text x="120" y="200">PACKAGES FOR ANYONE TO</text>
      <text x="120" y="240">LOOK AT PROPERLY.</text>
      <text x="120" y="280">MONTHLY RELEASES ARE</text>
      <text x="120" y="320">INCREASING!</text>
      <text x="80" y="360">2. BY THE SAME TOKEN</text>
      <text x="120" y="400">ISSUE'S OFTEN GO</text>
      <text x="120" y="440">UNNOTICED.</text>
    </PanelBox>
    <PanelBox>
      <text x="60" y="100">3. THERE ARE WAYS TO FAKE</text>
      <text x="100" y="140">GOOD RATINGS. FOR</text>
      <text x="100" y="180">EXAMPLE, <a
          href="https://checkmarx.com/blog/starjacking-making-your-new-open-source-package-popular-in-a-snap/">STARJACKING</a>
        IS</text>
      <text x="100" y="220">WHERE AN OPEN SOURCE</text>
      <text x="100" y="260">PACKAGE LINKS THEMSELVES</text>
      <text x="100" y="300">TO A POPULAR, UNRELATED</text>
      <text x="100" y="340">GIT REPO TO LOOK BETTER.</text>
    </PanelBox>
    <PanelBox>
      <BeanieMan :minimumX="60" :minimumY="110" :lengthX="90" :lengthY="360" beanieBaseColor="#ade"
        beanieStripeColor="#dea" />
      <text x="170" y="100">SO WE HAVE THESE 3</text>
      <text x="170" y="140">THINGS THAT MAKE</text>
      <text x="170" y="180">OPEN SOURCE FEEL</text>
      <text x="170" y="220">TRUSTWORTHY, BUT</text>
      <text x="170" y="260">THERE ARE WAYS IT</text>
      <text x="170" y="300">CAN GO WRONG.</text>
      <text x="170" y="360">FOR EXAMPLE:</text>
    </PanelBox>
    <PanelBox>
      <text x="60" y="100">UA-PARSER-JS: A POPULAR</text>
      <text x="60" y="140">NPM PACKAGE ACTIVELY</text>
      <text x="60" y="180">MAINTAINED FOR 10 YEARS,</text>
      <text x="60" y="220">WITH MILLIONS OF WEEKLY</text>
      <text x="60" y="260">DOWNLOADS. THE OWNER</text>
      <text x="60" y="300">DIDN'T HAVE 2FA ON, AND A</text>
      <text x="60" y="340">HACKING GROUP GOT IN AND</text>
      <text x="60" y="380">ADDED A CRYPTO MINER TO IT.</text>
      <text x="60" y="420">HUNDREDS OF THOUSANDS OF</text>
      <text x="60" y="460">DEVICES WERE COMPROMISED.</text>
    </PanelBox>
    <PanelBox>
      <BeanieMan :minimumX="60" :minimumY="110" :lengthX="90" :lengthY="360"
        :limbPositions="availableLimbPositions.handsFolded" beanieBaseColor="#ade" beanieStripeColor="#dea" />
      <text x="170" y="100">YOU CAN MAKE YOUR</text>
      <text x="170" y="140">DEVELOPERS USE 2FA.</text>
      <text x="170" y="180">YOU CAN'T MAKE SOME</text>
      <text x="170" y="220">HOBBY PROGRAMMER</text>
      <text x="170" y="260">WHO'S CODE RUNS ON</text>
      <text x="170" y="300">EVERY REACT INSTANCE</text>
      <text x="170" y="340">USE IT.</text>
    </PanelBox>
    <PanelBox>
      <BeanieMan :minimumX="60" :minimumY="110" :lengthX="90" :lengthY="360" beanieBaseColor="#ade"
        :limbPositions="availableLimbPositions.shrug" beanieStripeColor="#dea" />
      <text x="170" y="100">SO WHAT CAN YOU DO?</text>
      <text x="170" y="140">FIRST, BE AWARE.</text>
      <text x="170" y="200">DEVS, OPS, AND</text>
      <text x="170" y="240">MANAGEMENT ALL NEED</text>
      <text x="170" y="280">TO PRIORITISE SAFETY</text>
      <text x="170" y="320">FROM DEPENDENCY</text>
      <text x="170" y="360">THREATS FROM THE</text>
      <text x="170" y="400">START OF A PROJECT.</text>
    </PanelBox>
    <PanelBox>
      <BeanieMan :minimumX="60" :minimumY="110" :lengthX="90" :lengthY="360" beanieBaseColor="#ade"
        beanieStripeColor="#dea" />
      <text x="170" y="100">NEXT, YOU'LL ACTUALLY</text>
      <text x="170" y="140">NEED A WAY TO CHECK</text>
      <text x="170" y="180">FOR VULNERABILITIES.</text>
      <text x="170" y="220">REALISTICALLY, YOU'LL</text>
      <text x="170" y="260">NEED AN AUTOMATED</text>
      <text x="170" y="300">TOOL.</text>
      <text x="170" y="360">CHECKMARX IS ONE</text>
      <text x="170" y="400">GOOD OPTION.</text>
    </PanelBox>
    <PanelBox>
      <BeanieMan :minimumX="60" :minimumY="110" :lengthX="90" :lengthY="360"
        :limbPositions="availableLimbPositions.rightHandPointingSouthEast" beanieBaseColor="#ade"
        beanieStripeColor="#dea" />
      <text x="135" y="100">CHECKMARX INTEGRATES</text>
      <text x="170" y="140">SOURCE CODE, BUILD</text>
      <text x="170" y="180">AND DEPENDENCY</text>
      <text x="170" y="220">THREAT MITIGATION</text>
      <text x="170" y="260">INTO ONE UNIFIED</text>
      <text x="170" y="300">PLATFORM. THERE'S</text>
      <text x="170" y="340">MORE ABOUT IT AT</text>
      <text x="200" y="380"><a href="https://checkmarx.com/">checkmarx.com</a></text>
    </PanelBox>
    <PanelBox>
      <BeanieMan :minimumX="60" :minimumY="110" :lengthX="90" :lengthY="360" beanieBaseColor="#ade"
        beanieStripeColor="#dea" />
      <text x="170" y="100">FINALLY, REMEMBER:</text>
      <text x="170" y="140">VULNERABLE DOES'T</text>
      <text x="170" y="180">EQUAL MALICIOUS.</text>
      <text x="170" y="220">VULNERABLE CODE</text>
      <text x="170" y="260">THAT IS MANAGED IS</text>
      <text x="170" y="300">OKAY. MALICIOUS CODE</text>
      <text x="170" y="340">IS NEVER OKAY. MAKE</text>
      <text x="170" y="380">SURE YOU'RE AWARE</text>
      <text x="170" y="420">OF AND ARE LOOKING</text>
      <text x="170" y="460">OUT FOR BOTH.</text>
    </PanelBox>
  </ComicBox>
  <NavigationBar :comicList="comicList" />
  <AfterComicBox>
    <p>Thanks to <a href="https://www.linkedin.com/in/michael-fowler/">Michael Fowler</a> of Checkmarx for a cracker
      talk at <a href="https://devops.talksplus.com/sydney/devops.html">DevOps Talks Conference 2022</a></p>
    <p>Join the discussion at <a href="https://oneiress.slack.com/archives/C040VRMT64U/p1662099674315709">Slack</a>.</p>
  </AfterComicBox>
</template>