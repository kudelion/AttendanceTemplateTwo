<template>
  <div class="content">
    <div class="container-fluid">
      <div class="row">
        <div class="col-xl-3 col-md-6">
          <stats-card>
            <div slot="header" class="icon-warning">
              <i class="nc-icon nc-button-play text-success"></i>
            </div>
            <div slot="content">
              <p class="card-category">Days present</p>
              <h4 class="card-title">74 days</h4>
            </div>
            <div slot="footer">
              <i class="fa fa-refresh"></i>Total days
            </div>
          </stats-card>
        </div>

        <div class="col-xl-3 col-md-6">
          <stats-card>
            <div slot="header" class="icon-success">
              <i class="nc-icon nc-button-pause text-warning"></i>
            </div>
            <div slot="content">
              <p class="card-category">Days absent</p>
              <h4 class="card-title">12 days</h4>
            </div>
            <div slot="footer">
              <i class="fa fa-calendar-o"></i>6 days allowed absence
            </div>
          </stats-card>
        </div>

        <div class="col-xl-3 col-md-6">
          <stats-card>
            <div slot="header" class="icon-danger">
              <i class="nc-icon nc-time-alarm text-success"></i>
            </div>
            <div slot="content">
              <p class="card-category">Total days</p>
              <h4 class="card-title">86 days</h4>
            </div>
            <div slot="footer">
              <i class="fa fa-clock-o"></i>14 days to go
            </div>
          </stats-card>
        </div>

        <div class="col-xl-3 col-md-6">
          <stats-card>
            <div slot="header" class="icon-info">
              <i class="nc-icon nc-favourite-28 text-success"></i>
            </div>
            <div slot="content">
              <p class="card-category">status</p>
              <h4 class="card-title">ACTIVE</h4>
            </div>
            <div slot="footer">
              <i class="fa fa-refresh"></i>Regular 
            </div>
          </stats-card>
        </div>
      </div>

      <card>
        <h5>TIME-IN/OUT</h5>
        <form>
          <div class="row">
           <!-- Clock display -->            
            <div class="col-md-3">
              <VueClock />
            </div>
            <!-- Button for Time in and out -->            
            <div class="col-md-3">
              <div class="d-grid gap-2 col-8 mx-2 py-2">
                <button type="submit" 
                  class="btn btn-danger btn-fill btn-lg my-1 py-1 text-center" 
                  v-for="toggle in statusItem" :key="toggle.id" 
                  v-on:click="InputItem = toggle.item">
                        {{toggle.status}}
                </button>
              </div>
            </div>
            <!-- Status display -->  
            <div class="col-md-6">
              <h5>STATUS</h5>
              <h2><strong>{{InputItem}}</strong></h2>
            </div>
          </div>
        </form>
      </card>
    </div>
  </div> 
</template>
<script>
  import ChartCard from 'src/components/Cards/ChartCard.vue'
  import StatsCard from 'src/components/Cards/StatsCard.vue'
  import LTable from 'src/components/Table.vue'

  import VueClock from '@dangvanthanh/vue-clock'

  export default {
    components: {
      LTable,
      ChartCard,
      StatsCard,
      VueClock 
    },
    data () {
      return {
        InputItem: ' ',
                statusItem: [
                    {status:'Clock-In', item: 'Clock-In'},
                    {status:'Clock-Out', item: 'Clock-Out'}
                ],

        editTooltip: 'Edit Task',
        deleteTooltip: 'Remove',
        pieChart: {
          data: {
            labels: ['40%', '20%', '40%'],
            series: [40, 20, 40]
          }
        },
        lineChart: {
          data: {
            labels: ['9:00AM', '12:00AM', '3:00PM', '6:00PM', '9:00PM', '12:00PM', '3:00AM', '6:00AM'],
            series: [
              [287, 385, 490, 492, 554, 586, 698, 695],
              [67, 152, 143, 240, 287, 335, 435, 437],
              [23, 113, 67, 108, 190, 239, 307, 308]
            ]
          },
          options: {
            low: 0,
            high: 800,
            showArea: false,
            height: '245px',
            axisX: {
              showGrid: false
            },
            lineSmooth: true,
            showLine: true,
            showPoint: true,
            fullWidth: true,
            chartPadding: {
              right: 50
            }
          },
          responsiveOptions: [
            ['screen and (max-width: 640px)', {
              axisX: {
                labelInterpolationFnc (value) {
                  return value[0]
                }
              }
            }]
          ]
        },
        barChart: {
          data: {
            labels: ['Jan', 'Feb', 'Mar', 'Apr', 'Mai', 'Jun', 'Jul', 'Aug', 'Sep', 'Oct', 'Nov', 'Dec'],
            series: [
              [542, 443, 320, 780, 553, 453, 326, 434, 568, 610, 756, 895],
              [412, 243, 280, 580, 453, 353, 300, 364, 368, 410, 636, 695]
            ]
          },
          options: {
            seriesBarDistance: 10,
            axisX: {
              showGrid: false
            },
            height: '245px'
          },
          responsiveOptions: [
            ['screen and (max-width: 640px)', {
              seriesBarDistance: 5,
              axisX: {
                labelInterpolationFnc (value) {
                  return value[0]
                }
              }
            }]
          ]
        },
        tableData: {
          data: [
            {title: 'Sign contract for "What are conference organizers afraid of?"', checked: false},
            {title: 'Lines From Great Russian Literature? Or E-mails From My Boss?', checked: true},
            {
              title: 'Flooded: One year later, assessing what was lost and what was found when a ravaging rain swept through metro Detroit',
              checked: true
            },
            {title: 'Create 4 Invisible User Experiences you Never Knew About', checked: false},
            {title: 'Read "Following makes Medium better"', checked: false},
            {title: 'Unfollow 5 enemies from twitter', checked: false}
          ]
        }
      }
    }
  }
</script>
<style>

</style>
