<template>
  <div>

    <base-header class="pb-6 pb-8 pt-5 pt-md-8 bg-gradient-success">
      <!-- Card stats -->
      <b-row>
        <b-col xl="3" md="6">
          <stats-card title="实时人数"
                      type="gradient-red"
                      sub-title="78"
                      icon="ni ni-air-baloon"
                      class="mb-4">

            <template slot="footer">
              <span class="text-success mr-2">2.98%</span>
              <span class="text-nowrap">相比于一个小时前</span>
            </template>
          </stats-card>
        </b-col>
        <b-col xl="3" md="6">
          <stats-card title="进入监控区域人数"
                      type="gradient-orange"
                      sub-title="56"
                      icon="ni ni-bold-right"
                      class="mb-4">

            <template slot="footer">
              <span class="text-success mr-2">10.97%</span>
              <span class="text-nowrap">相比于一个小时前</span>
            </template>
          </stats-card>
        </b-col>
        <b-col xl="3" md="6">
          <stats-card title="离开监控区域人数"
                      type="gradient-green"
                      sub-title="24"
                      icon="ni ni-bold-left"
                      class="mb-4">

            <template slot="footer">
              <span class="text-danger mr-2">5.72%</span>
              <span class="text-nowrap">相比于一个小时前</span>
            </template>
          </stats-card>

        </b-col>
        <b-col xl="3" md="6">
          <stats-card title="平均停留时间 (s)"
                      type="gradient-info"
                      sub-title="37.8"
                      icon="ni ni-time-alarm"
                      class="mb-4">

            <template slot="footer">
              <span class="text-success mr-2">24.8%</span>
              <span class="text-nowrap">相比于一个小时前</span>
            </template>
          </stats-card>
        </b-col>
      </b-row>
    </base-header>

    <!--Charts-->
    <b-container fluid class="mt--7">
      <b-row>
        <b-col xl="8" class="mb-5 mb-xl-0">
          <card type="default" header-classes="bg-transparent">
            <b-row align-v="center" slot="header">
              <b-col>
                <h6 class="text-light text-uppercase ls-1 mb-1">数据分析</h6>
                <h5 class="h3 text-white mb-0">人数变化曲线图</h5>
              </b-col>
              <b-col>
                <b-nav class="nav-pills justify-content-end">
                  <b-nav-item
                       class="mr-2 mr-md-0"
                       :active="bigLineChart.activeIndex === 0"
                       link-classes="py-2 px-3"
                       @click.prevent="initBigChart(0)">
                      <span class="d-none d-md-block">昨天</span>
                      <span class="d-md-none">M</span>
                  </b-nav-item>
                  <b-nav-item
                    link-classes="py-2 px-3"
                    :active="bigLineChart.activeIndex === 1"
                    @click.prevent="initBigChart(1)"
                  >
                    <span class="d-none d-md-block">前天</span>
                    <span class="d-md-none">W</span>
                  </b-nav-item>
                </b-nav>
              </b-col>
            </b-row>
            <line-chart
              :height="350"
              ref="bigChart"
              :chart-data="bigLineChart.chartData"
              :extra-options="bigLineChart.extraOptions"
            >
            </line-chart>
          </card>
        </b-col>

        <b-col xl="4" class="mb-5 mb-xl-0">
          <card header-classes="bg-transparent">
            <b-row align-v="center" slot="header">
              <b-col>
                <h6 class="text-uppercase text-muted ls-1 mb-1">数据分析</h6>
                <h5 class="h3 mb-0">总人数</h5>
              </b-col>
            </b-row>

            <bar-chart
              :height="350"
              ref="barChart"
              :chart-data="redBarChart.chartData"
            >
            </bar-chart>
          </card>
        </b-col>
      </b-row>
      <!-- End charts-->

      <!--Tables-->
      <!-- <b-row class="mt-5">
        <b-col xl="8" class="mb-5 mb-xl-0">
          <page-visits-table></page-visits-table>
        </b-col>
        <b-col xl="4" class="mb-5 mb-xl-0">
          <social-traffic-table></social-traffic-table>
        </b-col>
      </b-row> -->
      <!--End tables-->
    </b-container>

  </div>
</template>
<script>
  // Charts
  import * as chartConfigs from '@/components/Charts/config';
  import LineChart from '@/components/Charts/LineChart';
  import BarChart from '@/components/Charts/BarChart';

  // Components
  import BaseProgress from '@/components/BaseProgress';
  import StatsCard from '@/components/Cards/StatsCard';

  // Tables
  // import SocialTrafficTable from './Dashboard/SocialTrafficTable';
  // import PageVisitsTable from './Dashboard/PageVisitsTable';

  export default {
    components: {
      LineChart,
      BarChart,
      BaseProgress,
      StatsCard,
      // PageVisitsTable,
      // SocialTrafficTable
    },
    data() {
      return {
        bigLineChart: {
          allData: [
            [18, 3, 2, 13, 42, 60, 78, 67, 34],
            [23, 9, 0, 23, 49, 90, 69, 78, 40]
          ],
          activeIndex: 0,
          chartData: {
            datasets: [
              {
                label: '人数',
                data: [18, 3, 2, 13, 42, 60, 78, 67, 34],
              }
            ],
            labels: ['0:00', '3:00', '6:00', '9:00', '12:00', '15:00', '18:00', '21:00'],
          },
          extraOptions: chartConfigs.blueChartOptions,
        },
        redBarChart: {
          chartData: {
            labels: ['周一', '周二', '周三', '周四', '周五', '周六', '周日'],
            datasets: [{
              label: '总人数',
              data: [316, 283, 297, 301, 317, 295, 289]
            }]
          },
          extraOptions: chartConfigs.blueChartOptions
        }
      };
    },
    methods: {
      initBigChart(index) {
        let chartData = {
          datasets: [
            {
              label: '人数',
              data: this.bigLineChart.allData[index]
            }
          ],
          labels: ['0:00', '3:00', '6:00', '9:00', '12:00', '15:00', '18:00', '21:00'],
        };
        this.bigLineChart.chartData = chartData;
        this.bigLineChart.activeIndex = index;
      }
    },
    mounted() {
      this.initBigChart(0);
    }
  };
</script>
<style>
.el-table .cell{
  padding-left: 0px;
  padding-right: 0px;
}
</style>
