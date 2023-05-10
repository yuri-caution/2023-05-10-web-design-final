## 웹디자인기능사 시험 연습

### JS 불러오기
```
<script src="./script/jquery-1.12.4.js"></script>
<script src="./script/common.js"></script>
```

### JS method 숨긴 서브 메뉴 보이기
```
<script>
        console.log($('.gnb'))
        $('.gnb').hover(
            function(){
                $('.gnb ul').show()
            },
            function(){
                $('.gnb ul').hide()
            }
        )
</script>
```
```
<script>
        console.log($('.gnb'))
        $('.gnb').hover(
            function(){
                $('.gnb ul').stop().slideDown()
            },
            function(){
                $('.gnb ul').stop().slideUp()
            }
        )
</script>
```

### JS 슬라이드 움직이기
```
// 슬라이드
setInterval(function(){
    $('.slide').animate({top:-300}, function(){
        $('.slide a:first').appendTo($('.slide'))
        $('.slide').css('top', 0)
    })
}, 3000)
```

### JS 선택한 것 확인하기
```
<script>
console.log($(this).index())
</script>
```

### JS 탭 전환
```
// 탭
$('.tab_tit h2').click(function(){
    $('.tab_tit h2').removeClass('on')
    $(this).addClass('on')

    console.log($(this).index())

    $('.tab_contents ul').css('display', 'none')
    $('.tab_contents ul').eq($(this).index()).css('display', 'block')
})
```

### css 갤러리 block으로 디자인
#### flex나 grid로 하면 JS 실행시 깨짐
```
ul.gallery {
    gap: 6px;
    height: 130px;
    display: none;
}

ul.gallery li {
    height: 100%;
    width: 32%;
    float: left;
    margin-right: 2%;
}

ul.gallery li:last-child {
    margin: 0;
}
```