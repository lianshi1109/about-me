var h = 0, m = 0;
function initPos() {
    var w = $(window).height()-580;
    w = w>0?w:0;
    $('#avatar').css('margin', w/2 + 'px 0');
    $('#profile').css('top', w/2 + 200 + 'px');
    $('#more').css('height', $(window).height() - 24 + 'px' );
    h = $('#about').height();
    m = h - w/2;
}
function scrollPage() {
    var ch = $(window).scrollTop();
    // 页面滚动效果
    if(ch < h/2) $('body,html').animate({'scrollTop': h + 'px'}, 1000, 'swing');
    else $('body,html').animate({'scrollTop': 0}, 1000, 'swing');
}
function onScroll() {
    var ch = $(window).scrollTop(), d = $('#arrow').data('direction');
    // 箭头方向
    if((ch < h/2 && d == 'up') || (ch > h/2 && d == 'down')) {
        // TODO: animate
        $('#arrow').toggleClass('rotated');
        d = d == 'up' ? 'down' : 'up';
        $('#arrow').data('direction', d);
    }
    // profile透明度
    if(ch < m) $('#opacity').css('opacity', 1 - ch/m);
}
function init() {
    $(window).resize(initPos).scroll(onScroll);
    $('#upAndDown').click(scrollPage);
    $('#arrow').data('direction','down');
    initPos();
}
$(document).ready(init);

