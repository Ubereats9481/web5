<script setup>
$(function () {
    var c = false;
    $('input, textarea').placeholder();
    $('#login_id').focus();
    $('.banner_btn').mouseover(function (e) { //banner
        var id = DOMPurifySanitize('banner_' + $(this).attr('id'));
        $('.banner_btn').removeClass('here');
        $(this).addClass('here');
        $('.banli').hide();
        $('#' + id).fadeIn();
    }).eq($('#bannerStart').val()).mouseover();
    $('#regen').click(function (e) {   //更新驗證碼
        var imgUrl = "https://cart.books.com.tw/member/captcha_login?9ac54f9d40f2dda611db54cf903064c9";
        $('#captcha_img').empty().html('<img src="' + imgUrl + '" width="160" height="75" />');
        $('#captcha').val('');
        e.preventDefault();
    });
    $('#captcha').keypress(function (e) {  //captcha
        $('#captcha_warn').html('').hide();
        if (e.which == 13) {
            e.preventDefault();
            $('#books_login').click();
        }
    });
    $('#login_id').keypress(function (e) {    //login id
        $('#id_warn').html('').hide();
        if (e.which == 13) {
            e.preventDefault();
            $('#books_login').click();
        }
    });
    $('#login_id_eye').click(function (e) {    //login_id_eye
        e.preventDefault();
        if ($('#login_id').prop('type') === "password") {
            $('#login_id').prop('type', 'text');
            $(this).addClass('show');
        } else {
            $('#login_id').prop('type', 'password');
            $(this).removeClass('show');
        }
    });
    $('#login_pswd').keypress(function (e) {  //login pswd
        $('#pswd_warn').html('').hide();
        var s = String.fromCharCode(e.which);
        if ((s.toUpperCase() === s && s.toLowerCase() !== s && !e.shiftKey) ||
            (s.toUpperCase() !== s && s.toLowerCase() === s && e.shiftKey)) { //caps is on
            $("#caps_warn").show();
        } else if ((s.toLowerCase() === s && s.toUpperCase() !== s && !e.shiftKey) ||
            (s.toLowerCase() !== s && s.toUpperCase() === s && e.shiftKey)) { //caps is off
            $("#caps_warn").hide();
        }
        if (e.which == 13) {
            e.preventDefault();
            $('#books_login').click();
        }
    });
    $('#books_login').click(function (e) {    //login
        e.preventDefault();
        var loginId = $.trim($('#login_id').val());
        if (loginId == '') {    //驗證 login id
            $('#id_warn').html('請輸入帳號ID或email').show();
            return;
        }
        var loginPswd = $.trim($('#login_pswd').val());
        if (loginPswd == '') {    //驗證 login pswd
            $('#pswd_warn').html('請輸入密碼 Password').show();
            return;
        }
        var captcha = $.trim($('#captcha').val());
        if (captcha == '') {    //驗證 login pswd
            $('#captcha_warn').html('請輸入驗證碼').show();
            return;
        }
        maskDivShow();
        alert("發生不明原因錯誤，請再試一次");
        location.href = "https://cart.books.com.tw/member/login";
    });
    $('#line_login').click(function (e) {    //login
        e.preventDefault();
        maskDivShow();
        alert("發生不明原因錯誤，請再試一次");
        location.href = "https://cart.books.com.tw/member/login";
    });
    $('#op_login').click(function (e) {    //login
        e.preventDefault();
        maskDivShow();
        alert("發生不明原因錯誤，請再試一次");
        location.href = "https://cart.books.com.tw/member/login";
    });
    var fbwin;
    $('#facebook_login').click(function (e) {  //facebook login
        e.preventDefault();
        maskDivShow();
        if (!fbwin || fbwin.closed !== false) {
            fbwin = window.open($('#fbUrl').val(), 'fb_login', 'left=500,top=200,width=500,height=300,toolbar=no,location=no,menubar=no,status=0');
        }
        fbwin.focus();
        var pollTimer = window.setInterval(function () {
            if (!fbwin || fbwin.closed !== false) { // !== is required for compatibility with Opera
                window.clearInterval(pollTimer);
                maskDivHidden();
            }
        }, 200);
    });
    $('#wdialog_close').click(function (e) {   //login failed - close window
        e.preventDefault();
        if (c) {
            location.reload();
        } else {
            closePopDiv('wdialog');
        }
    });
    $('#retype').click(function (e) {  //login failed - retype
        e.preventDefault();
        if (c) {
            location.reload();
        } else {
            closePopDiv('wdialog');
        }
    });
    $('#fbterm_close').click(function (e) {   //fb使用說明 - 關閉視窗
        e.preventDefault();
        closePopDiv('fbterm');
    });
    $('#fbterm_agreen').click(function (e) {   //fb使用說明 - 同意
        e.preventDefault();
        closePopDiv('fbterm');
        // clean previous value
        $('#link_id').val('');
        $('#link_pswd').val('');
        $('#link_warn').empty();
        openPopDiv('link');
    });
    $('#fbterm_disagreen').click(function (e) {   //fb使用說明 - 不同意
        e.preventDefault();
        closePopDiv('fbterm');
    });
    $('#link_close').click(function (e) {   //fb連結 - 關閉視窗
        e.preventDefault();
        closePopDiv('link');
    });

    $('#link_id').keypress(function (e) { //link fb id
        $('#link_warn').html('').hide();
    });
    $('#link_pswd').keypress(function (e) {  //link fb pswd
        $('#link_warn').html('').hide();
        var s = String.fromCharCode(e.which);
        if ((s.toUpperCase() === s && s.toLowerCase() !== s && !e.shiftKey) ||
            (s.toUpperCase() !== s && s.toLowerCase() === s && e.shiftKey)) { //caps is on
            $("#link_warn").html('大寫鎖定 (Caps Lock) 已啟用').show();
        } else if ((s.toLowerCase() === s && s.toUpperCase() !== s && !e.shiftKey) ||
            (s.toLowerCase() !== s && s.toUpperCase() === s && e.shiftKey)) { //caps is off
            $("#link_warn").html('').hide();
        }
    });
    $('#link_agreen').click(function (e) {   //fb連結-同意
        e.preventDefault();
        var linkId = $.trim($('#link_id').val());
        var linkPswd = $.trim($('#link_pswd').val());
        if (linkId == '') {    //驗證 link fb id
            $('#link_warn').html('請輸入帳號ID或email').show();
            return;
        }
        if (linkPswd == '') {    //驗證 login pswd
            $('#link_warn').html('請輸入密碼 Password').show();
            return;
        }
        $('#link_agreen').prop('disabled', true);
        $('#link_warn').html("連結中...請稍後...").show();
        $.ajax({
            url: "https://www.books.com.tw/member/link_fb_do",
            data: {
                link_id: linkId,
                link_pswd: linkPswd
            },
            type: 'POST',
            success: function (data, textStatus) {
                var result = $.parseJSON(data);
                result = DOMPurifySanitize(result);
                if (result.success) {    //連結登入成功
                    if (result.code == 3) {
                        $('#url').val("https://cart.books.com.tw/member_activate/mobile_notice/");
                    }
                    go();
                } else {  //連結登入失敗
                    $('#link_agreen').prop('disabled', false);
                    $('#link_warn').html(result.msg).show();
                }
            },
            error: function (jqXHR, textStatus) {
                alert('系統忙碌中，請稍後再試');
                $('#link_agreen').prop('disabled', false);
                $('#link_warn').html("").show();
            }
        });
    });
    $('#link_disagreen').click(function (e) {   //fb連結-不同意
        e.preventDefault();
        closePopDiv('link');
    });
});
function go() {
    // content analyze
    var content = $('#content').val();
    var ctParam = {};
    if (content.length !== 0) {
        var ctAry = content.split(";");
        for (var key in ctAry) {
            var ctkey = ctAry[key].split('=');
            ctParam[ctkey[0]] = ctkey[1];
        }
    }
    // url analyze
    var url = $('#url').val();
    var urlObj = $.url(url);
    var param = $.extend({}, urlObj.param(), ctParam);
    var domain = urlObj.attr('protocol') + '://' + urlObj.attr('host');
    var path = urlObj.attr('path');
    var method = 'GET';
    // post/get redirect
    if (url.indexOf('https://www.books.com.tw/shopping/cart.php') >= 0
        || url.indexOf('https://www.books.com.tw/shopping/promote_cart.php') >= 0
        || url.indexOf('https://www.books.com.tw/shopping/supplier_cart.php') >= 0) {   //force POST
        method = 'POST';
    }
    $().redirect(domain + path, param, method);
}
function showFbTerm() {
    if ($('#fbterm_text').html() == "") {
        $.ajax({
            url: "https://www.books.com.tw/member/fb_login_service_term",
            success: function (data, textStatus) {
                data = DOMPurifySanitize(data);
                $('#fbterm_text').html(data);
                openPopDiv('fbterm');
            },
            error: function (jqXHR, textStatus) {
                alert('系統忙碌中，請稍後再試');
            }
        })
    } else {
        openPopDiv('fbterm');
    }
}
var googletag = googletag || {};
googletag.cmd = googletag.cmd || [];
googletag.cmd.push(function () {
    googletag.defineSlot('https://www.books.com.tw/17812066/books_member_D_430x390_bot', [480, 320], 'div-gpt-ad-1515639533351-0').addService(googletag.pubads());
    googletag.pubads().enableSingleRequest();
    googletag.pubads().collapseEmptyDivs(true, true);
    googletag.enableServices();
});
$(function () {
    $(".search_set").hover(function () {
        $(".search_popup").show();
    }, function () {
        $(".search_popup").hide();
    });
    $(".search_popup a").click(function () {
        $("#cat").val($(this).attr('cat'));
        $("#search_name").text($(this).text());
        $(".search_popup").hide();
    });
    $("#search").submit(function (e) {
        if ($('#key').val() === '') {
            alert('請輸入關鍵字');
            e.preventDefault();
        }
    });
});
</script>