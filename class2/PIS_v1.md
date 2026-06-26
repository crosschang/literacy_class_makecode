# 개인정보 보안 블록코딩

```validation.global
# BlocksExistValidator
* markers: validate-exists
```

```template
let 개인정보단서: string[] = []
개인정보단서 = ["",""]

player.onChat("검사", function (num1) {

})
```
## Step 1
먼저 개인정보단서에 검사할 문자들을 입력해요

```blocks
개인정보단서 = [
"학년",
"학교",
"전화번호",
"010",
"아파트",
"이름",
"이메일",
".com",
"@",
"주소",
"집",
"번호"
]
```

## Step 2

그 다음 `검사` 채팅 명령어 블록을 확인해요.

채팅창에 `검사 1`처럼 입력하면 이 코드가 실행돼요.

```blocks
let 개인정보단서: string[] = []
개인정보단서 = [
"학년",
"학교",
"전화번호",
"010",
"아파트",
"이름",
"이메일",
".com",
"@",
"주소",
"집",
"번호"
]
// @validate-exists
player.onChat("검사", function (num1) {
// @validate-exists
    player.say("마인블록코딩")
})
```

## Step 3

`만약 / 아니면` 블록을 넣어요.

번호가 잘못되었는지 확인할 거예요.

```blocks
let 개인정보단서: string[] = []
개인정보단서 = [
"학년",
"학교",
"전화번호",
"010",
"아파트",
"이름",
"이메일",
".com",
"@",
"주소",
"집",
"번호"
]

player.onChat("검사", function (num1) {
    // @validate-exists
    if (true) {

    } else {

    }
})
```

## Step 4

조건에 `num1 < 1`을 넣어요.

입력한 번호가 1보다 작으면 잘못된 번호예요.

```blocks
let 개인정보단서: string[] = []
개인정보단서 = [
"학년",
"학교",
"전화번호",
"010",
"아파트",
"이름",
"이메일",
".com",
"@",
"주소",
"집",
"번호"
]

player.onChat("검사", function (num1) {
    // @validate-exists
    if (num1 < 1) {

    } else {

    }
})
```

## Step 5

조건에 `또는`을 넣어요.

번호가 1보다 작거나, 검사 문장 개수보다 크면 잘못된 번호예요.

```blocks
let 개인정보단서: string[] = []
개인정보단서 = [
"학년",
"학교",
"전화번호",
"010",
"아파트",
"이름",
"이메일",
".com",
"@",
"주소",
"집",
"번호"
]

player.onChat("검사", function (num1) {
    // @validate-exists
    if (num1 < 1 || num1 > CheckList.GetCheckList_Length()) {

    } else {

    }
})
```

## Step 6

번호가 잘못되었을 때 안내 문장을 말하게 해요.

```blocks
let 개인정보단서: string[] = []
개인정보단서 = [
"학년",
"학교",
"전화번호",
"010",
"아파트",
"이름",
"이메일",
".com",
"@",
"주소",
"집",
"번호"
]

player.onChat("검사", function (num1) {
    if (num1 < 1 || num1 > CheckList.GetCheckList_Length()) {
        // @validate-exists
        player.say("1부터 " + CheckList.GetCheckList_Length() + "까지의 번호를 입력해 주세요.")
    } else {

    }
})
```

## Step 7

번호가 맞으면 `발견됨`을 `false`로 바꿔요.

아직 개인정보 단서를 찾기 전이라서 `false`예요.

```blocks
let 개인정보단서: string[] = []
개인정보단서 = [
"학년",
"학교",
"전화번호",
"010",
"아파트",
"이름",
"이메일",
".com",
"@",
"주소",
"집",
"번호"
]

player.onChat("검사", function (num1) {
    if (num1 < 1 || num1 > CheckList.GetCheckList_Length()) {
        player.say("1부터 " + CheckList.GetCheckList_Length() + "까지의 번호를 입력해 주세요.")
    } else {
        // @validate-exists
        발견됨 = false
    }
})
```

## Step 8

번호에 맞는 검사 문장을 가져와요.

예를 들어 `검사 3`을 입력하면 3번 문장을 가져와요.

