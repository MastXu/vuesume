<!-- 每个内容模块的title -->

<template>
    <div class="skeleton" v-if="display">
        <a-skeleton v-for="num in seq" v-bind:key="num" data-aos="fade-right" active avatar :paragraph="{rows: 3}"/>
    </div>
</template>

<script lang="ts">
    import {Component, Vue} from 'vue-property-decorator';
    import _ from 'lodash';

    @Component({
        props: {
            display: Boolean,
            number: Number
        },
        computed: {
            seq() {
                return _.times((this as any).number);
            },
        },
    })
    export default class ModuleSkeleton extends Vue {
    }
</script>

<style scoped lang="scss">
    @import '../../styles/variable';
</style>
