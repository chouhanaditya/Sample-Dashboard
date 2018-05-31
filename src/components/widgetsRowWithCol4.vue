<template>
    <!--This is for widgets with size 4-->
    <section class="row">
        <div class="col-4" v-for="widget in widgetsList_Col4" v-if="widget.visible" v-bind:key="widget.id">
            <div class="card">
                <div class="card-header">
                    <a data-toggle="collapse" :data-target="'#widget4_'+widget.id" style="float: left">
                        {{widget.name}}
                    </a>
                    <a v-on:click="HideWidget(widget.id)" style="float: right">
                        <i class="fa fa-times-circle fa-lg"></i>
                    </a>
                </div>
                <div class="card-body collapse show widget"
                     :style="{backgroundColor:widget.backgroundColor}"
                     :id="'widget4_'+widget.id">
                </div>
            </div>
        </div>
    </section>
</template>

<script>
export default {
  name: 'widgetsRowWithCol4',
  props: ['widgetList'],
  computed: {
    widgetsList_Col4: function () {
      return this.widgetList.filter(x => x.size === 4)
    }
  },
  methods: {
    HideWidget: function (id) {
      var el = this.widgetsList_Col4.filter(x => x.id === id)[0]
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
