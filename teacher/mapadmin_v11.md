```template
mapadmin.task(function() {

})
```

# 교사용 맵 관리 시스템

## Step 1

안녕하세요. 이곳은 **교사용 맵 관리 시스템**입니다.

이 튜토리얼에서는 선생님이 수업 맵을 관리할 수 있습니다.

할 수 있는 일은 다음과 같습니다.

- 특정 수업 방의 문 열기
- 수업용 구조물 또는 장치 초기화
- 맵 작동 상태 다시 준비하기

> ⚠️ 주의  
> 관리 블록은 한 번에 여러 개를 연결하지 않는 것이 좋습니다.  
> 문 열기, 초기화, 전체 초기화 같은 블록을 동시에 실행하면 맵 상태가 꼬일 수 있습니다.  
> 필요한 블록을 **하나만 넣고 실행한 뒤**, 결과를 확인하고 다음 작업을 진행하세요.

```ghost
mapadmin.opendoor_class(RoomNumber.One, Roomtype.Class)
mapadmin.start_class(RoomNumber.One)
mapadmin.end_class(PlayerNumber.One)
mapadmin.factory_initialization()
mapadmin.initialization()
mapadmin.end_class_all()
mapadmin.start_build_class(RoomNumber.One)
mapadmin.end_build_class()
```

```package
literacy_class_makecode_extension=github:crosschang/literacy_class_makecode_extension#v1.1.1
```