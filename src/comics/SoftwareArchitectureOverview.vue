<script setup lang="ts">
import { toRefs } from "vue";
import { marked } from "marked";
import MarkdownBox from '../vue-comic-components/components/MarkdownBox.vue';
import ComicTitle from '../vue-comic-components/components/ComicTitle.vue';
import NavigationBar from '../vue-comic-components/components/NavigationBar.vue';
import { ref } from 'vue'
const SoftwareIntroMd = ref('');

import("../../notesMd/softwareArchitecture/broadOverview.md").then(res => {
    fetch(res.default)
        .then(response => response.text())
        .then(text => SoftwareIntroMd.value = text)
});
const props = defineProps<{
    comicList: Array<string>;
}>();
const { comicList } = toRefs(props);
</script>

<template>
    <ComicTitle>Introduction to Software Architecture</ComicTitle>
    <NavigationBar :comicList="comicList" />
    <MarkdownBox>
        <span v-html="marked.parse(SoftwareIntroMd)"></span>
    </MarkdownBox>
    <NavigationBar :comicList="comicList" />
</template>
