<template>
    <div class="w100p">
        <el-main>
            <el-form ref="initForm" :model="initForm">
                <el-row>
                    <el-col :span="24">   <!--占整行-->
                        <el-row>
                            <el-col :span="3">
                                <el-button type="primary" class="btnSizeMain" plain>送信</el-button>
                            </el-col>
                            <el-col :span="3">
                                <el-button type="primary" class="btnSizeMain" plain>ハードコピー</el-button>
                            </el-col>
                            <el-col :span="3">
                                <el-button type="primary" class="btnSizeMain" plain>フルサイズ</el-button>
                            </el-col>
                            <el-col :span="3">
                                <el-button type="primary" class="btnSizeMain" plain disabled>取消</el-button>
                            </el-col>
                            <el-col :span="3">
                                <el-button type="primary" class="btnSizeMain" plain>契約画面</el-button>
                            </el-col>
                            <el-col :span="3">
                                <el-button type="primary" class="btnSizeMain" plain>終了</el-button>
                            </el-col>
                            <el-col :span="3">
                            </el-col>
                            <el-col :span="3">
                            </el-col>
                        </el-row>
                    </el-col>
                </el-row>
                <el-row>
                    <el-col :span="24">
                        <div class="blankRowHigh">
                        </div>
                    </el-col>
                </el-row>
                <el-row>
                    <el-col :span="24">

                        <el-card class="box-card">
                            <el-row>
                                <el-col :span="24">   <!--占整行-->
                                    <el-row>
                                        <el-col :span="2" text-align="left">
                                            <label class="labelSize">事案番号</label>
                                        </el-col>
                                        <el-col :span="5" text-align="left">
                                            <el-input v-model="initForm.jianNo" style="width: 120px" disabled="true"
                                                      size="small"></el-input>
                                            <label class="labelSize">-</label>
                                            <el-input v-model="initForm.jianEdNo" style="width: 60px" disabled="true"
                                                      size="small"></el-input>
                                        </el-col>
                                        <el-col :span="12" text-align="left">
                                            <label class="labelSize">担当店</label>
                                            <el-input v-model="initForm.tandoutenCd" style="width: 65px" disabled="true"
                                                      size="small"></el-input>
                                            <el-input v-model="initForm.tandoutenNm" style="width: 200px"
                                                      disabled="true"
                                                      size="small"></el-input>
                                        </el-col>
                                        <el-col :span="2" text-align="left">
                                            <label class="labelSize">計上日</label>
                                        </el-col>
                                        <el-col :span="3" text-align="left">
                                            <el-date-picker type="date" v-model="initForm.keijyouBi" clearable
                                                            value-format="yyyyMMdd" style="width: 130px"
                                                            size="small"></el-date-picker>
                                        </el-col>
                                    </el-row>
                                    <el-row>
                                        <el-col :span="2" text-align="left">
                                            <label class="labelSize">証明書番号</label>
                                        </el-col>
                                        <el-col :span="17" text-align="left">
                                            <el-input v-model="initForm.syoumeiNo" style="width: 120px" disabled="true"
                                                      size="small"></el-input>
                                        </el-col>
                                        <el-col :span="2" text-align="left">
                                            <label class="labelSize">照会番号</label>
                                        </el-col>
                                        <el-col :span="3" text-align="left">
                                            <el-input v-model="initForm.syoukaiNo" style="width: 105px"
                                                      size="small"></el-input>
                                        </el-col>
                                    </el-row>
                                    <el-row>
                                        <el-col :span="2" text-align="left">
                                            <label class="labelSize">契約者名</label>
                                        </el-col>
                                        <el-col :span="6" text-align="left">
                                            <el-input v-model="initForm.keiyakuSyaNm" style="width: 250px"
                                                      disabled="true"
                                                      size="small"></el-input>
                                        </el-col>
                                        <el-col :span="11" text-align="left">
                                            <label class="labelSize">事故日時</label>
                                            <el-input v-model="initForm.jikoDay" style="width: 120px" disabled="true"
                                                      size="small"></el-input>
                                            <el-input v-model="initForm.jikoTime" style="width: 70px"
                                                      size="small"></el-input>
                                        </el-col>
                                        <el-col :span="2" text-align="left">
                                            <label class="labelSize">訴訟移行日</label>
                                        </el-col>
                                        <el-col :span="3" text-align="left">
                                            <el-date-picker type="date" v-model="initForm.ikouBi" clearable
                                                            value-format="yyyyMMdd" style="width: 130px"
                                                            size="small"></el-date-picker>
                                        </el-col>
                                    </el-row>
                                    <el-row>
                                        <el-col :span="24">
                                            <div style="height: 30px">
                                            </div>
                                        </el-col>
                                    </el-row>
                                    <el-row>
                                        <el-col :span="2" text-align="left">
                                            <label class="labelSize">登録区分</label>
                                        </el-col>
                                        <el-col :span="4" text-align="left">
                                            <el-input v-model="initForm.tourokuKbnValue" style="width: 40px"
                                                      size="small"></el-input>
                                            <el-select v-model="initForm.tourokuKbnValue" style="width: 120px"
                                                       size="small">
                                                <el-option
                                                    v-for="item in initForm.tourokuKbn"
                                                    :key="item.value"
                                                    :label="item.label"
                                                    :value="item.value">
                                                </el-option>
                                            </el-select>
                                        </el-col>
                                        <el-col :span="9" text-align="left">
                                            <label class="labelSize">一括払会社</label>
                                            <el-input v-model="initForm.ksidysKbnValue" style="width: 60px"
                                                      size="small"></el-input>
                                            <el-select v-model="initForm.ksidysKbnValue" style="width: 220px"
                                                       size="small">
                                                <el-option
                                                    v-for="item in initForm.ksidysKbn"
                                                    :key="item.value"
                                                    :label="item.label"
                                                    :value="item.value">
                                                </el-option>
                                            </el-select>
                                        </el-col>
                                        <el-col :span="3" text-align="left">
                                            <label class="labelSize">一括払会社事故番号</label>
                                        </el-col>
                                        <el-col :span="6" text-align="left">
                                            <el-input v-model="initForm.kaisyaJikoNo" style="width: 270px"
                                                      size="small"></el-input>
                                        </el-col>
                                    </el-row>
                                </el-col>
                            </el-row>
                            <div class="blankRowHigh">
                            </div>
                            <el-card class="box-card">
                                <div slot="header">
                                    <span class="txtb">被害者</span>
                                </div>
                                <el-row>
                                    <el-col :span="24">   <!--占整行-->
                                        <el-row>
                                            <el-col :span="2" text-align="left">
                                                <label class="labelSize">住所</label>
                                            </el-col>
                                            <el-col :span="12" text-align="left">
                                                <el-input v-model="initForm.jyusyoYubi1" style="width: 60px"
                                                          size="small"></el-input>
                                                <label class="labelSize">-</label>
                                                <el-input v-model="initForm.jyusyoYubi2" style="width: 80px"
                                                          size="small"></el-input>
                                            </el-col>
                                            <el-col :span="2" text-align="left">
                                                <label class="labelSize">ﾌﾘｶﾞﾅ</label>
                                            </el-col>
                                            <el-col :span="8" text-align="left">
                                                <el-input v-model="initForm.hiGaisyafurigana" style="width: 200px"
                                                          size="small"></el-input>
                                            </el-col>
                                        </el-row>
                                        <el-row>
                                            <el-col :span="2" text-align="left">
                                                <label class="labelSize">&emsp; </label>
                                            </el-col>
                                            <el-col :span="12" text-align="left">
                                                <el-input v-model="initForm.jyusyoNm" style="width: 450px"
                                                          size="small"></el-input>
                                            </el-col>
                                            <el-col :span="2" text-align="left">
                                                <label class="labelSize">氏名</label>
                                            </el-col>
                                            <el-col :span="8" text-align="left">
                                                <el-input v-model="initForm.hiGaisyaNm" style="width: 200px"
                                                          size="small"></el-input>
                                            </el-col>
                                        </el-row>
                                        <el-row>
                                            <el-col :span="2" text-align="left">
                                                <label class="labelSize">&emsp; </label>
                                            </el-col>
                                            <el-col :span="12" text-align="left">
                                                <label class="labelSize">&emsp; </label>
                                            </el-col>
                                            <el-col :span="2" text-align="left">
                                                <label class="labelSize">性別</label>
                                            </el-col>
                                            <el-col :span="8" text-align="left">
                                                <el-input v-model="initForm.hiGaisyaSex" style="width: 40px"
                                                          size="small"></el-input>
                                                <el-select v-model="initForm.hiGaisyaSex" style="width: 80px"
                                                           size="small">
                                                    <el-option
                                                        v-for="item in initForm.hiGaisyaSexList"
                                                        :key="item.value"
                                                        :label="item.label"
                                                        :value="item.value">
                                                    </el-option>
                                                </el-select>
                                            </el-col>
                                        </el-row>
                                        <el-row>
                                            <el-col :span="2" text-align="left">
                                                <label class="labelSize">TEL</label>
                                            </el-col>
                                            <el-col :span="12" text-align="left">
                                                <el-input v-model="initForm.hiGaisyaTel1" style="width: 60px"
                                                          size="small"></el-input>
                                                <label class="labelSize">-</label>
                                                <el-input v-model="initForm.hiGaisyaTel2" style="width: 60px"
                                                          size="small"></el-input>
                                                <label class="labelSize">-</label>
                                                <el-input v-model="initForm.hiGaisyaTel3" style="width: 60px"
                                                          size="small"></el-input>
                                            </el-col>
                                            <el-col :span="2" text-align="left">
                                                <label class="labelSize">生年月日</label>
                                            </el-col>
                                            <el-col :span="8" text-align="left">
                                                <el-input v-model="initForm.hiGaisyaGengo" style="width: 40px"
                                                          size="small"></el-input>
                                                <el-select v-model="initForm.hiGaisyaGengo" style="width: 80px"
                                                           size="small">
                                                    <el-option
                                                        v-for="item in initForm.hiGaisyaGengoList"
                                                        :key="item.value"
                                                        :label="item.label"
                                                        :value="item.value">
                                                    </el-option>
                                                </el-select>
                                                <el-date-picker type="date" v-model="initForm.hiGaisyaBirth" clearable
                                                                value-format="yyyyMMdd" style="width: 130px"
                                                                size="small"
                                                                @change="getAge"></el-date-picker>
                                                <el-input v-model="initForm.hiGaisyaAge" style="width: 50px"
                                                          size="small"></el-input>
                                                <label class="labelSize">才</label>
                                            </el-col>
                                        </el-row>
                                    </el-col>
                                </el-row>
                            </el-card>
                            <el-row>
                                <el-col :span="24">
                                    <div class="blankRowHigh">
                                        <label class="labelSize">&emsp; </label>
                                    </div>
                                </el-col>
                            </el-row>
                            <el-row>
                                <el-col :span="24">
                                    <div class="blankRowHigh">
                                        <label class="labelSize">&emsp; </label>
                                    </div>
                                </el-col>
                            </el-row>
                            <el-row>
                                <el-col :span="24">   <!--占整行-->
                                    <el-row>
                                        <el-col :span="5" text-align="right">
                                            <label class="labelSize">受傷区分</label>
                                            <el-input v-model="initForm.jyusyoKbn" style="width: 40px"
                                                      size="small"></el-input>
                                            <el-select v-model="initForm.jyusyoKbn" style="width: 100px" size="small">
                                                <el-option
                                                    v-for="item in initForm.jyusyoKbnList"
                                                    :key="item.value"
                                                    :label="item.label"
                                                    :value="item.value">
                                                </el-option>
                                            </el-select>
                                        </el-col>
                                        <el-col :span="4" text-align="right">
                                            <label class="labelSize">死亡日</label>
                                            <el-date-picker type="date" v-model="initForm.siboubi" clearable
                                                            value-format="yyyyMMdd" style="width: 130px"
                                                            size="small"></el-date-picker>
                                        </el-col>
                                        <el-col :span="15" text-align="left">
                                            <label class="labelSize">&emsp; </label>
                                        </el-col>
                                    </el-row>
                                </el-col>
                            </el-row>

                            <el-card class="box-card mt20">
                                <div slot="header">
                                    <span class="txtb">請求者</span>
                                </div>

                                <el-main>
                                    <el-row>
                                        <el-col :span="24">   <!--占整行-->
                                            <el-row>
                                                <el-col :span="3" text-align="left" size="small">
                                                    <label class="labelSize">請求者コード１</label>
                                                </el-col>
                                                <el-col :span="3" text-align="left">
                                                    <el-button type="primary" plain size="medium">被害者</el-button>
                                                </el-col>
                                                <el-col :span="1" text-align="left">
                                                    <label class="labelSize">氏名</label>
                                                </el-col>
                                                <el-col :span="9" text-align="left">
                                                    <el-input v-model="initForm.seikyusyaNm1" style="width: 270px"
                                                              size="small"></el-input>
                                                </el-col>
                                                <el-col :span="8" text-align="left">
                                                    <label class="labelSize">&emsp; </label>
                                                </el-col>
                                            </el-row>
                                        </el-col>
                                    </el-row>
                                    <el-row>
                                        <el-col :span="24">   <!--占整行-->
                                            <el-row>
                                                <el-col :span="3" text-align="left" size="small">
                                                    <label class="labelSize">請求者コード２</label>
                                                </el-col>
                                                <el-col :span="3" text-align="left">
                                                    <label class="labelSize">&emsp; </label>
                                                </el-col>
                                                <el-col :span="1" text-align="left">
                                                    <label class="labelSize">氏名</label>
                                                </el-col>
                                                <el-col :span="9" text-align="left">
                                                    <el-input v-model="initForm.seikyusyaNm2" style="width: 270px"
                                                              size="small"></el-input>
                                                </el-col>
                                                <el-col :span="8" text-align="left">
                                                    <label class="labelSize">&emsp; </label>
                                                </el-col>
                                            </el-row>
                                        </el-col>
                                    </el-row>
                                    <el-row>
                                        <el-col :span="24">   <!--占整行-->
                                            <el-row>
                                                <el-col :span="3" text-align="left" size="small">
                                                    <label class="labelSize">請求者コード３</label>
                                                </el-col>
                                                <el-col :span="3" text-align="left">
                                                    <label class="labelSize">&emsp; </label>
                                                </el-col>
                                                <el-col :span="1" text-align="left">
                                                    <label class="labelSize">氏名</label>
                                                </el-col>
                                                <el-col :span="9" text-align="left">
                                                    <el-input v-model="initForm.seikyusyaNm3" style="width: 270px"
                                                              size="small"></el-input>
                                                </el-col>
                                                <el-col :span="8" text-align="left">
                                                    <label class="labelSize">&emsp; </label>
                                                </el-col>
                                            </el-row>
                                        </el-col>
                                    </el-row>
                                    <el-row>
                                        <el-col :span="24">   <!--占整行-->
                                            <el-row>
                                                <el-col :span="3" text-align="left" size="small">
                                                    <label class="labelSize">請求者コード４</label>
                                                </el-col>
                                                <el-col :span="3" text-align="left">
                                                    <label class="labelSize">&emsp; </label>
                                                </el-col>
                                                <el-col :span="1" text-align="left">
                                                    <label class="labelSize">氏名</label>
                                                </el-col>
                                                <el-col :span="9" text-align="left">
                                                    <el-input v-model="initForm.seikyusyaNm4" style="width: 270px"
                                                              size="small"></el-input>
                                                </el-col>
                                                <el-col :span="8" text-align="left">
                                                    <label class="labelSize">&emsp; </label>
                                                </el-col>
                                            </el-row>
                                        </el-col>
                                    </el-row>
                                    <el-row>
                                        <el-col :span="24">   <!--占整行-->
                                            <el-row>
                                                <el-col :span="3" text-align="left" size="small">
                                                    <label class="labelSize">請求者コード５</label>
                                                </el-col>
                                                <el-col :span="3" text-align="left">
                                                    <label class="labelSize">&emsp; </label>
                                                </el-col>
                                                <el-col :span="1" text-align="left">
                                                    <label class="labelSize">氏名</label>
                                                </el-col>
                                                <el-col :span="9" text-align="left">
                                                    <el-input v-model="initForm.seikyusyaNm5" style="width: 270px"
                                                              size="small"></el-input>
                                                </el-col>
                                                <el-col :span="8" text-align="left">
                                                    <label class="labelSize">&emsp; </label>
                                                </el-col>
                                            </el-row>
                                        </el-col>
                                    </el-row>
                                    <el-row>
                                        <el-col :span="24">   <!--占整行-->
                                            <el-row>
                                                <el-col :span="3" text-align="left" size="small">
                                                    <label class="labelSize">請求者コード６</label>
                                                </el-col>
                                                <el-col :span="3" text-align="left">
                                                    <label class="labelSize">&emsp; </label>
                                                </el-col>
                                                <el-col :span="1" text-align="left">
                                                    <label class="labelSize">氏名</label>
                                                </el-col>
                                                <el-col :span="9" text-align="left">
                                                    <el-input v-model="initForm.seikyusyaNm6" style="width: 270px"
                                                              size="small"></el-input>
                                                </el-col>
                                                <el-col :span="8" text-align="left">
                                                    <label class="labelSize">&emsp; </label>
                                                </el-col>
                                            </el-row>
                                        </el-col>
                                    </el-row>
                                    <el-row>
                                        <el-col :span="24">   <!--占整行-->
                                            <el-row>
                                                <el-col :span="3" text-align="left" size="small">
                                                    <label class="labelSize">請求者コード７</label>
                                                </el-col>
                                                <el-col :span="3" text-align="left">
                                                    <label class="labelSize">&emsp; </label>
                                                </el-col>
                                                <el-col :span="1" text-align="left">
                                                    <label class="labelSize">氏名</label>
                                                </el-col>
                                                <el-col :span="9" text-align="left">
                                                    <el-input v-model="initForm.seikyusyaNm7" style="width: 270px"
                                                              size="small"></el-input>
                                                </el-col>
                                                <el-col :span="8" text-align="left">
                                                    <label class="labelSize">&emsp; </label>
                                                </el-col>
                                            </el-row>
                                        </el-col>
                                    </el-row>
                                    <el-row>
                                        <el-col :span="24">   <!--占整行-->
                                            <el-row>
                                                <el-col :span="3" text-align="left" size="small">
                                                    <label class="labelSize">請求者コード８</label>
                                                </el-col>
                                                <el-col :span="3" text-align="left">
                                                    <label class="labelSize">&emsp; </label>
                                                </el-col>
                                                <el-col :span="1" text-align="left">
                                                    <label class="labelSize">氏名</label>
                                                </el-col>
                                                <el-col :span="9" text-align="left">
                                                    <el-input v-model="initForm.seikyusyaNm8" style="width: 270px"
                                                              size="small"></el-input>
                                                </el-col>
                                                <el-col :span="8" text-align="left">
                                                    <label class="labelSize">&emsp; </label>
                                                </el-col>
                                            </el-row>
                                        </el-col>
                                    </el-row>
                                    <el-row>
                                        <el-col :span="24">   <!--占整行-->
                                            <el-row>
                                                <el-col :span="3" text-align="left" size="small">
                                                    <label class="labelSize">請求者コード９</label>
                                                </el-col>
                                                <el-col :span="3" text-align="left">
                                                    <label class="labelSize">&emsp; </label>
                                                </el-col>
                                                <el-col :span="1" text-align="left">
                                                    <label class="labelSize">氏名</label>
                                                </el-col>
                                                <el-col :span="9" text-align="left">
                                                    <el-input v-model="initForm.seikyusyaNm9" style="width: 270px"
                                                              size="small"></el-input>
                                                </el-col>
                                                <el-col :span="8" text-align="left">
                                                    <label class="labelSize">&emsp; </label>
                                                </el-col>
                                            </el-row>
                                        </el-col>
                                    </el-row>
                                </el-main>

                            </el-card>

                            <el-row>
                                <el-col :span="14">
                                    <el-card class="box-card mt20">
                                        <div slot="header">
                                            <span class="txtb">回収関連項目</span>
                                        </div>
                                        <el-main>
                                            <el-row>
                                                <el-col :span="24">
                                                    <el-row>
                                                        <el-col :span="5" text-align="left" size="small">
                                                            <el-checkbox :disabled="false"
                                                                         v-model="initForm.kaisyuYoteiFlg.value">回収予定
                                                            </el-checkbox>
                                                        </el-col>
                                                        <el-col :span="3" text-align="left">
                                                            <label class="labelSize">債務者</label>
                                                        </el-col>
                                                        <el-col :span="10" text-align="left">
                                                            <el-input v-model="initForm.seikyusyaNm1"
                                                                      style="width: 270px"
                                                                      size="small"></el-input>
                                                        </el-col>
                                                        <el-col :span="6" text-align="left">
                                                            <label class="labelSize">&emsp; </label>
                                                        </el-col>
                                                    </el-row>
                                                    <el-row>
                                                        <el-col :span="5" text-align="left" size="small">
                                                            <label class="labelSize">回収予定総額</label>
                                                        </el-col>
                                                        <el-col :span="6" text-align="left">
                                                            <el-input v-model="initForm.kaisyuYoteiGaku"
                                                                      style="width: 105px"
                                                                      class="mathsRight"
                                                                      size="small"></el-input>
                                                            <label class="labelSize">円</label>
                                                        </el-col>
                                                        <el-col :span="3" text-align="left">
                                                            <label class="labelSize">求償手段</label>
                                                        </el-col>
                                                        <el-col :span="10" text-align="left">
                                                            <el-input v-model="initForm.kyusyouSyudan"
                                                                      style="width: 40px"
                                                                      size="small"></el-input>
                                                            <el-select v-model="initForm.kyusyouSyudan"
                                                                       style="width: 160px" size="small">
                                                                <el-option
                                                                    v-for="item in initForm.kyusyouSyudanList"
                                                                    :key="item.value"
                                                                    :label="item.label"
                                                                    :value="item.value">
                                                                </el-option>
                                                            </el-select>
                                                        </el-col>
                                                    </el-row>
                                                    <el-row>
                                                        <el-col :span="5" text-align="left" size="small">
                                                            <label class="labelSize">既回収額</label>
                                                        </el-col>
                                                        <el-col :span="6" text-align="left">
                                                            <el-input v-model="initForm.kikaisyuYoteiGaku"
                                                                      style="width: 105px"
                                                                      size="small"></el-input>
                                                            <label class="labelSize">円</label>
                                                        </el-col>
                                                        <el-col :span="3" text-align="left">
                                                            <label class="labelSize">求償理由</label>
                                                        </el-col>
                                                        <el-col :span="10" text-align="left">
                                                            <el-input v-model="initForm.kyusyouRiyu" style="width: 40px"
                                                                      size="small"></el-input>
                                                            <el-select v-model="initForm.kyusyouRiyu"
                                                                       style="width: 160px" size="small">
                                                                <el-option
                                                                    v-for="item in initForm.kyusyouRiyuList"
                                                                    :key="item.value"
                                                                    :label="item.label"
                                                                    :value="item.value">
                                                                </el-option>
                                                            </el-select>
                                                        </el-col>
                                                    </el-row>
                                                    <el-row>
                                                        <el-col :span="5" text-align="left" size="small">
                                                            <label class="labelSize">今後回収見込額</label>
                                                        </el-col>
                                                        <el-col :span="6" text-align="left">
                                                            <el-input v-model="initForm.kongoGaku" style="width: 105px"
                                                                      size="small"></el-input>
                                                            <label class="labelSize">円</label>
                                                        </el-col>
                                                        <el-col :span="3" text-align="left">
                                                            <label class="labelSize">回収担当者</label>
                                                        </el-col>
                                                        <el-col :span="10" text-align="left">
                                                            <el-input v-model="initForm.kaisyuTanto" style="width: 40px"
                                                                      size="small"></el-input>
                                                            <el-select v-model="initForm.kaisyuTanto"
                                                                       style="width: 160px" size="small">
                                                                <el-option
                                                                    v-for="item in initForm.kaisyuTantoList"
                                                                    :key="item.value"
                                                                    :label="item.label"
                                                                    :value="item.value">
                                                                </el-option>
                                                            </el-select>
                                                        </el-col>
                                                    </el-row>
                                                </el-col>
                                            </el-row>
                                        </el-main>
                                    </el-card>
                                </el-col>
                                <el-col :span="1" text-align="left">
                                    <label class="labelSize">&emsp; </label>
                                </el-col>
                                <el-col :span="9">
                                    <el-card class="box-card mt20">
                                        <div slot="header">
                                            <span class="txtb">請求歴・諸情報</span>
                                        </div>

                                        <el-main>
                                            <el-row>
                                                <el-col :span="24">
                                                    <el-row>
                                                        <el-col :span="8" text-align="left" size="small">
                                                            <el-checkbox :disabled="false"
                                                                         v-model="initForm.kaisyuYoteiFlg.value">請求歴有
                                                            </el-checkbox>
                                                        </el-col>
                                                        <el-col :span="8" text-align="right">
                                                            <label class="labelSize">既請求担当店</label>
                                                        </el-col>
                                                        <el-col :span="8" text-align="left">
                                                            <el-input v-model="initForm.seikyuuTantotenCd"
                                                                      style="width: 120px"
                                                                      size="small"></el-input>
                                                        </el-col>
                                                    </el-row>
                                                    <el-row>
                                                        <el-col :span="8" text-align="left" size="small">
                                                            <el-checkbox :disabled="false"
                                                                         v-model="initForm.kaisyuYoteiFlg.value">諸情報有
                                                            </el-checkbox>
                                                        </el-col>
                                                        <el-col :span="8" text-align="right">
                                                            <label class="labelSize">&emsp;</label>
                                                        </el-col>
                                                        <el-col :span="8" text-align="left">
                                                            <label class="labelSize">&emsp;</label>
                                                        </el-col>
                                                    </el-row>
                                                </el-col>
                                            </el-row>
                                        </el-main>
                                    </el-card>
                                    <div text-align="right">
                                        <el-main>
                                            <el-row>
                                                <el-col :span="24">
                                                    <label class="labelSize">&emsp; </label>
                                                </el-col>
                                            </el-row>
                                            <el-row>
                                                <el-col :span="15">
                                                    <label class="labelSize">&emsp; </label>
                                                </el-col>
                                                <el-col :span="9" text-align="right">
                                                    <label class="labelSize">臨時対応</label>
                                                    <el-input v-model="initForm.reijiTaiou" style="width: 80px"
                                                              size="small"></el-input>
                                                </el-col>
                                            </el-row>
                                        </el-main>
                                    </div>

                                </el-col>
                            </el-row>

                        </el-card>

                    </el-col>
                </el-row>
            </el-form>
        </el-main>
    </div>
