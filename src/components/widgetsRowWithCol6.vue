<template>
    <!--This is for widgets with size 6-->
    <section class="row">
        <div class="col-6" v-for="widget in widgetsList_Col6" v-if="widget.visible" v-bind:key="widget.id">
            <div class="card">
                <div class="card-header">
                    <a data-toggle="collapse" :data-target="'#widget6_'+widget.id" style="float: left">
                        {{widget.name}}
                    </a>
                    <a v-on:click="HideWidget(widget.id)" style="float: right">
                        <i class="fa fa-times-circle fa-lg"></i>
                    </a>
                </div>
                <div class="card-body collapse show widget"
                     :style="{backgroundColor:widget.backgroundColor}"
                     :id="'widget6_'+widget.id">
                </div>
            </div>
        </div>
    </section>
</template>

<script>
export default {
  name: 'widgetsRowWithCol6',
  props: ['widgetList'],
  computed: {
    widgetsList_Col6: function () {
      return this.widgetList.filter(x => x.size === 6)
    }
  },
  methods: {
    HideWidget: function (id) {
      var el = this.widgetsList_Col6.filter(x => x.id === id)[0]
      el.visible = false
    }
  }
}
</script>

<style>
    .card-header a{
        cursor: pointer;
    }
    #widgetsUL  ul li input{
        padding-left: 10px!important;
    }
</style>
