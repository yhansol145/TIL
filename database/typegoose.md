## Typegoose
mongoDB와 함께 작업할 수 있도록 해주는 라이브러리

### Decorators
- prop : 모델 혹은 도큐먼트의 value들을 정의할때 쓴다.
```javascript
@prop({ required: true })
public name!: string;

@prop()
public age?: number;

@prop()
public isActive?: boolean;
```

- index : 인덱스를 정의할 때 사용
```javascript
@index({ name: 1 })
class User {
    @prop()
    public name?: string;
}

// User클래스의 'name' 필드에 대한 오름차순 인덱스 생성
// 1은 오름차순, -1은 내림차순
```

- getModelForClass : 클래스를 기반으로 모델을 생성하는데 사용
```javascript
class User {
    @prop({ required: true })
    public name!: string;

    @prop({ required: true, unique: true })
    public email!: stinrg;

    // 네이밍규칙에 의해 users라는 콜렉션 모델 생성
}
```