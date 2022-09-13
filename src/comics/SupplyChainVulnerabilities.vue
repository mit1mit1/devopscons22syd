<script setup lang="ts">
import BeanieMan from '../vue-comic-components/svgs/BeanieMan.vue';
import PanelBox from '../vue-comic-components/components/PanelBox.vue';
import ComicBox from '../vue-comic-components/components/ComicBox.vue';
import AfterComicBox from '../vue-comic-components/components/AfterComicBox.vue';
import ComicTitle from '../vue-comic-components/components/ComicTitle.vue';
import NavigationBar from '../vue-comic-components/components/NavigationBar.vue';
import { availableLimbPositions } from "../vue-comic-components/constants/limbPositions";
import { toRefs } from "vue";
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
      <text x="60" y="100">WHAT IF WE STICK TO JUST A </text>
      <text x="60" y="140">FEW OPEN SOURCE PACKAGES </text>
      <text x="60" y="180">AND CHECK THEM CAREFULLY?</text>
      <text x="60" y="220">PROBLEM: PACKAGES USE</text>
      <text x="60" y="260">PACKAGES USE PACKAGES.</text>
      <text x="60" y="300">EVEN A COUPLE OF PACKAGES</text>
      <text x="60" y="340">ENDS UP TOO BIG TO CHECK.</text>
      <text x="60" y="400">(Package mitosis svgs)</text>
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
      <BeanieMan :minimumX="60" :minimumY="110" :lengthX="90" :lengthY="360"
        :limbPositions="availableLimbPositions.handsFolded" beanieBaseColor="#ade" beanieStripeColor="#dea" />
      <text x="60" y="100">SO WE HAVE THESE THINGS</text>
      <text x="60" y="140">THAT MAKE OS FEEEEL TRUSTWORTHY,</text>
      <text x="60" y="180">BUT IT CAN GO BAD.</text>
      <text x="60" y="220">FOR EXAMPLE:</text>
    </PanelBox>
    <PanelBox>
      <text>
        <!-- AMERICAN GOV HAVE PUT OUT AN EXECUTIVE ORDER TO GET EM FIXED.
  
        SUPPLY CHAIN LEVELS FOR SOFTWARE ARCHITECTS ARE SOME BIG PLAYERS COMING TOGETHER TO TRY AND REGULATE THE SOURCE
        THREATS, BUILD THREATS AND DEPENDENCY THREATS IN THE SUPPLY CHAIN. -->
        <!-- MONTHLY PACKAGE RELEASES IS INCREASING ON A BUNCH OF PLATFORMS (EXCEPT RUBY :( ). -->

        THIS CONTRIBUTES TO TRUSTWORTHY FEELING, BUT IT CAN GO BAD.

        E.G.:

        UA-PARSER-JS - ACTIVELY MAINTAINED FOR 10 YEARS, MILLIONS OF REGULAR DOWNLOADS, MOST LIKELY YOU'RE ALREADY USING
        IT (FACEBOOK IS).

        IT DIDN'T HAVE 2FA ON THE ACCOUNT, A RUSSIAN HACKING GROUP GOT IT, PUBLISHED TO CREDENTIALS, AND THEY INSTALLED
        CRYPTO MINERS ON MANY MANY DEVICES.


        E.G. 2 WEEKS LATER:

        COA AND RC, 22 MILLION WEEKLY DOWNLOADS. WE DON'T KNOW HOW, BUT SOMEHOW THE SAME MALICIOUS CODE GOT PUT INTO
        BOTH OF THEM.


        YOU CAN ENSURE YOUR DEVS HAVE 2FA, BUT YOU CAN'T ENSURE THE HOBBY DEVELOPER WHO MAKES SOME LITTLE LIBRARY THAT'S
        PART OF REACT DOES TOO.


        E.G. 3:

        RIAEVANGELIST, ANOTHER SUPER POPULAR LIBRARY, THE AUTHOR PUT SOME VERY OBFUSICATED CODE INTO THE LIBRARY. IT
        TURNS OUT THAT IT CHECKS YOUR IP, AND IF YOU'RE FROM RUSSIA OR BELARUSE, IT DELETES - EVERYTHING.

        THE AUTHOR WAS ASKED ABOUT IT, HE SAID "IT'S MY CODE, YOU'RE RUNNING IT, I CAN DO WHAT I WANT WITH IT".

        HE DID THIS TO ONE OF HIS PROJECTS, HE HAS 40 OTHERS, WHAT IF HE DECIDES HE JUST DOESN'T LIKE BIG BANKS?


        E.G. REDLILI:

        THESE GUYS ARE A SUPPLY CHAIN ATTACK THREAT. THEY CREATE MALICIOUS PACKAGES FROM ALL DIFFERENT ACCOUNTS, ON
        DISPOSABLE DOMAINS - SO THEY CAN'T BE CAUGHT.


        ALIGN SECURITY AND OPERATIONS:

        - FRAME THE CONVERSATION ABOUT OPEN-SOURCE USAGE WITH DEV AND MANAGEMENT
        - UNDERSTAND YOUR OPEN SOURCE RISK PROFILE.

        (CHECKMARX ADVERTISING SPHEAL - SEEMS A SIMILAR TOOL TO SNYK, SCANS AND ALERTS YOU TO VULNERABILITIES IN
        PACKAGES AND SUBPACKAGES, GIVES YOU ATTACK VECTORS).


        VULNERABLE != MALICIOUS.

        - IT'S OKAY TO RUN VULNERABLE CODE, AS LONG AS IT IS MANAGED AND TRIAGED.
        - IT'S NOT OKAY TO RUN MALICIOUS.


        CHECKMARX DOES (SEE SLIDES). CLAIMS TO DO MORE THAN CURRENT MARKET OFFERINGS. ALSO CLAIMS TO KEEP THE OPEN
        SOURCE LIBRARIES UP TO DATE ON FOUND VULNERABILITIES, WHICH SEEMS COOL..
      </text>
    </PanelBox>

  </ComicBox>
  <NavigationBar :comicList="comicList" />
  <AfterComicBox>
    <p>Thanks to <a href="https://www.linkedin.com/in/michael-fowler/">Michael Fowler</a> of Checkmarx for a cracker
      talk at <a href="https://devops.talksplus.com/sydney/devops.html">DevOps Talks Conference 2022</a></p>
    <p>Join the discussion at <a href="https://oneiress.slack.com/archives/C040VRMT64U/p1662099674315709">Slack</a>.</p>
  </AfterComicBox>
</template>