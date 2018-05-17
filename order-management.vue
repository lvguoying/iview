<style lang="less">
@import "../../../../styles/common.less";
@import "../../access.less";
@import "../../tables/components/table.less";
</style>

<template>


    <Row class="margin-top-10">

        <Col span="24">
        <Card>
            <p slot="title">
                <Icon type="mouse"></Icon>
                点击搜索进行搜索
            </p>
            <Row>
                <Col span="20">
                    <input v-model="searchConName3" style="width:100%; height:30px;" placeholder="请输入预订单..."  />
                </Col>
                <Col span="4">
                <span @click="handleSearch3" style="margin: 0 10px;"><Button type="primary" icon="search">搜索</Button></span>
                <Button @click="handleCancel3" type="ghost" >取消</Button>
                </Col>
            </Row>
            
        </Card>
        </Col>

        <Col span="24">
        <Card>
            <p slot="title" style="height: 34px;overflow: visible">
                <Icon type="android-remove"></Icon>
                <span style="margin-right: 96px;">订单管理</span>
                
                <span style="margin-right: 6px;">区域: </span>
                <Select style="width:100px;margin-right: 16px;" :placeholder="local" :disabled="true">
                  <Option v-for="item in cityList" :value="item.value" :key="item.value">{{ item.label }}</Option>
                </Select>
                
                
                <span style="margin-right: 6px;">时间: </span>
                  <Row style="width: 160px;display: inline-block">
                    <Col>
                      <DatePicker @on-change="handleTimeSelect" type="month" placeholder="选择日期" style="width: 140px"></DatePicker>
                    </Col>
                  </Row>
                
                
                <span style="margin-right: 6px;">品类: </span>
                <Select @on-change="handleTyleSelect" style="width:100px">
                  <Option v-for="item in typeLIst" :value="item.value" :key="item.value">{{ item.label }}</Option>
                </Select>
            </p>
            <can-edit-table refs="table2" v-model="editInlineData" :columns-list="editInlineColumns"></can-edit-table>
            <router-link to="preorderadd"><Button type="ghost" long style="margin:10px 0;" > +添加</Button></router-link>
            <router-view></router-view>
            <Page :total="100"   :page-size="5"></Page>
        </Card>
        </Col>
    </Row>




</template>




<script>
import canEditTable from "../../tables/components/preordermanagementusercanEditTable.vue";
import axios from "axios";

export default {
  name: "editable-table",
  components: {
    canEditTable
  },
  data() {
    return {
      // 地址
      local:"黑龙江",
      localID: 17,
      // 筛选的时间
      selectTime: '',
      // 筛选的品类
      selectType:'',
      
      // 品类列表
      typeLIst: [
        {
          value: 1,
          label: "玉米"
        },{
          value: 2,
          label: "大豆"
        },{
          value: 3,
          label: "土豆"
        },{
          value: 4,
          label: "稻米"
        },
      ],

      initTable1: [],

      editInlineColumns: [
        {
          title: "id",
          align: "center",
          key: "id",
          width: 100
        },
        {
          title: "预订单编号",
          align: "center",
          key: "beforehandNum",
          width: 150
        },
        {
          title: "合同编号",
          align: "center",
          key: "compactNum",
          width: 150
        },
        {
          title: "签订地点",
          align: "center",
          key: "concludeSignPlace",
          width: 150,
          editable: true
        },
        {
          title: "签订时间",
          align: "center",
          key: "concludeSignDate",
          width: 150
        },
        {
          title: "合作商id",
          align: "center",
          key: "cooId",
          width: 150
        },
        {
          title: "操作",
          align: "center",
          width: 180,
          key: "handle",
          handle: ["edit", "delete"]
        }
      ],
      editInlineData: [],
      cityList: [
        
        {
          value: "Canberra",
          label: "1"
        }
      ]
    };
  },
  methods: {
    search(data, argumentObj) {
      let res = data;
      let dataClone = data;
      for (let argu in argumentObj) {
        if (argumentObj[argu].length > 0) {
          res = dataClone.filter(d => {
            return d[argu].indexOf(argumentObj[argu]) > -1;
          });
          dataClone = res;
        }
      }
      return res;
    },
    handleSearch3() {
      this.editInlineData = this.initTable1;
      this.editInlineData = this.search(this.initTable1, {
        name: this.searchConName3
      });
    },
    handleCancel3() {
      this.editInlineData = this.initTable1;
    },

    // 时间选择事件处理函数
    handleTimeSelect(){
      console.log(arguments);
    },
    // 品类选择处理函数
    handleTyleSelect(){
      console.log(arguments);
    }
  },
  mounted: function() {
    // 区域ID
    var localID = 17;

    //利用axios调用接口获取数据
    axios
      .get("http://39.107.253.90:60001/tbeforehandorder/findallorderpage")
      .then(
        response => {
          // console.log(response);
          // this.editInlineData = response.data.tbflist;
          console.log(response);
          // 筛选区域
          response.data.tbflist.forEach((item, index) => {
            if (item.id === localID) {
              this.initTable1.push(item);
            }
          });
          this.editInlineData = this.initTable1;
          console.log(res);
        },
        response => {
          console.log("error");
        }
      );
  }
};
</script>



<style>
#changeP {
  height: 34px;
}
#pre-book {
  margin-right: 20px;
}
</style>
