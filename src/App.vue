<script setup>
import { TreeMapComponent as EjsTreemap,TreeMapLegend,TreeMapTooltip ,TreeMapHighlight,TreeMapSelection} from "@syncfusion/ej2-vue-treemap";
import { provide } from 'vue';

provide('treemap', [TreeMapLegend, TreeMapTooltip,TreeMapHighlight,TreeMapSelection]);
const dataSource = [
    {country: 'United States',sales: 19400},
    {country: 'Japan',sales: 4400},
    {country:"Brazil", sales:1774},
    {country: 'Germany',sales: 3240},
    {country: 'Canada',sales: 19240},
    {country:"France", sales:2421},
    {country: 'Mexico', sales: 16980},
    {country:"China", sales:10550},
    {country:"India", sales:2073},
    {country:"Italy", sales:1814}
    
]

const leafItemSettings = {
  labelPath: "country",
  colorMapping:[
        { from:1, to:2000, color:'#C84B4B' },
       {
           from:2000,
           to:4000,
           color:'#8C304D'
       },
       {
           from:4000,
           to:20000,
           color:'#4B134F'
       }
    ]}
    const legendSettings = {
    visible: true  
};
const tooltipSettings = {
    visible: true
};
const  titleSettings= {
            text: 'Top 10 Countries by Sales',
        }
const highlightSettings = {
    enable: true
   
};
const selectionSettings = {
    enable: true
};
</script>

<template>
  
 <ejs-treemap 
  :dataSource="dataSource" weightValuePath="sales"  :leafItemSettings="leafItemSettings"
  rangeColorValuePath="sales" :legendSettings='legendSettings' :tooltipSettings='tooltipSettings'
  :titleSettings='titleSettings' :highlightSettings='highlightSettings'
  :selectionSettings='selectionSettings'></ejs-treemap>

</template>

<style>

</style>
