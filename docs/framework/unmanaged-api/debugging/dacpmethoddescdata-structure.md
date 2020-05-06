---
title: DacpMethodDescData 구조체
ms.date: 02/01/2019
api.name:
- DacpMethodDescData Structure
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- DacpMethodDescData Structure
helpviewer.keywords:
- DacpMethodDescData Structure [.NET Framework debugging]
topic_type:
- apiref
author: hoyosjs
ms.author: juhoyosa
ms.openlocfilehash: d623fe862eaf5902fd89d0e512dd07f73a03246f
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860810"
---
# <a name="dacpmethoddescdata-structure"></a>DacpMethodDescData 구조체

메서드의 런타임 정보에 대 한 전송 버퍼를 정의 합니다.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a>구문

```cpp
struct DacpMethodDescData
{
    int             bHasNativeCode;
    int             bIsDynamic;
    unsigned short  wSlotNumber;
    CLRDATA_ADDRESS NativeCodeAddr;
    CLRDATA_ADDRESS data;
    CLRDATA_ADDRESS MethodDescPtr;
    CLRDATA_ADDRESS nativeCodeInfo;
    CLRDATA_ADDRESS moduleInfo;
    mdToken         MDToken;
    CLRDATA_ADDRESS payloadGC;
    CLRDATA_ADDRESS payloadGC2;
    CLRDATA_ADDRESS managedDynamicMethodObject;
    CLRDATA_ADDRESS requestedIP;
    DacpReJitData   rejitDataCurrent;
    DacpReJitData   rejitDataRequested;
    unsigned long   cJittedRejitVersions;
};
```

## <a name="members"></a>구성원

| 멤버                       | Description                                                                                     |
| ---------------------------- | ----------------------------------------------------------------------------------------------- |
| `bHasNativeCode`             | 런타임에 메서드의 지정 된 인스턴스화에 사용할 수 있는 네이티브 코드가 있는지 여부를 나타냅니다. |
| `bIsDynamic`                 | 경량 코드 생성을 통해 메서드가 동적으로 생성 되는지 여부를 나타냅니다.           |
| `wSlotNumber`                | 메서드 테이블의 메서드 슬롯 번호입니다.                                                   |
| `NativeCodeAddr`             | 메서드의 초기 네이티브 주소입니다.                                                            |
| `data`                       | 런타임에서 내부적으로 사용 하는 버퍼에 대 한 포인터입니다.                                             |
| `MethodDescPtr`              | 런타임에 대 `MethodDesc` 한 포인터입니다.                                                     |
| `nativeCodeInfo`             | 런타임에서 메서드를 추적 하기 위해 내부적으로 사용 하는 버퍼에 대 한 포인터입니다.                            |
| `moduleInfo`                 | 모듈 정보에 대 한 런타임에서 내부적으로 사용 하는 버퍼에 대 한 포인터입니다.                      |
| `MDToken`                    | 지정 된 메서드와 연결 된 토큰입니다.                                                         |
| `payloadGC`                  | 런타임에서 내부적으로 사용 하는 가비지 컬렉션 버퍼에 대 한 포인터입니다.                          |
| `payloadGC2`                 | 런타임에서 내부적으로 사용 하는 가비지 컬렉션 버퍼에 대 한 포인터입니다.                          |
| `managedDynamicMethodObject` | 메서드가 동적 이면 런타임에서 정보 추적을 위해 내부적으로이 버퍼를 사용 합니다.     |
| `requestedIP`                | 네이티브 코드 주소가 지정 된 경우 요청당 구조를 채우는 데 사용 됩니다.                    |
| `rejitDataCurrent`           | 메서드의 최신 계측 된 버전에 대 한 정보입니다.                                   |
| `rejitDataRequested`         | 요청 된 기본 주소에 대 한 정보를 Rejit 합니다.                                             |
| `cJittedRejitVersions`       | 메서드가 계측을 통해 rejitted 된 횟수입니다.                           |

## <a name="remarks"></a>설명

이 구조체는 런타임 내에 있으며 헤더 또는 라이브러리 파일을 통해 노출 되지 않습니다. 이를 사용 하려면 위에 지정 된 대로 구조를 정의 합니다.

## <a name="requirements"></a>요구 사항
**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
**헤더:** 없음을  
**라이브러리:** 없음을  
**.NET Framework 버전:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>참고 항목

- [디버깅](index.md)
- [디버깅 구조체](debugging-structures.md)
- [공통 데이터 형식](../common-data-types-unmanaged-api-reference.md)
