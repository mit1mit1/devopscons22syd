<script setup lang="ts">
import IntroComic from './comics/IntroComic.vue';
import SupplyChainVulnerabilities from './comics/SupplyChainVulnerabilities.vue';
import { getComicNumber } from './vue-comic-components/utils/comicNumber';
import DoraReport from './comics/DoraReport.vue';
const comicList = ['intro', 'supply_chain_vulnerabilities', 'dora_report']
const comicNumber = getComicNumber(comicList);
</script>
  
<template>
  <main>
    <h1>DevOpsCon Sydney, 2022</h1>
    <IntroComic v-if="comicNumber == comicList.indexOf('intro')" :comicList="comicList" />
    <SupplyChainVulnerabilities :comicList="comicList"
      v-else-if="comicNumber == comicList.indexOf('supply_chain_vulnerabilities')" />
    <DoraReport :comicList="comicList"
      v-else-if="comicNumber == comicList.indexOf('dora_report')" />
    <div v-else>Sorry, no comic at this address.</div>
  </main>
</template>
  
<style>
h1 {
  text-align: center;
  font-family: monospace;
  font-weight: normal;
}

html {
  background-color: #eee;
}
</style>
  