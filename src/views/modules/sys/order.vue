<template>
  <el-tabs v-model="activeName" @tab-click="handleClick">
    <el-tab-pane label="全部订单" name="first">
      <AllOrder/>
    </el-tab-pane>
    <el-tab-pane label="待支付" name="second">
      <AwiatPay ref="awaitPay"/>
    </el-tab-pane>
    <el-tab-pane label="已支付" name="third">
      <ShipOrder ref="shipOrder"/>
    </el-tab-pane>
    <el-tab-pane label="已出证" name="seventh">
      <CertiOrder ref="certiOrder"/>
    </el-tab-pane>
    <el-tab-pane label="已发货" name="fourth">
      <ReceiptOrder ref="receiptOrder"/>
    </el-tab-pane>
    <el-tab-pane label="已妥投" name="fifth">
      <RewardOrder ref="rewardOrder"/>
    </el-tab-pane>
    <el-tab-pane label="未妥投" name="eighth">
      <NotReceiveOrder ref="notReceiveOrder"/>
    </el-tab-pane>
    <el-tab-pane label="已取消" name="sixth">
      <CancelOrder ref="cancelOrder"/>
    </el-tab-pane>
  </el-tabs>
</template>

<script>
  import AllOrder from './all-order.vue'
  import ShipOrder from './ship-order.vue'
  import ReceiptOrder from './receipt-order.vue'
  import RewardOrder from './reward-order.vue'
  import CancelOrder from './cancel-order.vue'
  import AwiatPay from './awiat-pay.vue'
  import CertiOrder from './certi-order.vue'
  import NotReceiveOrder from './not-receive-order.vue'
  export default {
    data(){
      return{
        activeName: 'first'
      }
    },
    components:{
      AllOrder,
      ShipOrder,
      ReceiptOrder,
      RewardOrder,
      CancelOrder,
      AwiatPay,
      CertiOrder,
      NotReceiveOrder
    },
    methods:{
      handleClick(tab, event){
        if(tab.name === 'second'){
          this.$refs.awaitPay.getCancelDataList()
        }
        if(tab.name === 'third'){
          this.$refs.shipOrder.getShipDataList()
        }
        if(tab.name === 'fourth'){
          this.$refs.receiptOrder.getReceiptDataList()
        }
        if(tab.name === 'fifth'){
          this.$refs.rewardOrder.getRewardDataList()
        }
        if(tab.name === 'sixth'){
          this.$refs.cancelOrder.getCancelDataList()
        }
        if(tab.name === 'seventh'){
          this.$refs.certiOrder.getCertiDataList()
        }
        if(tab.name === 'eighth'){
          this.$refs.notReceiveOrder.getNotReceiveDataList()
        }
      }
    }
  }
</script>

<style scoped>

</style>
