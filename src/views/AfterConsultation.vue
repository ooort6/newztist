<template>
  <div class="cooperation">
    <div class="header1">
      <div class="nav">
        <Header />
      </div>
    </div>

    <div class="content1">
      <span class="span_1">产品、项目售后咨询单</span>
      <div style="width:40%;margin:0 auto;padding:20px;">
        <Form
          ref="formValidate"
          :model="formValidate"
          :rules="ruleValidate"
          label-position="left"
          :label-width="0"
        >
          <Row style="margin-bottom:5%">
            <span class="span_2"></span>
            <span class="span_3">联系方式</span>
          </Row>

          <Row>
            <Col span="11">
              <FormItem prop="name">
                <Input
                  style="background-color:transparent"
                  placeholder="姓名："
                  v-model="formValidate.name"
                ></Input>
              </FormItem>
            </Col>
            <Col span="11" offset="2">
              <FormItem :label-width="70" label="称谓：" prop="sex">
                <RadioGroup v-model="formValidate.sex" style="width:700px">
                  <Radio label="1" style="margin-right:5%">先生</Radio>
                  <Radio label="2" style="margin-right:5%">女士</Radio>
                </RadioGroup>
              </FormItem>
            </Col>
          </Row>
          <Row style="margin-bottom:8%">
            <Col span="11">
              <FormItem label prop="phone">
                <Input
                  style="background-color:transparent"
                  placeholder="电话："
                  v-model="formValidate.phone"
                ></Input>
              </FormItem>
            </Col>
            <Col span="11" offset="2">
              <FormItem label prop="email">
                <Input
                  style="background-color:transparent"
                  placeholder="邮箱："
                  v-model="formValidate.email"
                ></Input>
              </FormItem>
            </Col>
          </Row>
          <Row style="margin-bottom:5%">
            <span class="span_2"></span>
            <span class="span_3">单位信息</span>
          </Row>
          <FormItem label prop="company">
            <Input
              style="background-color:transparent"
              placeholder="单位名称："
              v-model="formValidate.company"
            ></Input>
          </FormItem>
          <FormItem style="margin-bottom:12%" label prop="company_address">
            <Input
              style="background-color:transparent"
              placeholder="单位地址："
              v-model="formValidate.company_address"
            ></Input>
          </FormItem>

          <Row style="margin-bottom:5%">
            <span class="span_2"></span>
            <span class="span_3">产品咨询</span>
          </Row>
          <Row>
            <Col span="15">
              <FormItem label="请选择所购产品：" prop="product_type" :label-width="150">
                <Select v-model="formValidate.product_type">
                  <Option value="1">智天恶意代码防护</Option>
                  <Option value="2">智天智能DNS</Option>
                  <Option value="3">网络流量分析及管理系统</Option>
                  <Option value="4">智天网络内容审核</Option>
                  <Option value="5">综合控制系统</Option>
                  <Option value="6">三维全景GIS系统</Option>
                  <Option value="7">安全管理平台</Option>
                </Select>
              </FormItem>
            </Col>
          </Row>
           <Row>
              <FormItem prop="history_project_name"  label="历史项目名称："  :label-width="150">
                <Input
                  style="background-color:transparent"
                  placeholder="若有，请填写项目名称"
                 
                 
                  v-model="formValidate.history_project_name"
                ></Input>
              </FormItem>
            </Row>
          <Row>
            <span style="font-size:16px;color:#fff;margin-bottom:3%;display:block">
              <span style="color:red">*</span> 希望解决的问题：
            </span>
          </Row>
          <FormItem label :label-width="0" prop="hope_solve_problem">
            <Input
              v-model="formValidate.hope_solve_problem"
              type="textarea"
              :autosize="{minRows: 4,maxRows: 5}"
              placeholder="简述产品或项目在后期运营中所遇到的问题"
            ></Input>
          </FormItem>
          <Row>
            <Col span="6" offset="6">
              <div class="btn_1" @click="handleSubmit('formValidate')">提交</div>
            </Col>
            <Col span="1"></Col>
            <Col span="11">
              <div class="btn_2" @click="handleReset('formValidate')">重置</div>
            </Col>
          </Row>
        </Form>
      </div>

      <!-- <div class="content_2">
        <div class="content_3">
          <p class="p_1"><img src="@/assets/image/jt.png" alt=""></p>
          <p class="p_2">工作日 9:00-12:00 14:00-18:00</p>
          <p class="p_2" style="margin-bottom:70px">客服代表一对一即时消息沟通</p>

          <p class="p_3">QQ: 31756964995</p>
        </div>
        <div class="content_3">
          <p class="p_1"><img src="@/assets/image/zx.png" alt=""></p>

          <p class="p_2" style="margin-bottom:70px">
            就你感兴趣的产品或解决方案提交咨询
            问题，我们将安排专人在一个工作日内
            给您答复
          </p>

          <span class="content_4">填写咨询表单</span>
        </div>
        <div class="content_3">
          <p class="p_1"><img src="@/assets/image/dh.png" alt=""></p>
          <p class="p_2" style="margin-bottom:70px">
            全国统一售前服务热线，若遇线路
            繁忙，请选择 在线交谈 进行产品
            和服务咨询
          </p>

          <p class="p_3" style="color:#fff">021-22819090</p>
        </div>
      </div>-->
    </div>
    <Modal v-model="modal3"  class-name="vertical-center-modal" footer-hide >
        <img src="@/assets/image/tc.png" width="100%"  style="margin:0 auto;display:block" alt="">
         <!-- <div slot="footer" style="background:black"> -->
            <!-- <img src="@/assets/image/qx.png"  alt=""> -->
        <!-- </div> -->
    </Modal>
  </div>
