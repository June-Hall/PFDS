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
    <!-- <b-container fluid class="mt--7">
      <b-row>
        <b-col>
          <light-table/>
        </b-col>
      </b-row>
      <div class="mt-5"></div>
      <dark-table></dark-table>
    </b-container> -->
  </div>
</template>
<script>
  import { Dropdown, DropdownItem, DropdownMenu, Table, TableColumn } from 'element-ui';
  import projects from './Tables/projects'
  import users from './Tables/users'
  import LightTable from "./Tables/RegularTables/LightTable";
  import DarkTable from "./Tables/RegularTables/DarkTable";

  export default {
    components: {
      LightTable,
      DarkTable,
      [Dropdown.name]: Dropdown,
      [DropdownItem.name]: DropdownItem,
      [DropdownMenu.name]: DropdownMenu,
      [Table.name]: Table,
      [TableColumn.name]: TableColumn
    },
    data() {
      return {
        projects,
        users
      };
    }
  };
</script>
<style>
.el-table.table-dark{
  background-color: #172b4d;
  color: #f8f9fe;
}

.el-table.table-dark th,
.el-table.table-dark tr{
  background-color: #172b4d;
}

.el-table.table-dark td,
.el-table.table-dark th.is-leaf{
  border-bottom: none;
}
</style>
