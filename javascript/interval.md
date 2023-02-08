## setInterval
자바스크립트에서 5분짜리 타이머 기능 만들기<br>
```javascript
<script>
    var time = 300;
    var min;
    var sec;
    
    var timeover = setInterval(function() {
        min = parseInt(time/60);
        sec = time%60
        
        document.getElementById("time").innerHTML = min + ":" + sec;
        time--;
        
        if(time<0){
            clearInterval(x);
            document.getElementById("time").innerHTML("시간이 만료되었습니다.");
        }
    }, 1000);
</script>
```