```blocks
let 개인정보단서: string[] = []
개인정보단서 = [
"학년",
"학교",
"전화번호",
"010",
"아파트",
"이름",
"이메일",
".com",
"@",
"주소",
"집",
"번호"
]

player.onChat("검사", function (num1) {
    if (num1 < 1 || num1 > CheckList.GetCheckList_Length()) {
        player.say("1부터 " + CheckList.GetCheckList_Length() + "까지의 번호를 입력해 주세요.")
    } else {
        발견됨 = false
        // @validate-exists
        검사할_문장 = CheckList.GetCheckList_Sentence(num1)
    }
})
```

## Step 9

가져온 문장을 채팅창에 보여줘요.

```blocks
let 개인정보단서: string[] = []
개인정보단서 = [
"학년",
"학교",
"전화번호",
"010",
"아파트",
"이름",
"이메일",
".com",
"@",
"주소",
"집",
"번호"
]

player.onChat("검사", function (num1) {
    if (num1 < 1 || num1 > CheckList.GetCheckList_Length()) {
        player.say("1부터 " + CheckList.GetCheckList_Length() + "까지의 번호를 입력해 주세요.")
    } else {
        발견됨 = false
        검사할_문장 = CheckList.GetCheckList_Sentence(num1)
        // @validate-exists
        player.say("검사할 문장 : " + 검사할_문장)
    }
})
```

## Step 10

반복문을 넣어요.

개인정보 단서 목록을 처음부터 끝까지 하나씩 확인할 거예요.

```blocks
let 개인정보단서: string[] = []
개인정보단서 = [
"학년",
"학교",
"전화번호",
"010",
"아파트",
"이름",
"이메일",
".com",
"@",
"주소",
"집",
"번호"
]

player.onChat("검사", function (num1) {
    if (num1 < 1 || num1 > CheckList.GetCheckList_Length()) {
        player.say("1부터 " + CheckList.GetCheckList_Length() + "까지의 번호를 입력해 주세요.")
    } else {
        발견됨 = false
        검사할_문장 = CheckList.GetCheckList_Sentence(num1)
        player.say("검사할 문장 : " + 검사할_문장)
        // @validate-exists
        for (let 값 = 0; 값 <= 개인정보단서.length; 값++) {

        }
    }
})
```

## Step 11

검사할 문장 안에 개인정보 단서가 들어 있는지 확인해요.

```blocks
개인정보단서 = [
"학년",
"학교",
"전화번호",
"010",
"아파트",
"이름",
"이메일",
".com",
"@",
"주소",
"집",
"번호"
]

player.onChat("검사", function (num1) {
    if (num1 < 1 || num1 > CheckList.GetCheckList_Length()) {
        player.say("1부터 " + CheckList.GetCheckList_Length() + "까지의 번호를 입력해 주세요.")
    } else {
        발견됨 = false
        검사할_문장 = CheckList.GetCheckList_Sentence(num1)
        player.say("검사할 문장 : " + 검사할_문장)
        for (let 값 = 0; 값 <= 개인정보단서.length; 값++) {
            // @validate-exists
            if (검사할_문장.includes(개인정보단서[값])) {

            }
        }
    }
})
```

## Step 12

개인정보 단서를 찾으면 `발견됨`을 `true`로 바꿔요.

```blocks
개인정보단서 = [
"학년",
"학교",
"전화번호",
"010",
"아파트",
"이름",
"이메일",
".com",
"@",
"주소",
"집",
"번호"
]

player.onChat("검사", function (num1) {
    if (num1 < 1 || num1 > CheckList.GetCheckList_Length()) {
        player.say("1부터 " + CheckList.GetCheckList_Length() + "까지의 번호를 입력해 주세요.")
    } else {
        발견됨 = false
        검사할_문장 = CheckList.GetCheckList_Sentence(num1)
        player.say("검사할 문장 : " + 검사할_문장)
        for (let 값 = 0; 값 <= 개인정보단서.length; 값++) {
            if (검사할_문장.includes(개인정보단서[값])) {
                // @validate-exists
                발견됨 = true
            }
        }
    }
})
```

## Step 13

찾은 개인정보 단서를 말하게 해요.

예를 들어 문장에 `전화번호`가 있으면 `개인정보 단서 발견 : 전화번호`라고 말해요.

