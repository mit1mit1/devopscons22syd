<script setup lang="ts">
import BeanieMan from '../vue-comic-components/svgs/BeanieMan.vue';
import PanelBox from '../vue-comic-components/components/PanelBox.vue';
import ComicBox from '../vue-comic-components/components/ComicBox.vue';
import AfterComicBox from '../vue-comic-components/components/AfterComicBox.vue';
import ComicTitle from '../vue-comic-components/components/ComicTitle.vue';
import NavigationBar from '../vue-comic-components/components/NavigationBar.vue';
import { availableLimbPositions } from "../vue-comic-components/svgs/constants/limbPositions";
import { toRefs } from "vue";
const props = defineProps<{
  comicList: Array<string>;
}>();
const { comicList } = toRefs(props);
</script>

<template>
  <ComicTitle>Intro</ComicTitle>
  <NavigationBar :comicList="comicList" />
  <ComicBox>
    <PanelBox>
      <BeanieMan :minimumX="70" :minimumY="50" :limbPositions="availableLimbPositions.leftHandWave" />
      <text x="185" y="100">HEY THERE!</text>
      <text x="185" y="140">IF YOU'RE WONDERING</text>
      <text x="185" y="180">WHO THE STRANGE,</text>
      <text x="185" y="220">BEANIE-WEARING</text>
      <text x="185" y="260">STICK FIGURE IS,</text>
      <text x="185" y="300">I'M MITCH.</text>
    </PanelBox>

    <PanelBox>
      <BeanieMan :minimumX="50" :minimumY="50" :limbPositions="availableLimbPositions.rightHandPointUp" />
      <text x="185" y="100">"DEVOPS" IS AN</text>
      <text x="185" y="140">IDEA IN SOFTWARE</text>
      <text x="185" y="180">DEVELOPMENT. IT</text>
      <text x="185" y="220">SAYS "DEVELOPERS"</text>
      <text x="185" y="260">(WHO WRITE CODE)</text>
      <text x="185" y="300">AND "OPERATORS"</text>
      <text x="185" y="340">(WHO KEEP CODE</text>
      <text x="185" y="380">RUNNING) SHOULD</text>
      <text x="185" y="420">WORK CLOSELY.</text>
    </PanelBox>

    <PanelBox>
      <BeanieMan :minimumX="50" :minimumY="50" :limbPositions="availableLimbPositions.handsDown" />
      <text x="185" y="100">THIS IS MEANT TO</text>
      <text x="185" y="140">MAKE SOFTWARE</text>
      <text x="185" y="180">FASTER TO BUILD,</text>
      <text x="185" y="220">LESS LIKELY TO</text>
      <text x="185" y="260">BREAK, AND BETTER</text>
      <text x="185" y="300">TO USE.</text>
    </PanelBox>

    <PanelBox>
      <BeanieMan :minimumX="70" :minimumY="50" :limbPositions="availableLimbPositions.shrug" />
      <text x="205" y="100">OF COURSE, THERE</text>
      <text x="205" y="140">IS A WHOLE BUNCH</text>
      <text x="205" y="180">OF RELATED IDEAS</text>
      <text x="205" y="220">IN THE DEVOPS</text>
      <text x="205" y="260">MOVEMENT AS WELL.</text>
    </PanelBox>

    <PanelBox>
      <BeanieMan :minimumX="70" :minimumY="50" :limbPositions="availableLimbPositions.excited" />
      <text x="205" y="100">SO, HOPEFULLY, THE</text>
      <text x="205" y="140">TALK SUMMARIES'LL</text>
      <text x="205" y="180">GIVE YOU A GOOD</text>
      <text x="205" y="220">INTRO TO SOME OF</text>
      <text x="205" y="260">THOSE IDEAS!</text>
      <text x="205" y="300">AND SOME GOOD</text>
      <text x="205" y="340">PLACES TO LEARN</text>
      <text x="205" y="380">MORE IF YOU WANT.</text>
    </PanelBox>

    <PanelBox>
      <BeanieMan :minimumX="55" :minimumY="160" :lengthX="75" :lengthY="300"
        :limbPositions="availableLimbPositions.rightHandWave" />
      <text x="170" y="100">WITH THAT, ENJOY! I'M</text>
      <text x="170" y="140">A BIG FAN OF MAKING</text>
      <text x="170" y="180">COOL BUT COMPLEX</text>
      <text x="170" y="220">IDEAS EASIER TO</text>
      <text x="170" y="260">UNDERSTAND - </text>
      <text x="170" y="300">I'M HOPING THIS COMIC'LL</text>
      <text x="170" y="340">WILL DO THAT.</text>
      <text x="170" y="380">IF NOT, FEEDBACK IS</text>
      <text x="170" y="420">ALWAYS WELCOME!</text>
    </PanelBox>
  </ComicBox>
  <NavigationBar :comicList="comicList" />
  <AfterComicBox>
    <p>Hey hey, welcome to the first post-comic text! I'll stick any necessary explanations or useful links here. I'll
      also leave a link to a discussion thread. In this case:</p>
    <p>
      Join the discussion at <a
        href="https://www.reddit.com/r/mitt_comics/">Reddit</a>.
    </p>
    <p>See more about DevOpsCon at <a href="https://devops.talksplus.com/2022_Sydney/index.ht ml">their website</a></p>
    <p>And a huge thank you to my company <a href="https://www.linkedin.com/company/iress/">Iress</a> for taking a bunch
      of us along to the conference - hugely appreciated.</p>

    <p>
      P.S.: If you want to more of my (more humorous) work, check it out at
      <a target="_blank" rel="noreferrer" href="https://mit1mit1.github.io/">mit1mit1.github.io/</a> ;)
    </p>
  </AfterComicBox>
</template>