</template>
<script>
import Header from "@/components/Header.vue";
export default {
  name: "Consultation",
  components: {
    Header
  },
  data() {
    const validatePhone = (rule, value, callback) => {
      if (!value) {
        return callback(new Error("手机号不能为空"));
      } else if (!/^1[34578]\d{9}$/.test(value)) {
        callback("请填写正确的手机号");
      } else {
        callback();
      }
    };
    return {
       modal3: false,
      formValidate: {
        name: "",
        sex: "",
        email: "",
        phone: "",
        company: "",
        product_type: "",
        form_type:4,
        product_type: "",
        our_company_type: 1,
        hope_solve_problem: "",
        company_address: "",
        history_project_name:''
      },
      ruleValidate: {
        name: [{ required: true, message: "姓名不能为空", trigger: "blur" }],
        sex: [{ required: true, message: "性别不能为空", trigger: "blur" }],

        hope_solve_problem: [
          { required: true, message: "希望解决问题不能为空", trigger: "blur" }
        ],
        product_type: [
          { required: true, message: "请选择所购产品", trigger: "blur" }
        ],
        phone: [
          //   { required: true, message: "手机号码不能为空", trigger: "blur" },
          { required: true, message: "手机号不能为空", trigger: "blur" }
        ],
        number: [{ message: "联系电话不能为空", trigger: "blur" }],
        gurl: [
          { message: "公司网址不能为空", trigger: "blur" }
          // { type: 'url', message: '请填写正确的网址', trigger: 'blur' }
        ],
        email: [
          { required: true, message: "邮箱不能为空", trigger: "blur" }
          // { type: "email", message: "请填写正确的邮箱", trigger: "blur" },
          // { message: "请填写正确的邮箱", trigger: "blur" }
        ],
        company: [
          { required: true, message: "单位名称不能为空", trigger: "blur" }
          // { type: "email", message: "请填写正确的邮箱", trigger: "blur" },
        ],
        company_address: [
          { required: true, message: "单位地址不能为空", trigger: "blur" }
          // { type: "email", message: "请填写正确的邮箱", trigger: "blur" },
        ]
      }
    };
  },
  watch: {
    //监听路由变化
  },
  mounted() {
    // this.init();
  },
  methods: {
    handleSubmit(name) {
      this.$refs[name].validate(valid => {
        console.log(valid);
        if (valid) {
          const _this = this;
          let params = new URLSearchParams();
          const api = this.$common.getUrl() +"/webForm/add";
          params.append("name", _this.formValidate.name);
          params.append("sex", _this.formValidate.sex);
          params.append("phone", _this.formValidate.phone);
          params.append("email", _this.formValidate.email);
          params.append("company", _this.formValidate.company);
          params.append("company_address", _this.formValidate.company_address);
          params.append("form_type", _this.formValidate.form_type);
          params.append(
            "our_company_type",
            _this.formValidate.our_company_type
          );
          params.append("product_type", _this.formValidate.product_type);
          params.append(
            "hope_solve_problem",
            _this.formValidate.hope_solve_problem
          );
  params.append(
            "history_project_name",
            _this.formValidate.history_project_name
          );
          
          this.$axios({
            method: "post",
            url: api,
            data: params
          }).then(function(res) {
            if(res.data.status=="000"){
              // _this.$Message.info(res.data.message);
              _this.modal3=true;
              _this.$refs[name].resetFields();
            }
              else {
          _this.$Message.info(res.data.message);
        }
            console.log(res);
          });

          console.log(_this.formValidate);
        } else {
           _this.$Message.info(res.data.message);
        }
      });
    },

    handleReset(name) {
          //  this.modal3=true;
      this.$refs[name].resetFields();
    },
    init() {
      const api = "/user/webForm/add";
      let params = new URLSearchParams();

      params.append("name", "1");
      params.append("sex", 1);
      params.append("phone", "1");
      params.append("email", "1");
      params.append("company", "1");
      params.append("company_address", "1");
      params.append("form_type", 3);
      params.append("our_company_type", 1);
      params.append("product_type", 1);
      params.append("hope_solve_problem", "21");
   
      this.$axios({
        method: "post",
        url: api,
        data: params
      }).then(function(res) {
        console.log(res);
      });
    }
    // this.$axios({

    // })
  }
};
</script>
<style lang="scss" scoped>
   /deep/.ivu-modal-mask {
      background: rgba(0,0,0,0.7)
    }