```blocks
개인정보단서 = [
"학년",
"학교",
"전화번호",
"010",
"아파트",
"이름",
"이메일",
".com",
"@",
"주소",
"집",
"번호"
]

player.onChat("검사", function (num1) {
    if (num1 < 1 || num1 > CheckList.GetCheckList_Length()) {
        player.say("1부터 " + CheckList.GetCheckList_Length() + "까지의 번호를 입력해 주세요.")
    } else {
        발견됨 = false
        검사할_문장 = CheckList.GetCheckList_Sentence(num1)
        player.say("검사할 문장 : " + 검사할_문장)
        for (let 값 = 0; 값 <= 개인정보단서.length; 값++) {
            if (검사할_문장.includes(개인정보단서[값])) {
                발견됨 = true
                // @validate-exists
                player.say("개인정보 단서 발견 : " + 개인정보단서[값])
            }
        }
    }
})
```

## Step 14

반복 검사가 끝난 뒤, 결과를 확인하는 `만약` 블록을 넣어요.

```blocks
개인정보단서 = [
"학년",
"학교",
"전화번호",
"010",
"아파트",
"이름",
"이메일",
".com",
"@",
"주소",
"집",
"번호"
]

player.onChat("검사", function (num1) {
    if (num1 < 1 || num1 > CheckList.GetCheckList_Length()) {
        player.say("1부터 " + CheckList.GetCheckList_Length() + "까지의 번호를 입력해 주세요.")
    } else {
        발견됨 = false
        검사할_문장 = CheckList.GetCheckList_Sentence(num1)
        player.say("검사할 문장 : " + 검사할_문장)
        for (let 값 = 0; 값 <= 개인정보단서.length; 값++) {
            if (검사할_문장.includes(개인정보단서[값])) {
                발견됨 = true
                player.say("개인정보 단서 발견 : " + 개인정보단서[값])
            }
        }
        // @validate-exists
        if (발견됨 == true) {

        } else {

        }
    }
})
```

## Step 15

개인정보 단서가 발견되었을 때 말할 문장을 넣어요.

```blocks
개인정보단서 = [
"학년",
"학교",
"전화번호",
"010",
"아파트",
"이름",
"이메일",
".com",
"@",
"주소",
"집",
"번호"
]

player.onChat("검사", function (num1) {
    if (num1 < 1 || num1 > CheckList.GetCheckList_Length()) {
        player.say("1부터 " + CheckList.GetCheckList_Length() + "까지의 번호를 입력해 주세요.")
    } else {
        발견됨 = false
        검사할_문장 = CheckList.GetCheckList_Sentence(num1)
        player.say("검사할 문장 : " + 검사할_문장)
        for (let 값 = 0; 값 <= 개인정보단서.length; 값++) {
            if (검사할_문장.includes(개인정보단서[값])) {
                발견됨 = true
                player.say("개인정보 단서 발견 : " + 개인정보단서[값])
            }
        }
        if (발견됨 == true) {
            // @validate-exists
            player.say("이 문장에는 개인정보가 포함되어 있을 수 있어요!")
        } else {

        }
    }
})
```

## Step 16

개인정보 단서가 없을 때 말할 문장을 넣어요.

이제 개인정보 검사 블록코딩이 완성됩니다.

```blocks
개인정보단서 = [
"학년",
"학교",
"전화번호",
"010",
"아파트",
"이름",
"이메일",
".com",
"@",
"주소",
"집",
"번호"
]

player.onChat("검사", function (num1) {
    if (num1 < 1 || num1 > CheckList.GetCheckList_Length()) {
        player.say("1부터 " + CheckList.GetCheckList_Length() + "까지의 번호를 입력해 주세요.")
    } else {
        발견됨 = false
        검사할_문장 = CheckList.GetCheckList_Sentence(num1)
        player.say("검사할 문장 : " + 검사할_문장)
        for (let 값 = 0; 값 <= 개인정보단서.length; 값++) {
            if (검사할_문장.includes(개인정보단서[값])) {
                발견됨 = true
                player.say("개인정보 단서 발견 : " + 개인정보단서[값])
            }
        }
        if (발견됨 == true) {
            player.say("이 문장에는 개인정보가 포함되어 있을 수 있어요!")
        } else {
            // @validate-exists
            player.say("이 문장에는 개인정보 단서가 없어요.")
        }
    }
})
```

## Step 17

완성했어요!

채팅창에 이렇게 입력해 보세요.

`검사 1`

또 다른 번호도 입력해 보세요.

`검사 6`

전화번호, 이메일, 주소 같은 말이 들어 있는 문장에서는 개인정보 단서가 발견될 거예요.

```package
literacy_class_makecode_extension=github:crosschang/literacy_class_makecode_extension#v1.0.0
```