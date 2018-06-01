<template>
  <div class="container">
    <h2 style="text-align: center">Sample Dashboard</h2>
    <br>
    <subHeader :widgetList="widgetList"></subHeader>
    <br><br>
    <widgetsRowWithCol6 :widgetList="widgetList"></widgetsRowWithCol6>
    <br>
    <widgetsRowWithCol4 :widgetList="widgetList"></widgetsRowWithCol4>
    <br>
    <widgetsRowWithCol3 :widgetList="widgetList"></widgetsRowWithCol3>
    <br>
    <widgetsRowWithCol12 :widgetList="widgetList"></widgetsRowWithCol12>
  </div>
</template>

<script>
import subHeader from './subHeader.vue'
import widgetsRowWithCol6 from './widgetsRowWithCol6.vue'
import widgetsRowWithCol4 from './widgetsRowWithCol4.vue'
import widgetsRowWithCol3 from './widgetsRowWithCol3.vue'
import widgetsRowWithCol12 from './widgetsRowWithCol12.vue'
import Widget from '../Widget_Model'

export default {
  name: 'HelloWorld',
  data () {
    return {
      widgetList: [
        new Widget(1, 'Widget 1', 6, 'Blue', true, 'Pie'),
        new Widget(14, 'Widget ABC', 6, 'grey', true, 'Pie'),
        new Widget(165, 'Widget fgf', 6, 'lightgreen', true, 'Pie'),
        new Widget(2, 'Widget 2', 6, 'Red', true, 'Pie'),
        new Widget(3, 'Widget 3', 4, 'yellow', true, 'Pie'),
        new Widget(4, 'Widget 4', 4, 'grey', true, 'Pie'),
        new Widget(5, 'Widget 5', 4, 'green', true, 'Pie'),
        new Widget(6, 'Widget 6', 4, 'orange', true, 'Pie'),
        new Widget(7, 'Widget 7', 3, 'yellow', true, 'Pie'),
        new Widget(8, 'Widget 8', 3, 'lightblue', true, 'Pie'),
        new Widget(9, 'Widget 9', 3, 'silver', true, 'Pie'),
        new Widget(10, 'Widget 10', 3, 'lightgrey', true, 'Pie'),
        new Widget(11, 'Widget 11', 12, 'gold', true, 'Pie')
      ]
    }
  },
  components: {
    'subHeader': subHeader,
    'widgetsRowWithCol6': widgetsRowWithCol6,
    'widgetsRowWithCol4': widgetsRowWithCol4,
    'widgetsRowWithCol3': widgetsRowWithCol3,
    'widgetsRowWithCol12': widgetsRowWithCol12
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
