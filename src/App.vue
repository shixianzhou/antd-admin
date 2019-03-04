<template>
    <a-layout id="index">
        <a-layout-sider
                :trigger="null"
                collapsible
                v-model="collapsed"
        >
            <a-menu theme="light" mode="inline" :defaultSelectedKeys="['1']">
                <a-menu-item key="1">
                    <a-icon type="home"/>
                    <span>首页</span>
                </a-menu-item>
                <a-menu-item key="2">
                    <a-icon type="pushpin"/>
                    <span>引导</span>
                </a-menu-item>
                <a-sub-menu key="3">
                    <span slot="title"><a-icon type="smile"/><span>图标</span></span>
                    <a-menu-item key="3-1">antd图标</a-menu-item>
                    <a-menu-item key="3-2">iconfont</a-menu-item>
                </a-sub-menu>
                <a-menu-item key="4">
                    <a-icon type="block"/>
                    <span>frame</span>
                </a-menu-item>
                <a-menu-item key="5">
                    <a-icon type="environment"/>
                    <span>地图</span>
                </a-menu-item>
                <a-sub-menu key="6">
                    <span slot="title"><a-icon type="line-chart"/><span>图表</span></span>
                    <a-menu-item key="6-1">常见类型</a-menu-item>
                    <a-menu-item key="6-2">其他类型</a-menu-item>
                </a-sub-menu>
                <a-sub-menu key="7">
                    <span slot="title"><a-icon type="deployment-unit"/><span>功能</span></span>
                    <a-menu-item key="7-1">antd图标</a-menu-item>
                    <a-menu-item key="7-2">iconfont</a-menu-item>
                </a-sub-menu>
                <a-menu-item key="8">
                    <a-icon type="check-square"/>
                    <span>表单</span>
                </a-menu-item>
                <a-sub-menu key="9">
                    <span slot="title"><a-icon type="export"/><span>Export</span></span>
                    <a-menu-item key="9-1">导入表格</a-menu-item>
                    <a-menu-item key="9-2">导出表格</a-menu-item>
                </a-sub-menu>
            </a-menu>
        </a-layout-sider>
        <a-layout>
            <a-layout-header style="background: #fff; padding: 0">
                <a-icon
                        class="trigger"
                        :type="collapsed ? 'menu-unfold' : 'menu-fold'"
                        @click="()=> collapsed = !collapsed"
                />
            </a-layout-header>
            <a-layout-content :style="{ margin: '24px 16px', padding: '24px', background: '#fff', minHeight: '280px' }">
                <router-view id="view"></router-view>
            </a-layout-content>
        </a-layout>
    </a-layout>
</template>
<script>
    export default {
        name: 'index',
        data() {
            return {
                collapsed: false,
            }
        },
    }
</script>
<style lang="less" scoped>
    #index {
        width: 100%;
        height: 100%;
        overflow: hidden;

        .ant-layout-sider {
            background: #fff;
        }

        #view {
            width: 100%;
            height: 100%;
            overflow: auto;
            overflow-x: hidden;
            &::-webkit-scrollbar {/*滚动条整体样式*/
                width: 2px;     /*高宽分别对应横竖滚动条的尺寸*/
                height: 2px;
                display: none;
            }
            &::-webkit-scrollbar-thumb {/*滚动条里面小方块*/
                border-radius: 5px;
                -webkit-box-shadow: inset 0 0 5px rgba(0,0,0,0.2);
                background: rgba(0,0,0,0.2);
            }
            &::-webkit-scrollbar-track {/*滚动条里面轨道*/
                display: none;
            }
        }

        .ant-menu-inline {
            height: 100%;
            overflow: auto;
            overflow-x: hidden;

            &::-webkit-scrollbar {
                display: none;
            }
        }

        .ant-menu-inline-collapsed {
            height: 100%;
        }

        .trigger {
            font-size: 18px;
            line-height: 64px;
            padding: 0 24px;
            cursor: pointer;
            transition: color .3s;
        }
    }
</style>