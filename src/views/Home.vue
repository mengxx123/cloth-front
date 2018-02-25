<template>
    <my-page title="标准尺码对照表">
        <ul>
            <li v-for="group in groups">
                <h2 class="group-title">{{ group.name }}</h2>
                <ul class="type-list">
                    <li class="item" v-for="type in group.types">
                        <router-link class="link" :to="'cloth/' + type.id">
                            <ui-icon class="icon" :value="':icon icon-' + type.icon" />
                            <h3 class="title">{{ type.name }}</h3>
                        </router-link>
                    </li>
                </ul>
            </li>
        </ul>
    </my-page>
</template>

<script>
    /* eslint-disable */
    export default {
        data () {
            return {
                groups: [
                    {
                        name: '女装',
                        types: [
                            {
                                id: '1',
                                name: '女装',
                                icon: 'female'
                            },
                            {
                                id: '2',
                                name: '衬衫',
                                icon: 'shirt'
                            },
                            {
                                id: '3',
                                name: '连衣裙',
                                icon: 'skirt'
                            },
                            {
                                id: '4',
                                name: '裤子',
                                icon: 'pants'
                            },
                            {
                                id: '5',
                                name: '文胸',
                                icon: 'bras'
                            },
                            {
                                id: '6',
                                name: '内裤',
                                icon: 'underpants'
                            }
                        ]
                    },
                    {
                        name: '男装',
                        types: [
                            {
                                id: '21',
                                name: '男装',
                                icon: 'shirt'
                            },
                            {
                                id: '22',
                                name: '衬衫',
                                icon: 'shirt'
                            },
                            {
                                id: '23',
                                name: '西装',
                                icon: 'suit'
                            },
                            {
                                id: '24',
                                name: '裤子',
                                icon: 'pants'
                            },
                            {
                                id: '25',
                                name: '内裤',
                                icon: 'underpants'
                            }
                        ]
                    },
                    {
                        name: '童装',
                        types: [
                            {
                                id: '31',
                                name: '童装',
                                icon: 'children'
                            },
                            {
                                id: '32',
                                name: '婴童',
                                icon: 'children'
                            },
                            {
                                id: '33',
                                name: '中童',
                                icon: 'children'
                            },
                            {
                                id: '34',
                                name: '大童',
                                icon: 'children'
                            }
                        ]
                    },
                    {
                        name: '其他',
                        types: [
                            {
                                id: '41',
                                name: '鞋码',
                                icon: 'shoes'
                            }
                        ]
                    }
                ]
            }
        },
        mounted() {
        }
    }
</script>

<style lang="scss" scoped>
    @import '../scss/var';

    .group-title {
        font-size: 16px;
        margin-bottom: 16px;
    }
    .type-list {
        @include clearfix;
        .item {
            float: left;
            width: 80px;
            height: 80px;
            margin-right: 16px;
            margin-bottom: 16px;
            background-color: #fff;
            box-shadow: 0 1px 6px rgba(0,0,0,.117647), 0 1px 4px rgba(0,0,0,.117647);
        }
        .link {
            display: block;
            width: 100%;
            height: 100%;
            padding: 16px 16px;
            color: inherit;
            text-align: center;
        }
        .icon {
            font-size: 32px;
            line-height: 1;
            margin-bottom: 4px;
        }
        .title {
        }
    }
</style>
