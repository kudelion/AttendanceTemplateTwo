<template>
  <div class="content">
    <div class="container-fluid">
      <div class="row">
        <div class="col-12">
          <card class="strpied-tabled-with-hover"
                body-classes="table-full-width table-responsive"
          >
            <template slot="header">
              <h4 class="card-title">Attendance Status</h4>
              <p class="card-category">Juan Dela Cruz</p>
            </template>
            <l-table class="table-hover table-striped"
                     :columns="table1.columns"
                     :data="table1.data">
            </l-table>
          </card>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
  import LTable from 'src/components/Table.vue'
  import Card from 'src/components/Cards/Card.vue'
  
  const tableColumns = ['date', 'class', 'clockin', 'clockout', 'status1']
  const tableData = [{
    date: '01-Jan-2023',
    class: 'Part-time',
    clockin: '1900',
    clockout: '2203',
    status1: 'Present'
  },
  {
    date: '02-Jan-2023',
    class: 'Part-time',
    clockin: '1901',
    clockout: '2205',
    status1: 'Present'
  },
  {
    date: '03-Jan-2023',
    class: 'Part-time',
    clockin: '1845',
    clockout: '2203',
    status1: 'Present'
  },
  {
    date: '04-Jan-2023',
    class: 'Part-time',
    clockin: '1910',
    clockout: '2243',
    status1: 'Present'
  },
  {
    date: '05-Jan-2023',
    class: 'Part-time',
    clockin: '-',
    clockout: '-',
    status1: 'Absent'
  },
  {
    date: '06-Jan-2023',
    class: 'Part-time',
    clockin: '1900',
    clockout: '2203',
    status1: 'Present'
  },
  {
    date: '07-Jan-2023',
    class: 'Part-time',
    clockin: '1901',
    clockout: '2205',
    status1: 'Present'
  },
  {
    date: '08-Jan-2023',
    class: 'Part-time',
    clockin: '1845',
    clockout: '2203',
    status1: 'Present'
  },
  {
    date: '09-Jan-2023',
    class: 'Part-time',
    clockin: '1910',
    clockout: '2243',
    status1: 'Present'
  },
  {
    date: '10-Jan-2023',
    class: 'Part-time',
    clockin: '1906',
    clockout: '2201',
    status1: 'Present'
  },
  {
    date: '11-Jan-2023',
    class: 'Part-time',
    clockin: '-',
    clockout: '-',
    status1: 'Absent'
  },    
]
  export default {
    components: {
      LTable,
      Card
    },
    data () {
      return {
        table1: {
          columns: [...tableColumns],
          data: [...tableData]
        },
        table2: {
          columns: [...tableColumns],
          data: [...tableData]
        }
      }
    }
  }
</script>
<style>
</style>
