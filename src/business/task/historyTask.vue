<template>
    <div class="history-task">
        <div class="history-task-item task-list-piece" v-for="item in list">
            <div class="head-info">
                <div class="name">{{ item.name }}</div>
                <div class="status">{{ item.statusDesc }}</div>
            </div>
            <div class="task-item-container">
                <div class="task-container-item">活跃度：{{ item.activity }}</div>
                <div class="task-container-item">兑换所需：{{ item.needSugar }}</div>
                <div class="task-container-item">奖励糖果：{{ item.rewardSugar }}</div>
                <div class="task-container-item">任务周期：{{ item.dateTime }}</div>
                <div class="task-container-item">任务编号：{{ item.code }}</div>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        name: 'history-task',
        data() {
            return {
                list: [
                    {
                        name: '试炼任务',
                        statusDesc: '已过期',
                        activity: 1,
                        hanselActivity: 2,
                        needSugar: 10,
                        rewardSugar: 11,
                        hanselSugar: 2,
                        dateTime: '2018.06.10-2018.06.10',
                        code: 'xddsdh324354657'
                    },
                    {
                        name: '试炼任务',
                        statusDesc: '已完成',
                        activity: 1,
                        hanselActivity: 2,
                        needSugar: 10,
                        rewardSugar: 11,
                        hanselSugar: 2,
                        dateTime: '2018.06.10-2018.06.10',
                        code: 'xddsdh324354657'
                    },
                    {
                        name: '试炼任务',
                        statusDesc: '已完成',
                        activity: 1,
                        hanselActivity: 2,
                        needSugar: 10,
                        rewardSugar: 11,
                        hanselSugar: 2,
                        dateTime: '2018.06.10-2018.06.10',
                        code: 'xddsdh324354657'
                    }
                ]
            }
        }
    }
</script>

<style lang="scss">
    .history-task {
        width: 690px;
        margin: 0 auto;
        .history-task-item {
            margin-top: 20px;
            .head-info {
                display: flex;
                justify-content: space-between;
                .name {
                    font-size: 32px;
                    line-height: 32px;
                }
                .step-info {
                    font-size: 30px;
                    line-height: 30px;
                    margin-top: 1px;
                }
            }
            .task-item-container {
                margin-top: 40px;
                .task-container-item {
                    margin-bottom: 20px;
                    font-size: 24px;
                    line-height: 24px;
                    &:nth-last-child(1) {
                        margin-bottom: 0;
                    }
                    .hansel {
                        display: inline-block;
                        color: #62c627;
                    }
                }
            }
        }
    }
</style>
