<style>
  .user1{
    background: white;
    padding: 20px;
    padding-left: 300px;
    padding-right: 300px;
    height: 100%;
    text-align: center;
  }
  .h1{
    padding: 10px;
    text-align: center;
    
  }
</style>

<template>

  <Form ref="formValidate" :model="formValidate" :rules="ruleValidate" :label-width="80" class="user1">
    <h3 class="h1">添加预订单</h3>
    <FormItem label="id" prop="id">
      <Input v-model="formValidate.id" placeholder="请输入id"></Input>
    </FormItem>
    <FormItem label="预订单编号" prop="beforehandNum">
      <Input v-model="formValidate.beforehandNum" placeholder="请输入预订单编号"></Input>
    </FormItem>
    <FormItem label="合同编号" prop="compactNum">
      <Input v-model="formValidate.compactNum" placeholder="合同编号"></Input>
    </FormItem>
    <FormItem label="签订地点" prop="concludeSignPlace">
      <Input v-model="formValidate.concludeSignPlace" placeholder="请输入签订地点"></Input>
    </FormItem>
        <FormItem label="签订时间" prop="concludeSignDate">
      <Input v-model="formValidate.concludeSignDate" placeholder="请输入签订时间"></Input>
    </FormItem>
    <FormItem label="甲方(收购方)" prop="firstParty">
      <Input v-model="formValidate.firstParty" placeholder="请输入甲方(收购方)"></Input>
    </FormItem>
    <FormItem label="乙方(出售方)" prop="secondParty">
      <Input v-model="formValidate.secondParty" placeholder="请输入乙方(出售方)"></Input>
    </FormItem>
    <FormItem label="合同年份" prop="year">
      <Input v-model="formValidate.year" placeholder="请输入合同年份"></Input>
    </FormItem>
        <FormItem label="种植区域及面积" prop="plantArea">
      <Input v-model="formValidate.plantArea" placeholder="请输入种植区域及面积"></Input>
    </FormItem>
    <FormItem label="面积" prop="acreage">
      <Input v-model="formValidate.acreage" placeholder="请输入面积"></Input>
    </FormItem>
    <FormItem label="干粮吨数" prop="fieldRationsNum">
      <Input v-model="formValidate.fieldRationsNum" placeholder="请输入干粮吨数"></Input>
    </FormItem>
    <FormItem label="干粮水分" prop="fieldRationsWet">
      <Input v-model="formValidate.fieldRationsWet" placeholder="请输入干粮水分"></Input>
    </FormItem>
        <FormItem label="潮粮吨数" prop="moistGrainNum">
      <Input v-model="formValidate.moistGrainNum" placeholder="请输入潮粮吨数"></Input>
    </FormItem>
    <FormItem label="潮粮水分" prop="moistGrainWet">
      <Input v-model="formValidate.moistGrainWet" placeholder="请输入潮粮水分"></Input>
    </FormItem>
    <FormItem label="上下浮动不超过" prop="floating">
      <Input v-model="formValidate.floating" placeholder="上下浮动不超过"></Input>
    </FormItem>
    <FormItem label="质量标准" prop="nationalStandard">
      <Input v-model="formValidate.nationalStandard" placeholder="请输入质量标准"></Input>
    </FormItem>
        <FormItem label="国标等级" prop="nationalLevel">
      <Input v-model="formValidate.nationalLevel" placeholder="请输入国标等级"></Input>
    </FormItem>
    <FormItem label="水分25%" prop="wet1">
      <Input v-model="formValidate.wet1" placeholder="请输入水分25%"></Input>
    </FormItem>
    <FormItem label="25%折扣比例" prop="discountRate1">
      <Input v-model="formValidate.discountRate1" placeholder="25%折扣比例"></Input>
    </FormItem>
    <FormItem label="水分25-30%" prop="wet2">
      <Input v-model="formValidate.wet2" placeholder="请输入水分25-30%"></Input>
    </FormItem>
        <FormItem label="25%-30折比例" prop="discountRate2">
      <Input v-model="formValidate.discountRate2" placeholder="请输入25%-30折比例"></Input>
    </FormItem>
    <FormItem label="水分30%以上" prop="wet3">
      <Input v-model="formValidate.wet3" placeholder="请输入水分30%以上"></Input>
    </FormItem>
    <FormItem label="水分30%以上折扣比例" prop="discountRate3">
      <Input v-model="formValidate.discountRate3" placeholder="请输入水分30%以上折扣比例"></Input>
    </FormItem>
    <FormItem label="生霉粒率" prop="mildew">
      <Input v-model="formValidate.mildew" placeholder="请输入生霉粒率"></Input>
    </FormItem>
    <FormItem label="生霉粒2-3%" prop="mildewRate1">
      <Input v-model="formValidate.mildewRate1" placeholder="请输入生霉粒2-3%"></Input>
    </FormItem>
    <FormItem label="3%-4%扣量比例" prop="mildewRate2">
      <Input v-model="formValidate.mildewRate2" placeholder="请输入3%-4%扣量比例"></Input>
    </FormItem>
    <FormItem label="生霉粒超4%拒收" prop="mildewRate3">
      <Input v-model="formValidate.mildewRate3" placeholder="请输入生霉粒超4%拒收"></Input>
    </FormItem>
    <FormItem label="锁定价格14水分" prop="farelock1">
      <Input v-model="formValidate.farelock1" placeholder="请输入锁定价格14水分"></Input>
    </FormItem>
        <FormItem label="锁定价格28水分" prop="farelock2">
      <Input v-model="formValidate.farelock2" placeholder="请输入锁定价格28水分"></Input>
    </FormItem>
    <FormItem label="几日支付保证金" prop="payEarnestMoneyDate">
      <Input v-model="formValidate.payEarnestMoneyDate" placeholder="请输入几日支付保证金"></Input>
    </FormItem>
    <FormItem label="保证金元/吨" prop="perEarnestMoney">
      <Input v-model="formValidate.perEarnestMoney" placeholder="请输入保证金元/吨"></Input>
    </FormItem>
    <FormItem label="年化率" prop="yearRate">
      <Input v-model="formValidate.yearRate" placeholder="请输入年化率"></Input>
    </FormItem>
        <FormItem label="保底价14水" prop="minimumPrice1">
      <Input v-model="formValidate.minimumPrice1" placeholder="请输入保底价14水"></Input>
    </FormItem>
    <FormItem label="保底价28水" prop="minimumPrice2">
      <Input v-model="formValidate.minimumPrice2" placeholder="请输入保底价28水"></Input>
    </FormItem>
    <FormItem label="交粮期限" prop="jiaoliangDate">
      <Input v-model="formValidate.jiaoliangDate" placeholder="请输入交粮期限"></Input>
    </FormItem>
    <FormItem label="几日内签订书面变更合同" prop="changeDate">
      <Input v-model="formValidate.changeDate" placeholder="请输入几日内签订书面变更合同"></Input>
    </FormItem>
        <FormItem label="不可抗拒力发生几日通报" prop="noticeDate">
      <Input v-model="formValidate.noticeDate" placeholder="请输入不可抗拒力发生几日通报"></Input>
    </FormItem>
    <FormItem label="不可抗力持续超过几日" prop="noAgreement">
      <Input v-model="formValidate.noAgreement" placeholder="请输入不可抗力持续超过几日"></Input>
    </FormItem>
    <FormItem label="合同有效日" prop="efficaciousDateg">
      <Input v-model="formValidate.efficaciousDateg" placeholder="合同有效日"></Input>
    </FormItem>
    <FormItem label="" prop="graindepotIdd">
      <Input v-model="formValidate.graindepotIdd" placeholder="请输入"></Input>
    </FormItem>
        <FormItem label="烘干塔ID" prop="dtowerId">
      <Input v-model="formValidate.dtowerId" placeholder="请输入烘干塔ID"></Input>
    </FormItem>
    <FormItem label="" prop="operatorId">
      <Input v-model="formValidate.operatorId" placeholder="请输入"></Input>
    </FormItem>
    <FormItem label="" prop="separateBill">
      <Input v-model="formValidate.separateBill" placeholder=""></Input>
    </FormItem>
    <FormItem label="" prop="cooId">
      <Input v-model="formValidate.cooId" placeholder="请输入"></Input>
    </FormItem>
        <FormItem label="" prop="audit">
      <Input v-model="formValidate.audit" placeholder="请输入"></Input>
    </FormItem>
    
    <FormItem>
      <Button type="primary" @click="handleSubmit('formValidate')">提交</Button>
      <Button type="ghost" @click="handleReset('formValidate')" style="margin-left: 8px">取消</Button>
    </FormItem>
  </Form>