.cooperation {
  min-width: 1500px;
  background: url("../assets/image/sheetbg.png") no-repeat;
  //  .vertical-center-modal{
  //       display: flex;
  //       align-items: center;
  //       justify-content: center;

  //       .ivu-modal{
  //           top: 0;
  //       }
  //   }
 
  .header1 {
    height: 100px;
    // background: url("../assets/image/rhgm.png") no-repeat;
    // background-size: 100% 100%;
    // padding-top: 1rem;

    .title {
      display: flex;
      height: 80%;
      justify-content: center;
      align-items: center;
      flex-flow: column;
      .p_1 {
        // width: 100%;
        display: block;
        font-size: 60px;
        font-family: Source Han Sans CN;
        font-weight: 500;
        color: #08fcff;
        line-height: 109px;
      }
      .p_2 {
        text-align: center;
        width: 100%;
        font-size: 18px;
        font-family: "SourceHanSansCN";
        font-weight: 400;
        color: #08fcff;
        line-height: 29px;
        display: block;
      }
      .p_3 {
        text-align: center;
        display: block;
        width: 3%;
        height: 4px;
        background: #08fcff;
        margin-bottom: 20px;
      }
    }
  }

  .content1 {
    height: 940px;
    width: 74%;
    // background: red;
    margin: 0 auto;
    padding-top: 70px;
    /deep/.ivu-input {
      background-color: transparent;
      color: #fff;
    }
    /deep/.ivu-form .ivu-form-item-label {
      color: #fff;
    }
    /deep/.ivu-radio-wrapper {
      color: #fff;
    }
    /deep/.ivu-select-selection {
      background-color: transparent;
      .ivu-select-selected-value {
        color: #fff;
      }
    }
  
    .vertical-center-modal{
        display: flex;
        align-items: center;
        justify-content: center;

        .ivu-modal{
            top: 0;
        }
    }
    .span_1 {
      display: block;
      width: 100%;
      text-align: center;
      font-size: 24px;
      color: #fff;
      margin-bottom: 4%;
    }
    .span_2 {
      display: block;
      width: 8px;
      height: 22px;
      background: #00d8ff;
      float: left;
      margin-right: 2%;
    }
    .span_3 {
      color: #fff;
      font-size: 18px;
    }
    .btn_1 {
      width: 92px;
      height: 28px;
      background: rgba(28, 91, 220, 1);
      border-radius: 10px;
      text-align: center;
      line-height: 28px;
      color: #fff;
      cursor: pointer;
    }
    .btn_2 {
      width: 92px;
      height: 28px;
      background: #dc3c1c;
      text-align: center;
      line-height: 28px;
      color: #fff;
      border-radius: 10px;
      cursor: pointer;

    }

    .content_2 {
      width: 100%;
      height: 500px;
      // background: red;
      display: flex;
      justify-content: space-around;
      .content_3 {
        width: 20%;
        display: flex;
        justify-content: center;
        // align-items: center;
        flex-flow: column;
        .p_1 {
          font-size: 18px;
          color: #fff;
          font-weight: bold;
          margin-bottom: 40px;
        }
        .p_2 {
          font-size: 16px;
          color: #fff;
          text-align: left;
        }
        .p_3 {
          font-size: 24px;
          font-family: Impact;
          font-weight: 400;
          color: rgba(32, 240, 255, 1);
        }
        .content_4 {
          display: block;
          border: 1px solid #20f0ff;
          width: 155px;
          height: 36px;
          text-align: center;
          color: #20f0ff;
          font-size: 16px;
          line-height: 36px;
        }
      }
    }
  }
}
</style>