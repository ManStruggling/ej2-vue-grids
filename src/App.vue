<template>
  <div id="app">
    <ejs-grid
      :dataSource="data"
      :allowSorting="true"
      :allowFiltering="true"
      :allowGrouping="true"
    >
      <e-columns>
        <e-column
          field="Inventor"
          headerText="Inventor Name"
          width="190"
        ></e-column>
        <e-column
          field="NumberofPatentFamilies"
          headerText="No of Patent Families"
          width="120"
        ></e-column>
        <e-column
          field="Country"
          headerText="Country"
          type="string"
          :enableGroupByFormat="true"
          :formatter="
            (column, data) => (data.Country === 'Australia' ? 'Aus' : 'Other')
          "
          width="90"
        ></e-column>
        <e-column field="Active" headerText="Active" width="120"></e-column>
        <e-column
          field="Mainfieldsofinvention"
          headerText="Main fields of invention"
          width="200"
        ></e-column>
      </e-columns>
    </ejs-grid>
  </div>
</template>
<script>
import Vue from "vue";
import {
  GridPlugin,
  Sort,
  Filter,
  Group,
} from "@syncfusion/ej2-vue-grids";

Vue.use(GridPlugin);

export default {
  data: function () {
    return {
      data: [
        {
          Inventor: "Kia Silverbrook",
          NumberofPatentFamilies: 4737,
          Country: "Australia",
          "Number of INPADOC patents": 9839,
          Active: "1994-2016",
          createTime: "2021-08-10 12:30:42",
          Mainfieldsofinvention:
            "Printing, Digital paper, Internet, Electronics,Lab-on-a-chip, MEMS, Mechanical, VLSI",
        },

        {
          Inventor: "Shunpei Yamazaki",
          NumberofPatentFamilies: 4677,
          Country: "Japan",
          "Number of INPADOC patents": "10000+",
          Active: "1976-2016",
          createTime: "2021-08-10 12:30:42",
          Mainfieldsofinvention:
            "Thin film transistors, Liquid crystal displays, Solar cells, Flash memory, OLED",
        },

        {
          Inventor: "Lowell L. Wood, Jr.",
          NumberofPatentFamilies: 1419,
          Country: "USA",
          "Number of INPADOC patents": 1332,
          Active: "1977-2016",
          createTime: "2021-08-10 12:30:42",
          Mainfieldsofinvention: "Mosquito laser, Nuclear weapons",
        },

        {
          Inventor: "Paul Lapstun",
          NumberofPatentFamilies: 1281,
          Country: "Australia",
          "Number of INPADOC patents": 3099,
          Active: "2000-2016",
          createTime: "2021-08-10 12:30:42",
          Mainfieldsofinvention:
            "Printing, Digital paper, Internet, Electronics, CGI, VLSI",
        },

        {
          Inventor: "Gurtej Sandhu",
          NumberofPatentFamilies: 1255,
          Country: "India",
          "Number of INPADOC patents": 2038,
          Active: "1991-2016",
          createTime: "2021-08-10 12:30:42",
          Mainfieldsofinvention:
            "Thin film processes and materials, VLSI, Semiconductor device fabrication",
        },

        {
          Inventor: "Jun Koyama",
          NumberofPatentFamilies: 1240,
          Country: "Japan",
          "Number of INPADOC patents": 4126,
          Active: "1991-2016",
          createTime: "2021-08-10 12:30:42",
          Mainfieldsofinvention:
            "Thin film transistors, Liquid crystal displays, OLED",
        },
      ],
    };
  },
  provide: {
    grid: [Sort, Filter, Group],
  },
};
</script>
<style>
@import "../node_modules/@syncfusion/ej2-vue-grids/styles/material.css";
</style>