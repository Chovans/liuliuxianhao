<template>
    <div class="sell-infomation">
        <header class="commodity-head">
            我要租
            <span class="return-back" @click="ruturnBack"></span>
        </header>
        <form id="form" action="" enctype="" method="post"  class="clearfix"> 
            <div class="sell-first">点击添加图片</div>
            <input type="hidden" id="goods-id">
            <div class="pic-dis" style="display: none;"></div>
            <div class="release_pic clearfix">
                <div class="realease_picbtn" data="0">
                    <img data-id="img_0" src="../assets/images/add.png" alt="" title="">
                    <div style="display:none;" id="none"></div>
                    <input  id="platFileBtn" name="file" type="file" multiple />
                </div>
            </div>
            <div class="sell-second">填写详细信息</div>
            <ul class="sell-information clearfix">
                <li class="clearfix">
                    <span><i>*</i>商品标题：</span>
                    <input id="name" name="name" type="text" value="" placeholder="请输入商品的标题"/>
                </li>
                <li class="clearfix">
                    <span>&nbsp;账号ID：</span>
                    <input id="account" name="account" type="number" value="" placeholder="没有填无"/>
                </li>
                <li class="clearfix">
                    <span><i>*</i>角色等级：</span>
                    <input id="grade" type="number" name="grade" value="" placeholder="请输入角色等级"/>
                </li>
                <li class="sell-sex clearfix">
                    <span><i>*</i>性&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;别：</span>
                    <div id="sex" name="sex" class="re_sele">
                        <label>
                            <input type="radio" checked="checked" name="sex" value="1"/>
                            <i class="choice-sho choiced-show" @click="changeMach"></i>
                            <em class="choice-text">男</em>
                        </label>
                        <label>
                            <input type="radio" name="sex" value="2"/>
                            <i class="choice-sho" @click="changeMach"></i>
                            <em class="choice-text">女</em>
                        </label>
                    </div>
                </li>
                <li class="sell-sex clearfix">
                    <span><i>*</i>操作系统：</span>
                    <div id="system" name="system" class="re_sele">
                        <label>
                            <input type="radio" checked="checked"  name="system" value="3"/>
                            <i class="choice-sho choiced-show" @click="changeMach"></i>
                            <em class="choice-text">通用</em>
                        </label>
                        <label>
                            <input type="radio"  name="system" value="1"/>
                            <i class="choice-sho" @click="changeMach"></i>
                            <em class="choice-text">安卓</em>
                        </label>
                        <label>
                            <input type="radio" name="system" value="2"/>
                            <i class="choice-sho" @click="changeMach"></i>
                            <em class="choice-text">IOS</em>
                        </label>
                    </div>
                </li>
                <li class="sell-sex clearfix">
                    <span><i>*</i>客户端：</span>
                    <div id="client" name="client" class="re_sele">
                        <label>
                            <input type="radio" checked="checked"  name="client" value="3"/>
                            <i class="choice-sho choiced-show" @click="changeMach"></i>
                            <em class="choice-text">通用</em>
                        </label>
                        <label>
                            <input type="radio"  name="client" value="1"/>
                            <i class="choice-sho" @click="changeMach"></i>
                            <em class="choice-text">手机端</em>
                        </label>
                        <label>
                            <input type="radio" name="client" value="2"/>
                            <i class="choice-sho" @click="changeMach"></i>
                            <em class="choice-text">PC端</em>
                        </label>
                    </div>
                </li>
                <li class="sell-sex clearfix">
                    <span><i>*</i>账号绑定：</span>
                    <div id="binding" name="binding" class="re_sele">
                        <label>
                            <input type="radio" checked="checked"  name="binding" value="3"/>
                            <i class="choice-sho choiced-show" @click="changeMach"></i>
                            <em class="choice-text">无</em>
                        </label>
                        <label>
                            <input type="radio" name="binding" value="1"/>
                            <i class="choice-sho" @click="changeMach"></i>
                            <em class="choice-text">手机</em>
                        </label>
                        <label>
                            <input type="radio" name="binding" value="2"/>
                            <i class="choice-sho" @click="changeMach"></i>
                            <em class="choice-text">邮箱</em>
                        </label>
                    </div>
                </li>
                <li class="sell-sex clearfix">
                    <span><i>*</i>第三方授权：</span>
                    <div id="authorization" name="authorization" class="re_sele">
                        <label style="width: 24%; margin-right: 0;">
                            <input type="radio" checked="checked"  name="authorization" value="4"/>
                            <i class="choice-sho choiced-show" @click="changeMach"></i>
                            <em class="choice-text">无</em>
                        </label>
                        <label style="width: 24%; margin-right: 0;">
                            <input type="radio"  name="authorization" value="1"/>
                            <i class="choice-sho" @click="changeMach"></i>
                            <em class="choice-text">QQ</em>
                        </label style="width: 24%; margin-right: 0;">
                        <label style="width: 24%; margin-right: 0;">
                            <input type="radio" name="authorization" value="2"/>
                            <i class="choice-sho" @click="changeMach"></i>
                            <em class="choice-text">微信</em>
                        </label>
                        <label style="width: 24%; margin-right: 0;">
                            <input type="radio" name="authorization" value="3"/>
                            <i class="choice-sho" @click="changeMach"></i>
                            <em class="choice-text">微博</em>
                        </label>
                    </div>
                </li>
                 <li class="sell-sex clearfix">
                    <span><i>*</i>身份认证：</span>
                    <div id="identification" name="identification" class="re_sele">
                        <label>
                            <input type="radio" checked="checked"  name="identification" value="1"/>
                            <i class="choice-sho choiced-show" @click="changeMach"></i>
                            <em class="choice-text">未认证</em>
                        </label>
                        <label>
                            <input type="radio" name="identification" value="2"/>
                            <i class="choice-sho" @click="changeMach"></i>
                            <em class="choice-text">已认证</em>
                        </label>
                    </div>
                </li>
                <li class="lease-diff sell-sex clearfix">
                    <div class="lease-diff-head">
                        <span>出租方式：</span>
                        <em>（选择你的支付方式并写上价格，可多选）</em>
                    </div>
                    <div class="lease-check">
                        <label>
                            <input type="checkbox" name="check" class="lease-dis" value="2"/>
                            <i class="choice-sho" @click="changeMach"></i>
                            <em class="choice-text" style="width: 12%;">时租</em>
                            <input type="text" name="check" class="lease-con" value="" placeholder="输入价格"/>
                            <span>元/时</span>
                        </label>
                        <label>
                            <input type="checkbox" name="check" class="lease-dis" value="2"/>
                            <i class="choice-sho" @click="changeMach"></i>
                            <em class="choice-text" style="width: 12%;">日租</em>
                            <input type="text" name="check" class="lease-con" value="" placeholder="输入价格"/>
                            <span>元/天</span>
                        </label>
                        <label>
                            <input type="checkbox" name="check" class="lease-dis" value="2"/>
                            <i class="choice-sho" @click="changeMach"></i>
                            <em class="choice-text" style="width: 12%;">周租</em>
                            <input type="text" name="check" class="lease-con" value="" placeholder="输入价格"/>
                            <span>元/周</span>
                        </label>
                        <label>
                            <input type="checkbox" name="check" class="lease-dis" value="2"/>
                            <i class="choice-sho" @click="changeMach"></i>
                            <em class="choice-text" style="width: 12%;">月租</em>
                            <input type="text" name="check" class="lease-con" value="" placeholder="输入价格"/>
                            <span>元/月</span>
                        </label>
                    </div>
                </li>
                <li class="sell-sex clearfix">
                    <span><i>*</i>支付方式：</span>
                    <div id="payway" name="payway" class="re_sele">
                        <label>
                            <input type="radio" checked="checked"  name="payway" value="1"/>
                            <i class="choice-sho choiced-show" @click="changeMach"></i>
                            <em class="choice-text">现金结算</em>
                        </label>
                        <!-- <label>
                            <input type="radio" name="payway" value="2"/>
                            <i class="choice-sho" @click="changeMach"></i>
                            <em class="choice-text">其他</em>
                        </label> -->
                    </div>
                </li>
            </ul>
            <ul class="account-infor">
                <li>
                    <label><i>*</i>直播账号</label>
                    <input type="text"   name="" value="" placeholder="请输入直播账号"/>
                </li>
                <li>
                    <label><i>*</i>账号密码</label>
                    <input type="text"   name="" value="" placeholder="请输入账号密码"/>
                </li>
                <li>
                    <label><i>*</i>联系手机</label>
                    <input type="text"   name="" value="" placeholder="请输入手机号码"/>
                </li>
                <li>
                    <label><i>*</i>QQ号码</label>
                    <input type="text"   name="" value="" placeholder="请输入QQ号码"/>
                </li>
            </ul>
            <div class="add-com">
                <h3>商品描述：</h3>
                <textarea id="detail" name="detail" maxlength="200" placeholder="输入商品的补充说明" rows="3"></textarea>
            </div>
            <div class="fill-foot">
                <em>(所有交易平台将收取10%的手续费)</em>
            </div>
            <div class="sell-next">
                <input type="button" class="diyStart" value="提交" />
            </div>
        </form>
    </div>
</template>
<script>
     export default {
        name: 'sell-infomation',
        data() {
            return {
            
            }
        },
        methods: {
            changeMach: function(e) {
                $(e.target).addClass('choiced-show');
            },
            ruturnBack: function() {
                this.$router.go(-1);
            }
        }
    }
</script>