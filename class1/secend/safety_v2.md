```template
player.onChat("safety", function () {

})
```
# 오늘의 안전 규칙 3가지 알림 코드 만들기

## Step 1

채팅창에 말하기 블록을 추가하고

# :minecoin: 오늘의 안전 규칙 3가지! :minecoin:

작성해줍니다.

```blocks
player.onChat("safety", function () {
    player.execute(
    "say :minecoin: 오늘의 안전 규칙 3가지! :minecoin:"
    )
})
```
## Step 2

채팅창에 말하기 블록을 연속을 추가하고

# 1. 친구를 밀거나 방해하지 않기
# 2. 선생님 신호가 있으면 바로 멈추기
# 3. 모르는 명령어는 함부로 실행하지 않기

작성해줍니다.

```blocks
player.onChat("safety", function () {
    player.execute(
    "say :minecoin: 오늘의 안전 규칙 3가지! :minecoin:"
    )
    player.execute(
    "say 1. 친구를 밀거나 방해하지 않기"
    )
    player.execute(
    "say 2. 선생님 신호가 있으면 바로 멈추기"
    )
    player.execute(
    "say 3. 모르는 명령어는 함부로 실행하지 않기"
    )
    player.execute(
    "say 준비됐으면 '확인!'이라고 말해요."
    )
})
```

## Step 3

채팅창에 말하기 블록을 추가하고

# 1. 준비됐으면 '확인!'이라고 말해요.

작성해줍니다.

```blocks
player.onChat("safety", function () {
    player.execute(
    "say :minecoin: 오늘의 안전 규칙 3가지! :minecoin:"
    )
    player.execute(
    "say 1. 친구를 밀거나 방해하지 않기"
    )
    player.execute(
    "say 2. 선생님 신호가 있으면 바로 멈추기"
    )
    player.execute(
    "say 3. 모르는 명령어는 함부로 실행하지 않기"
    )
    player.execute(
    "say 준비됐으면 '확인!'이라고 말해요."
    )
})
```

## Step 4

이제 다 완성 했으면 ▶ 을 누르고 채팅창에 safety를 작성하고 엔터를 눌러보세요