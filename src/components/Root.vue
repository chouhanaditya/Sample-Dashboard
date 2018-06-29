<template>
  <div class="container" style="position:relative;">
    <div class="row">
      <div class="col-12">
        <h2 style="text-align: center">Sample Dashboard</h2>
        <a v-on:click="IsPanelVisible=!IsPanelVisible" style="float: right" title="Customize Widgets Visibility">
          <!-- <i class="fa fa-plus-circle fa-lg" v-if="IsPanelVisible === false"></i> -->
          <!-- <i class="fa fa-minus-circle fa-lg" v-if="IsPanelVisible === true"></i> -->
          <i class="fa fa-cogs fa-lg" ></i>

        </a>
      </div>
    </div>
    <br>
    <subHeader
      :widgetList="widgetList"
      v-if="IsPanelVisible === true"
      id="subHeader"
      :IsPanelVisible="IsPanelVisible"
      @clicked="onClickClose"
    ></subHeader>
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
      ],
      IsPanelVisible: false
    }
  },
  components: {
    'subHeader': subHeader,
    'widgetsRowWithCol6': widgetsRowWithCol6,
    'widgetsRowWithCol4': widgetsRowWithCol4,
    'widgetsRowWithCol3': widgetsRowWithCol3,
    'widgetsRowWithCol12': widgetsRowWithCol12
  },
  methods: {
    onClickClose (value) {
      this.IsPanelVisible = value
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  #subHeader {
    position:absolute;
    right: 0;
    z-index: 1000;
    background-color: lightgrey;
    width: 100%;
}

</style>
