## Node Cron

Spring 에서 쓰는 @Scheduled 어노테이션처럼 node에서 사용하는 스케쥴러이다.

```javascript
*    *    *    *    *  수행할 명령어
┬   ┬   ┬   ┬   ┬
│   │   │   │   │
│   │   │   │   │
│   │   │   │   └───────── 요일 (0 - 6) (0 =일요일)
│   │   │   └────────── 월 (1 - 12)
│   │   └─────────── 일 (1 - 31)
│   └──────────── 시 (0 - 23)
└───────────── 분 (0 - 59)
```

스케쥴러와 동일하게 반복작업을 도와준다.

### npm install
```javascript
npm install node-cron
```

### 사용법
```javascript
const task = cron.schedule('30 0 * * *', () => {
    console.log('노드 크론 작업')
});
task.start(); //cron start
```

위와같은 코드로 매일 12시 30분에 '노드 크론 작업' 을 로그로 띄워주게 된다.