</template>

<script>
export default {
    name: 'PJ4CR100',
    data: function () {
        return {
            initForm: {
                jianNo: '1234567890', // 事案番号
                jianEdNo: '123', // 事案番号枝番
                tandoutenCd: '2020', // 担当店コード
                tandoutenNm: '東京営業所第一店', // 担当店名称
                keijyouBi: '20201010', // 計上日
                syoumeiNo: '12345678901', // 証明書番号
                syoukaiNo: '123456', // 照会番号
                keiyakuSyaNm: '田中　契約者', // 契約者名
                jikoDay: '2020/08/15', // 事故日
                jikoTime: '12:50', // 事故時刻
                ikouBi: '20201010', // 訴訟移行日
                tourokuKbn: [{// 登録区分
                    value: '1',
                    label: '  '
                }, {
                    value: '2',
                    label: '担当'
                }, {
                    value: '3',
                    label: '組合'
                }],
                tourokuKbnValue: '1', // 登録区分デフォルト
                ksidysKbn: [{// 一括払会社
                    value: '11',
                    label: '  '
                }, {
                    value: '21',
                    label: 'ソフトバンク会社'
                }, {
                    value: '31',
                    label: 'ハローワーク会社'
                }],
                ksidysKbnValue: '11', // 一括払会社コード
                kaisyaJikoNo: '12345678901234567890123456', // 一括払会社事故番号

                // 被害者＊＊＊＊＊＊＊＊＊＊＊＊＊＊＊＊＊＊＊＊＊＊＊＊＊＊＊＊＊＊＊＊＊＊
                jyusyoYubi1: '123', // 住所郵便１
                jyusyoYubi2: '4567', // 住所郵便２
                jyusyoNm: '被害者住所１２３丁目', // 住所
                hiGaisyafurigana: 'ﾀﾅｶ　ﾀﾛｳ', // ﾌﾘｶﾞﾅ
                hiGaisyaNm: '田中　太郎', // 氏名
                hiGaisyaSex: '1', // 性別
                hiGaisyaSexList: [{// 性別
                    value: '1',
                    label: '男'
                }, {
                    value: '2',
                    label: '女'
                }],
                hiGaisyaTel1: '090', // 被害者TEL1
                hiGaisyaTel2: '1234', // 被害者TEL2
                hiGaisyaTel3: '5678', // 被害者TEL3
                hiGaisyaGengo: '1', // 生年年月日元号デフォルト
                hiGaisyaGengoList: [{// 生年年月日 元号
                    value: '1',
                    label: '令和'
                }, {
                    value: '2',
                    label: '平成'
                }],
                hiGaisyaBirth: '20000130', // 生年年月日
                hiGaisyaAge: '25', // 生年年月日 年齢
                jyusyoKbn: '1', // 受傷区分
                jyusyoKbnList: [{// 受傷区分リスト
                    value: '1',
                    label: '死亡'
                }, {
                    value: '2',
                    label: '後遺'
                }],
                siboubi: '20201010', // 死亡日

                // 請求者＊＊＊＊＊＊＊＊＊＊＊＊＊＊＊＊＊＊＊＊＊＊＊＊＊＊＊＊＊＊＊＊＊＊＊
                seikyusyaNm1: '請求者　太郎1', // 請求者氏名１
                seikyusyaNm2: '請求者　太郎2', // 請求者氏名２
                seikyusyaNm3: '請求者　太郎3', // 請求者氏名３
                seikyusyaNm4: '請求者　太郎4', // 請求者氏名４
                seikyusyaNm5: '請求者　太郎5', // 請求者氏名５
                seikyusyaNm6: '請求者　太郎6', // 請求者氏名６
                seikyusyaNm7: '請求者　太郎7', // 請求者氏名７
                seikyusyaNm8: '請求者　太郎8', // 請求者氏名８
                seikyusyaNm9: '請求者　太郎9', // 請求者氏名９

                // 回収関連項目＊＊＊＊＊＊＊＊＊＊＊＊＊＊＊＊＊＊＊＊＊＊＊＊＊＊＊＊＊＊＊＊
                kaisyuYoteiFlg: '1', // 回収予定
                saimusya: '田中　債務者', // 債務者
                kaisyuYoteiGaku: '2234567890', // 回収予定総額
                kikaisyuYoteiGaku: '1234567890', // 既回収額
                kongoGaku: '3234567890', // 今後回収見込額
                kyusyouSyudan: '1', // 求償手段
                kyusyouSyudanList: [{// 求償手段リスト
                    value: '1',
                    label: '現金'
                }, {
                    value: '2',
                    label: '振替'
                }],
                kyusyouRiyu: '1', // 求償理由
                kyusyouRiyuList: [{// 求償理由スト
                    value: '1',
                    label: '求償'
                }, {
                    value: '2',
                    label: 'その他'
                }],

                kaisyuTanto: '1', // 回収担当者
                kaisyuTantoList: [{// 回収担当者スト
                    value: '1',
                    label: '田中　回収担当'
                }, {
                    value: '2',
                    label: '佐藤　先生'
                }],

                // 請求歴・諸情報＊＊＊＊＊＊＊＊＊＊＊＊＊＊＊＊＊＊＊＊＊＊＊＊＊＊＊＊＊＊＊
                seikyuusya: '1', // 請求歴有
                seikyuuTantotenCd: '123', // 既請求担当店
                syoJyouhouAri: '1', // 諸情報有
                reijiTaiou: '12345'// 臨時対応
            }
        }
    },
    methods: {
        newBtn () {
            this.$router.push('/page/PJ4CR100')
        },
        //      判断用户的年龄
        getAge () {
            let birthdays = new Date(this.initForm.hiGaisyaBirth.slice(0, 4) + '-' + this.initForm.hiGaisyaBirth.slice(4, 6) + '-' + this.initForm.hiGaisyaBirth.slice(6, 8))
            let d = new Date()
            let age =
                d.getFullYear() -
                birthdays.getFullYear() -
                (d.getMonth() < birthdays.getMonth() ||
                (d.getMonth() === birthdays.getMonth() &&
                    d.getDate() < birthdays.getDate())
                    ? 1
                    : 0)
            this.initForm.hiGaisyaAge = age
        }
    }
}
</script>

<style scoped>

</style>
