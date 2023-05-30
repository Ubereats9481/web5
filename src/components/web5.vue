<script setup>
</script>

<template>
  <!-- Country Select Start -->
  <!-- Country Select End -->

    <div class="container_24 type04_header_simplify  clearfix" id="header_id" data-attr="simple">
        <div class="grid_24 clearfix">
            <div class="mod header_box clearfix"
                 style="background-image:url(https://db.books.com.tw/G/header/2008/new_header/images/books_logo_a.gif)">
                <div class="books_logo"><a href="https://www.books.com.tw" title="回博客來首頁"><span>回博客來首頁</span></a></div>
                <div class="search clearfix">
                    <h2 class="hide">網站搜尋</h2>

                    <form action="https://www.books.com.tw/" id="search" name="search" method="GET">
                        <input type="text" class="search_key" name="key" id="key" placeholder="請輸入關鍵字">
                        <div class="search_set">
                            <div class="top_search_tip">
                                <a href="javascript:;"><span id="search_name">全館</span><span class="icon" title="展開"></span></a>
                                <input type="hidden" name="cat" id="cat" value="all">
                            </div>
                            <ul class="search_popup" style="display:none;">
                                <li><a href="javascript:;" cat="all" id="default_search_key">全館</a></li>
                                <li><a href="javascript:;" cat="BKA">圖書</a></li>
                                <li><a href="javascript:;" cat="AVA">影音</a></li>
                                <li><a href="javascript:;" cat="DPA">百貨</a></li>
                                <li><a href="javascript:;" cat="MGA">雜誌</a></li>
                                <li><a href="javascript:;" cat="TKA">售票</a></li>
                            </ul>
                        </div>
                        <button type="submit" title="搜尋"><span class="icon">搜尋</span></button>
                    </form>
                </div>
            </div>
        </div>
    </div><!--End Header-->
  <!--start pop win-->
    <div class="newmember_pop newmember message_info clearfix" id="wdialog" style="display: none;">
        <div id="wdialog_close" class="close_pop" title="關閉視窗"><span>關閉視窗</span></div>
        <div class="bd_a">
            <h2 class="title_09" title="提示訊息">提示訊息</h2>
            <!--提示訊息-->
            <div class="set_cont">
                <ul>
                    <li>您輸入的帳號或密碼錯誤，請<a href="javascript:;" id="retype">重新輸入</a></li>
                    <li>忘了會員帳號與密碼，請<a href="https://www.books.com.tw/member/forgot">查詢帳號與密碼</a></li>
                    <li>還不是博客來會員，請<a
                            href="https://www.books.com.tw/member/join_validate?url=https%3A%2F%2Fwww.books.com.tw%2F">加入會員</a>
                    </li>
                </ul>
            </div><!--End 提示訊息-->
        </div>
    </div><!--end pop win-->
  <!--start pop win-->
    <div class="newmember_pop newmember fb_policy clearfix" id="fbterm" style="display: none;">
        <div id="fbterm_close" class="close_pop" title="關閉視窗"><span>關閉視窗</span></div>
        <div class="bd_a">
            <h2 class="title_06" title="會員登入-博客來連結FB帳號，使用說明">博客來連結FB帳號，使用說明</h2>
            <div class="member_m01 clearfix" id="fbterm_text"></div>
            <div class="ft01 btnwrap">
                <span><a href="javascript:;" id="fbterm_agreen" class="button02">同意</a></span>
                <span><a href="javascript:;" id="fbterm_disagreen" class="button03">不同意</a></span>
            </div>
        </div>
    </div><!--end pop win-->
  <!--start pop win-->
    <div class="newmember_pop newmember fb_link clearfix" id="link" style="display: none;">
        <div id="link_close" class="close_pop" title="關閉視窗"><span>關閉視窗</span></div>
        <div class="bd_a">
            <h2 class="title_07" title="會員登入-連結您的博客來帳號">連結您的博客來帳號</h2>
            <div class="member_m01 clearfix">
                <p>請填入您的博客來會員帳號或e-mail，以及密碼。<br>
                    您只需設定一次，日後即可用 facebook 快速登入博客來。</p>
            </div>
            <div class="set_cont">
                <h3 class="pic">fb連結您的博客來帳號</h3>
                <p><input type="text" id="link_id" required="required" placeholder="博客來 帳號ID或email"
                          class="width01 input01" autocorrect="off" autocapitalize="none"></p>
                <p><input type="password" id="link_pswd" required="required" placeholder="博客來 密碼 Password"
                          class="width01 input01" maxlength="16" size="16"></p>
                <p class="point msg" id="link_warn" style="display:none;"></p>
            </div>
            <div class="mod ft01 btnwrap clearfix">
                <span><a href="javascript:;" id="link_agreen" class="button02">同意</a></span>
                <span><a href="javascript:;" id="link_disagreen" class="button03">不同意</a></span>
            </div>
            <ul class="mod member_m03 clearfix">
                <li class="li_left"><a href="https://www.books.com.tw/member/forgot">忘記帳號密碼</a></li>
                <li class="li_right">還不是會員? <a
                        href="https://www.books.com.tw/member/join_validate?url=https%3A%2F%2Fwww.books.com.tw%2F">加入會員</a>
                </li>
            </ul>
        </div>
    </div><!--end pop win-->
  <!--start pop win-->
    <div class="newmember_pop newmember message_info clearfix" id="pswd_safety" style="display: none;">
        <div id="pswd_close" class="close_pop" title="關閉視窗"><span>關閉視窗</span></div>
        <div class="bd_a">
            <h2 class="title_09" title="提示訊息">提示訊息</h2>
            <!--提示訊息-->
            <div class="set_cont">
                <ul id="pswd_safety_text">
                </ul>
            </div><!--End 提示訊息-->
            <div class="mod ft01 btnwrap clearfix">
                <span><a href="#" class="button02" id="update_password1">修改密碼</a></span>
                <span><a href="#" class="button02" id="update_password2">修改密碼</a></span>
                <span><a href="#" class="button03" id="keep_password">沿用舊密碼</a></span>
            </div>
        </div>
    </div><!--end pop win-->

  <!--main_wrap-->
    <div class="container_24 main_wrap clearfix">
        <!--main_column( 20grid:790px )-->
        <div class="grid_20 push_2 newmember">
            <div class="mod join_wrap clearfix">
                <div class="box_1 grid_13 alpha">
                    <!--m04-->
                    <div class="mod member_m04 flearfix">
                        <h3 class="hide">廣告輪播</h3>
                        <div class='css_pt_div'>
                            <img src="https://tpc.googlesyndication.com/simgad/6681725742384300013">
                            <img width="480" src="https://im1.book.com.tw/image/getImage?i=https://addons.books.com.tw/G/ADbanner/2023/04/ebcommerce_750240.jpg">
                        </div>
                    </div><!--End m04-->
                </div>
                <div class="box_2 grid_7 omega">
                    <div class="content_wrap">
                        <div class="bd_b">
                            <h1 class="title_05" title="會員登入">會員登入</h1>
                            <div class="mod clearfix">
                                <table class="table_c">
                                    <col width="50%">
                                    <col width="50%">
                                    <tbody>
                                    <tr>
                                        <td colspan="2">
                                            <p class="idword">
                                                <input type="password" name="login_id" id="login_id" value=""
                                                       class="width01 input01" required="required"
                                                       placeholder="帳號ID或email" maxlength="50" size="50" tabindex="1"
                                                       autocorrect="off" autocapitalize="none">
                                                <i class="icon" id="login_id_eye"></i>
                                            </p>
                                            <p class="point msg" id="id_warn" style="display:none;"></p>
                                        </td>
                                    </tr>
                                    <tr>
                                        <td colspan="2">
                                            <input type="password" name="login_pswd" id="login_pswd"
                                                   class="width01 input01" required="required"
                                                   placeholder="密碼 Password" maxlength="16" size="16" tabindex="2">
                                            <p class="point msg" id="pswd_warn" style="display:none;"></p>
                                            <p class="point msg" id="caps_warn" style="display:none;">大寫鎖定 (Caps
                                                Lock) 已啟用</p>
                                            <input type="hidden" name="url" id="url"
                                                   value="https://www.books.com.tw/">
                                            <input type="hidden" name="content" id="content" value="">
                                        </td>
                                    </tr>
                                    <tr>
                                        <td colspan="2">
                                            <input type="text" name="captcha" id="captcha" class="width01 input01"
                                                   required="required" placeholder="請輸入驗證碼（不分大小寫）" maxlength="4"
                                                   size="6" autocomplete="off" tabindex="3">
                                            <p class="point msg" id="captcha_warn" style="display:none;"></p>
                                        </td>
                                    </tr>
                                    <tr>
                                        <td>
                                            <div id="captcha_img"><img
                                                    src="https://cart.books.com.tw/member/captcha_login?9ac54f9d40f2dda611db54cf903065c7"
                                                    width="160" height="75"></div>
                                        </td>
                                        <td style="text-align:center;">
                                            <p><a href="javascript:;" id="regen">更新驗證碼</a></p>
                                        </td>
                                    </tr>
                                    <tr>
                                        <td colspan="2"><button id="books_login" class="button04"
                                                                tabindex="4">登入</button></td>
                                    </tr>
                                    </tbody>
                                </table>
                            </div>
                            <div class="mod clearfix">
                                <ul class="member_m03">
                                    <li class="li_left"><a href="https://cart.books.com.tw/member/forgot">忘記帳號密碼</a>
                                    </li>
                                    <li class="li_right">還不是會員? <a
                                            href="https://cart.books.com.tw/member/join_validate?url=https%3A%2F%2Fwww.books.com.tw%2F">加入會員</a>
                                    </li>
                                </ul>
                            </div>
                            <h3>更多登入方式</h3>
                            <div class="mod sns-btn-group h" id="css_pt_grid">

                                <ul>
                                    <li>
                                        <a href="javascript:;" id="op_login"
                                           class="sns-btn btn-op">&nbsp;&nbsp;&nbsp;&nbsp;使用&nbsp;OPEN&nbsp;POINT&nbsp;登入</a>
                                    </li>
                                    <li>
                                        <a href="javascript:;" id="facebook_login" class="sns-btn btn-fb"
                                           title="Facebook登入">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;使用&nbsp;Facebook&nbsp;登入</a>
                                        <input type="hidden" id="fbUrl"
                                               value="https://www.facebook.com/v3.2/dialog/oauth?client_id=210743125726405&amp;scope=email,public_profile&amp;redirect_uri=https%3A%2F%2Fcart.books.com.tw%2Fmember%2Ffb_login_do&amp;display=popup">
                                    </li>
                                    <li>
                                        <a href="javascript:;" id="line_login" class="sns-btn btn-line"
                                           title="Line登入">&nbsp;&nbsp;&nbsp;&nbsp;使用&nbsp;LINE&nbsp;登入</a>
                                    </li>
                                </ul>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div><!--end main_column-->
        <!--right_column( 2grid:70px )-->
        <div class="grid_2 push_2">&nbsp;</div><!--end right_column-->
        <!--left_column( 2grid:70px )-->
        <div class="grid_2 pull_22">&nbsp;</div><!--end left_column-->

    </div><!--End main_wrap-->
  <!--footer-->
    <div class="container_24 type04_footer_simplify clearfix">
        <div class="grid_24 wrap clearfix">
            <div class="bd">
                <h4 class="books_logo"><a></a></h4>
                <ul class="service_message">
                    <li>
                        <p><span>客戶服務專線：02-26535588</span><span>傳真：02-27885008</span><span>服務時間：週一~五 8:00~19:00，週六~日、例假日
                                9:00~18:00，365天全年無休</span></p>
                    </li>
                    <li>
                        <p><span>博客來數位科技股份有限公司</span><span>地址：115 台北市南港區八德路四段768巷1弄18號B1之1</span></p>
                    </li>
                    <li>
                        <p>Copyright &copy; since 1995 books.com.tw All Rights Reserved.</p>
                    </li>
                </ul>
            </div>
        </div>
    </div><!--End footer-->
</template>

<style scoped>
.css_pt_div {
    height: 550px;
    display: flex;
    flex-direction: column;
    justify-content: space-around;
}

#css_pt_grid{
    display: grid;
    grid-template-rows: 40px 40px 40px;
    grid-template-columns: 246px 246px 246px;
    grid-gap: 5px;
}
</style>
