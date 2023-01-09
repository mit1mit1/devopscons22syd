<script setup lang="ts">
import IntroComic from './comics/IntroComic.vue';
import SupplyChainVulnerabilities from './comics/SupplyChainVulnerabilities.vue';
import { getComicNumber } from './vue-comic-components/utils/comicNumber';
import DoraReport2021 from './comics/DoraReport2021.vue';
import DoraReport2022 from './comics/DoraReport2022.vue';
const comicList = [
  'intro',
  'supply_chain_vulnerabilities',
  'dora_report_2021',
  // 'dora_report_2022',
]
const comicNumber = getComicNumber(comicList);
</script>

<template>
  <main>
    <h1>DevOpsCon Sydney, 2022</h1>
    <IntroComic v-if="comicNumber == comicList.indexOf('intro')" :comicList="comicList" />
    <SupplyChainVulnerabilities :comicList="comicList"
      v-else-if="comicNumber == comicList.indexOf('supply_chain_vulnerabilities')" />
    <DoraReport2021 :comicList="comicList" v-else-if="comicNumber == comicList.indexOf('dora_report_2021')" />
    <DoraReport2022 :comicList="comicList" v-else-if="comicNumber == comicList.indexOf('dora_report_2022')" />
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
