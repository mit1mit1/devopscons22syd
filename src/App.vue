<script setup lang="ts">
import IntroComic from './comics/IntroComic.vue';
import SupplyChainVulnerabilities from './comics/SupplyChainVulnerabilities.vue';
import SoftwareArchitectureOverview from './comics/SoftwareArchitectureOverview.vue';
import SoftwareArchitectureMicroservices from './comics/SoftwareArchitectureMicroservices.vue';
import SoftwareArchitectureMicrofrontends from './comics/SoftwareArchitectureMicrofrontends.vue';
import { getComicNumber } from './vue-comic-components/utils/comicNumber';
import DoraReport2021 from './comics/DoraReport2021.vue';
const comicList = [
  'intro',
  'supply-chain-vulnerabilities',
  'dora-report-2021',
  'software-architecture-overview',
  'software-architecture-microservices',
  'software-architecture-microfrontends',
]
const comicNumber = getComicNumber(comicList);
</script>

<template>
  <main>
    <h1>Software Dev Resources</h1>
    <IntroComic v-if="comicNumber == comicList.indexOf('intro')" :comicList="comicList" />
    <SupplyChainVulnerabilities :comicList="comicList"
      v-else-if="comicNumber == comicList.indexOf('supply-chain-vulnerabilities')" />
    <DoraReport2021 :comicList="comicList" v-else-if="comicNumber == comicList.indexOf('dora-report-2021')" />
    <SoftwareArchitectureOverview :comicList="comicList"
      v-else-if="comicNumber == comicList.indexOf('software-architecture-overview')" />
    <SoftwareArchitectureMicroservices :comicList="comicList"
      v-else-if="comicNumber == comicList.indexOf('software-architecture-microservices')" />
    <SoftwareArchitectureMicrofrontends :comicList="comicList"
      v-else-if="comicNumber == comicList.indexOf('software-architecture-microfrontends')" />
    <div v-else>Sorry, no comic at this address.</div>
  </main>
</template>

<style>
@import "./themes/global.css";
@import "./themes/light.css";

h1 {
  text-align: center;
  font-family: monospace;
  font-weight: normal;
}

html {
  background-color: #eee;
}
</style>