</template>
<script>
    export default {
        data () {
            return {
                formValidate: {
                    id: '',
                    beforehandNum: '',
                    compactNum: '',
                    concludeSignPlace: '',
                    concludeSignDate:'',
                    firstParty:'',
                    secondParty:'',
                    year:'',
                    plantArea:'',
                    acreage:'',
                    fieldRationsNum:'',
                    fieldRationsWet:'',
                    moistGrainNum:'',
                    moistGrainWet:'',
                    floating:'',
                    nationalStandard:'',
                    nationalLevel:'',
                    wet1:'',
                    discountRate1:'',
                    wet2:'',
                    discountRate2:'',
                    wet3:'',
                    discountRate3:'',
                    mildew:'',
                    mildewRate1:'',
                    mildewRate2:'',
                    mildewRate3:'',
                    farelock1:'',
                    farelock2:'',
                    payEarnestMoneyDate:'',
                    perEarnestMoney:'',
                    yearRate:'',
                    minimumPrice1:'',
                    jiaoliangDate:'',
                    changeDate:'',
                    noticeDate:'',
                    continueDate:'',
                    noAgreement:'',
                    efficaciousDate:'',
                    graindepotId:'',
                    dtowerId:'',
                    operatorId:'',
                    separateBill:'',
                    cooId:'',
                    audit:'',
                },
                ruleValidate: {
                    id: [
                        { required: true, message: '这里不能为空', trigger: 'blur' }
                    ],
                    beforehandNum: [
                        { required: true, message: '这里不能为空', trigger: 'blur' }
                    ],
                    compactNum: [
                        { required: true, message: '这里不能为空', trigger: 'blur' }
                    ],
                    concludeSignPlace: [
                        { required: true, message: '这里不能为空', trigger: 'change' }
                    ],
                    concludeSignDate: [
                        { required: true, message: '这里不能为空', trigger: 'change' }
                    ],
                     firstParty: [
                        { required: true, message: '这里不能为空', trigger: 'change' }
                    ],
                    secondParty: [
                        { required: true, message: '这里不能为空', trigger: 'change' }
                    ],
                    year: [
                        { required: true, message: '这里不能为空', trigger: 'change' }
                    ]
                }
            }
        },
        methods: {
            handleSubmit (deptId) {
                this.$refs[deptId].validate((valid) => {
                    if (valid) {
                        this.$Message.success('Success!');
                    } else {
                        this.$Message.error('Fail!');
                    }
                })
            },
            handleReset (deptId) {
                this.$refs[deptId].resetFields();
            }
        }
    }
</script>
