<template>
    <div id="app">
        <ejs-grid :dataSource="data" :showColumnChooser='true' :toolbar='toolbarOptions' height='272px'
        :allowPaging='true' :allowExcelExport='true' :allowPdfExport='true' :allowSorting='true'
        :contextMenuItems="contextMenuItems" :editSettings='editing' :allowGrouping='true'
        >
            <e-columns>
                <e-column field='OrderID' headerText='Order ID' width='120' textAlign="Right"></e-column>
                <e-column field='CustomerID' headerText='Customer Name' width='150' :showInColumnChooser='false'></e-column>
                <e-column field='Freight' headerText='Freight' :visible='false' width='120' format='C2' textAlign="Right"></e-column>
                <e-column field='ShipCountry' headerText='Ship Country' :visible='true' width='150'></e-column>
                <e-column field='ShipName' headerText='Ship Name' :visible='true' width='150'></e-column>
            </e-columns>
        </ejs-grid>
    </div>
</template>
<script>
import Vue from "vue";
//import { GridPlugin, ColumnChooser, Toolbar } from "@syncfusion/ej2-vue-grids";
import { GridPlugin, ColumnChooser, Toolbar, ContextMenu, Page, Resize, Sort, Group, Edit, PdfExport, ExcelExport } from "@syncfusion/ej2-vue-grids";
//import { data } from './data-source.js';

Vue.use(GridPlugin);

export default {
  data() {
    return {
      data: [{
    "OrderID": 10259,
    "CustomerID": "CENTC",
    "OrderDate": "1996-07-18T00:00:00.000Z",
    "ShippedDate": "1996-07-25T00:00:00.000Z",
    "Freight": 3.25,
    "ShipName": "군산호",
    "ShipAddress": "Sierras de Granada 9993",
    "ShipCity": "México D.F.",
    "ShipRegion": null,
    "ShipCountry": "Mexico",
    "Verified": true
},
{
    "OrderID": 10260,
    "CustomerID": "OTTIK",
    "OrderDate": "1996-07-19T00:00:00.000Z",
    "ShippedDate": "1996-07-29T00:00:00.000Z",
    "Freight": 55.09,
    "ShipName": "금성호",
    "ShipAddress": "Mehrheimerstr. 369",
    "ShipCity": "Köln",
    "ShipRegion": null,
    "ShipCountry": "Germany",
    "Verified": true
},
{
    "OrderID": 10261,
    "CustomerID": "QUEDE",
    "OrderDate": "1996-07-19T00:00:00.000Z",
    "ShippedDate": "1996-07-30T00:00:00.000Z",
    "Freight": 3.05,
    "ShipName": "충남호",
    "ShipAddress": "Rua da Panificadora, 12",
    "ShipCity": "Rio de Janeiro",
    "ShipRegion": "RJ",
    "ShipCountry": "Brazil"
},
{
    "OrderID": 10262,
    "CustomerID": "RATTC",
    "OrderDate": "1996-07-22T00:00:00.000Z",
    "ShippedDate": "1996-07-25T00:00:00.000Z",
    "Freight": 48.29,
    "ShipName": "상원호",
    "ShipAddress": "2817 Milton Dr.",
    "ShipCity": "Albuquerque",
    "ShipRegion": "NM",
    "ShipCountry": "USA",
    "Verified": true
},
{
    "OrderID": 10263,
    "CustomerID": "ERNSH",
    "OrderDate": "1996-07-23T00:00:00.000Z",
    "ShippedDate": "1996-07-31T00:00:00.000Z",
    "Freight": 146.06,
    "ShipName": "겨울호",
    "ShipAddress": "Kirchgasse 6",
    "ShipCity": "Graz",
    "ShipRegion": null,
    "Verified": true,
    "ShipCountry": "Austria"
},
{
    "OrderID": 10264,
    "CustomerID": "FOLKO",
    "OrderDate": "1996-07-24T00:00:00.000Z",
    "ShippedDate": "1996-08-23T00:00:00.000Z",
    "Freight": 3.67,
    "ShipName": "백두산호",
    "ShipAddress": "Åkergatan 24",
    "ShipCity": "Bräcke",
    "ShipRegion": null,
    "ShipCountry": "Sweden"
},
{
    "OrderID": 10265,
    "CustomerID": "BLONP",
    "OrderDate": "1996-07-25T00:00:00.000Z",
    "ShippedDate": "1996-08-12T00:00:00.000Z",
    "Freight": 55.28,
    "ShipName": "한라산호",
    "ShipAddress": "24, place Kléber",
    "ShipCity": "Strasbourg",
    "ShipRegion": null,
    "ShipCountry": "France"
},
{
    "OrderID": 10266,
    "CustomerID": "WARTH",
    "OrderDate": "1996-07-26T00:00:00.000Z",
    "ShippedDate": "1996-07-31T00:00:00.000Z",
    "Freight": 25.73,
    "ShipName": "한강호",
    "ShipAddress": "Torikatu 38",
    "ShipCity": "Oulu",
    "ShipRegion": null,
    "ShipCountry": "Finland"
},
{
    "OrderID": 10267,
    "CustomerID": "FRANK",
    "OrderDate": "1996-07-29T00:00:00.000Z",
    "ShippedDate": "1996-08-06T00:00:00.000Z",
    "Freight": 208.58,
    "ShipName": "울룽도호 ",
    "ShipAddress": "Berliner Platz 43",
    "ShipCity": "München",
    "ShipRegion": null,
    "ShipCountry": "Germany",
    "Verified": true
},
{
    "OrderID": 10268,
    "CustomerID": "GROSR",
    "OrderDate": "1996-07-30T00:00:00.000Z",
    "ShippedDate": "1996-08-02T00:00:00.000Z",
    "Freight": 66.29,
    "ShipName": "유비씨호",
    "ShipAddress": "5ª Ave. Los Palos Grandes",
    "ShipCity": "Caracas",
    "ShipRegion": "DF",
    "ShipCountry": "Venezuela"
}],
      toolbarOptions: ['ColumnChooser'],
  contextMenuItems: ['AutoFit', 'AutoFitAll', 'SortAscending', 'SortDescending',
                'Copy', 'Edit', 'Delete', 'Save', 'Cancel',
                'PdfExport', 'ExcelExport', 'CsvExport', 'FirstPage', 'PrevPage',
                'LastPage', 'NextPage', 'Group', 'Ungroup'],
      editing: {allowEditing: true, allowDeleting: true}
    };
  },
  provide: {
      grid: [ColumnChooser, Toolbar, ContextMenu, Page, Resize, Sort, Group, Edit, PdfExport, ExcelExport]
  }
}
</script>
<style>
 @import "../../node_modules/@syncfusion/ej2-vue-grids/styles/material.css";
</style>