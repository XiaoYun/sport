<template>
    <div class="home">
        <l-head>
            首页
        </l-head>
        <div class="home-container">
            <div class="home-head">
                <l-banner/>
            </div>
            <div class="home-notice">
                <div class="left-icons pull-left">
                    <l-icon name="tongzhi-"/>
                </div>
                <div class="right-container">
                    您的俱乐部有新成员加入...
                </div>
            </div>
            <div class="short-menu">
                <div class="short-menu-item text-center" v-for="item in shortMenuList"
                     @click="toShortMenu(item.router)">
                    <l-icon :name="item.icons" class="short-menu-icon"/>
                    <div class="short-menu-label">{{ item.name }}</div>
                </div>
            </div>
            <div class="step-container">
                <div class="left-people">
                    <img src="static/img/home/men.png" alt="">
                </div>
                <div class="right-step-info text-center" @click="showStepDetails">
                    <div class="step-num-info">
                        {{ stepNum }} <span class="steps">步</span>
                    </div>
                    <div class="step-heat">{{ stepHeat }} Kal</div>
                </div>
            </div>
            <div class="reward-info text-center">奖励糖果:{{ rewardNum }}</div>
            <div class="user-basic-info">
                <div class="text-center user-basic-info-list">
                    <div class="basic-info-value isVip">{{ 'Lv.'+vipLevel }}</div>
                    <div class="basic-info-label">会员等级</div>
                </div>
                <div class="text-center user-basic-info-list">
                    <div class="basic-info-value">{{ activity }}</div>
                    <div class="basic-info-label">活跃度</div>
                </div>
                <div class="text-center user-basic-info-list">
                    <div class="basic-info-value">{{ totalReward }}</div>
                    <div class="basic-info-label">总糖果</div>
                </div>
                <div class="text-center user-basic-info-list">
                    <div class="basic-info-value">{{ contribution }}</div>
                    <div class="basic-info-label">贡献值</div>
                </div>
            </div>
        </div>
        <l-footerMenu :currentRoute.sync="route"/>
    </div>
</template>

<script>
    let _this
    export default {
        name: 'home',
        data() {
            return {
                route: 'home',
                shortMenuList: [],
                stepNum: 26984,
                stepHeat: 256,
                rewardNum: '1.032132187784',
                vipLevel: 1,
                activity: 50,
                totalReward: 150,
                contribution: 1500,
            }
        },
        mounted() {
            _this = this
            _this.getShortMenuList()
        },
        methods: {
            getShortMenuList() {
                _this.shortMenuList = [
                    {
                        router: 'teamList',
                        name: '组队',
                        icons: 'zudui'
                    },
                    {
                        router: 'task',
                        name: '任务',
                        icons: 'renwu'
                    },
                    {
                        router: 'activity',
                        name: '活动',
                        icons: 'huodong'
                    },
                    {
                        router: 'newsList',
                        name: '资讯',
                        icons: 'zixun'
                    }
                ]
            },
            showStepDetails() {
                this.$router.push('stepDetails')
            },
            toShortMenu(router) {
                this.$router.push(router)
            }
        }
    }
</script>

<style lang="scss">
    .home {
    
    }
    
    .home-container {
        overflow: hidden;
        .home-head {
            width: 750px;
            .head-img {
                width: 750px;
            }
        }
        .home-notice {
            line-height: 24px;
            font-size: 24px;
            padding: 28px 30px;
            .left-icons {
                margin-right: 30px;
                .icons {
                    width: 24px;
                    height: 24px;
                }
            }
        }
        .short-menu {
            padding: 40px 0 50px;
            width: calc(100% - 60px);
            border-bottom: 1px solid #000000;
            margin: 0 auto;
            .short-menu-item {
                width: 25%;
                display: inline-block;
                .short-menu-icon {
                    width: 60px;
                    height: 60px;
                }
                .short-menu-label {
                    font-size: 30px;
                    line-height: 30px;
                    margin-top: 20px;
                }
            }
        }
        .step-container {
            padding: 50px 40px 60px 80px;
            display: flex;
            justify-content: space-between;
            .left-people {
                width: 191px;
                height: 314px;
                margin-top: 20px;
                img {
                    width: 191px;
                    height: 314px;
                }
            }
            .right-step-info {
                width: 330px;
                height: 330px;
                -webkit-border-radius: 100%;
                -moz-border-radius: 100%;
                border-radius: 100%;
                border: 10px solid #d7dce6;
                .step-num-info {
                    width: 230px;
                    padding-bottom: 10px;
                    margin: 102px auto 0;
                    border-bottom: 4px solid #666666;
                    color: #FFD554;
                    overflow: hidden;
                    font-size: 60px;
                    line-height: 60px;
                    .steps {
                        font-size: 30px;
                        line-height: 30px;
                        display: inline-block;
                    }
                }
                .step-heat {
                    font-size: 30px;
                    line-height: 30px;
                    margin-top: 14px;
                }
            }
        }
        .reward-info {
            font-size: 28px;
            line-height: 28px;
            color: #ffd554;
        }
        .user-basic-info {
            margin-top: 50px;
            padding: 0 40px 0 40px;
            display: flex;
            justify-content: space-between;
            text-align: center;
            .user-basic-info-list {
                width: 120px;
                .basic-info-value {
                    margin-bottom: 20px;
                    height: 48px;
                    line-height: 48px;
                    font-size: 48px;
                    &.isVip {
                        background: #ffd554;
                        color: #000000;
                        height: 40px;
                        line-height: 40px;
                        margin: 4px auto 24px;
                        font-size: 36px;
                        -webkit-border-radius: 25px;
                        -moz-border-radius: 25px;
                        border-radius: 25px;
                        width: 96px;
                    }
                }
                .basic-info-label {
                    font-size: 24px;
                    line-height: 24px;
                }
            }
        }
    }
</style>
