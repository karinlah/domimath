<template>
  <div>
    <div class="row">
      <div class="col-lg-3 col-sm-6">
          <circle-chart-card :percentage="20"
                             title="גאומטריה אנליטית"
                             description="נקודות, ישרים, מעגל"
                             color="brown">
          </circle-chart-card>
      </div>

      <div class="col-lg-3 col-sm-6">
          <circle-chart-card :percentage="60"
                             title="גיאומטריה"
                             description="מעגל, פיתגורס, שטחים, תאלס, דמיון משולשים"
                             color="orange">
          </circle-chart-card>
      </div>

      <div class="col-lg-3 col-sm-6">
        <circle-chart-card @click.native='navigate()'
                            :percentage="90"
                            title="טריגונומטריה"
                            description="הרדיאן, מעגל היחידה, פונקציות tg, cos, sin, זהויות, משפט sin ומשפט cos"
                            color="green">
        </circle-chart-card>
      </div>

      <div class="col-lg-3 col-sm-6 ">
        <router-link :to="{name: 'חדוא'}">
        <circle-chart-card :percentage="34"
                           title="חדו״א"
                           description="מושג הגבול, נגזרות ושימושי משיק, בעיות קיצון,חקירת פונקציות, פונקציה קדומה"
                           color="brown">
        </circle-chart-card></router-link>
      </div>

      <div class="col-lg-3 col-sm-6 ">
        <circle-chart-card :percentage="62"
                           title="אלגברה"
                           description="אי שוויונים ממעלה ראשונה ושניה, חזקות ושורשים, בעיות מילוליות"
                           color="orange">
        </circle-chart-card>
      </div>
    </div>
  </div>
</template>
<script>
  import CircleChartCard from 'src/components/UIComponents/Cards/CircleChartCard.vue'
  import StatsCard from 'src/components/UIComponents/Cards/StatsCard.vue'
  import ChartCard from 'src/components/UIComponents/Cards/ChartCard.vue'
  import Loading from 'src/components/Dashboard/Layout/LoadingMainPanel.vue'

  const WorldMap = () => ({
    component: import('./../Maps/WorldMap.vue'),
    loading: Loading,
    delay: 200
  })

  export default {
    components: {
      StatsCard,
      ChartCard,
      CircleChartCard,
      WorldMap
    },
    /**
     * Chart data used to render stats, charts. Should be replaced with server data
     */
    data () {
      return {
        statsCards: [
          {
            type: 'warning',
            icon: 'ti-server',
            title: 'Capacity',
            value: '105GB',
            footerText: 'Updated now',
            footerIcon: 'ti-reload'
          },
          {
            type: 'success',
            icon: 'ti-wallet',
            title: 'Revenue',
            value: '$1,345',
            footerText: 'Last day',
            footerIcon: 'ti-calendar'
          },
          {
            type: 'danger',
            icon: 'ti-pulse',
            title: 'Errors',
            value: '23',
            footerText: 'In the last hour',
            footerIcon: 'ti-timer'
          },
          {
            type: 'info',
            icon: 'ti-twitter-alt',
            title: 'Followers',
            value: '+45',
            footerText: 'Updated now',
            footerIcon: 'ti-reload'
          }
        ],
        earningsChart: {
          data: {
            labels: ['Jan', 'Feb', 'Mar', 'April', 'May', 'June'],
            series: [
              [230, 340, 400, 300, 570, 500, 800]
            ]
          },
          options: {
            showPoint: false,
            lineSmooth: true,
            height: '210px',
            axisX: {
              showGrid: false,
              showLabel: true
            },
            axisY: {
              offset: 40,
              showGrid: false
            },
            low: 0,
            high: 'auto',
            classNames: {
              line: 'ct-line ct-green'
            }
          }
        }

      }
    },
    methods: {
      navigate () {

      }
    }
  }

</script>
<style>

</style>
