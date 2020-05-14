---
title: 'ISOSDacInterface:: GetMethodDescData 메서드'
ms.date: 01/16/2019
api.name:
- ISOSDacInterface::GetMethodDescData Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- ISOSDacInterface::GetMethodDescData Method
helpviewer.keywords:
- ISOSDacInterface::GetMethodDescData Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: e4c44379d9db0f5e98f3ca66ec0486961ec2df3a
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396939"
---
# <a name="isosdacinterfacegetmethoddescdata-method"></a>ISOSDacInterface:: GetMethodDescData 메서드

지정 된 MethodDesc 포인터에 대 한 데이터를 가져옵니다.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a>구문

```cpp
HRESULT GetMethodDescData(
    CLRDATA_ADDRESS            methodDesc,
    CLRDATA_ADDRESS            ip,
    DacpMethodDescData *data,
    ULONG                      cRevertedRejitVersions,
    DacpReJitData      *rgRevertedRejitData,
    void                      *pcNeededRevertedRejitData
);
```

## <a name="parameters"></a>매개 변수

`methodDesc`\
진행 MethodDesc의 주소입니다.

`ip`\
진행 메서드의 IP 주소입니다.

`data`\
제한이 내부 Api에서 반환 되는 MethodDesc와 연결 된 데이터입니다.

`cRevertedRejitVersions`\
제한이 되돌린 rejit 버전의 수입니다.

`rgRevertedRejitData`\
제한이 내부 Api에서 반환 된 대로 되돌린 rejit 버전과 연결 된 데이터입니다.

`pcNeededRevertedRejitData`\
제한이 되돌린 ReJit 버전과 연결 된 데이터를 저장 하는 데 필요한 바이트 수입니다.

## <a name="remarks"></a>설명

제공 된 메서드는 인터페이스의 일부 `ISOSDacInterface` 이며 가상 메서드 테이블의 21 슬롯에 해당 합니다. 이를 사용 하려면를 [`CLRDATA_ADDRESS`](../common-data-types-unmanaged-api-reference.md) 64 비트 부호 없는 정수로 정의 해야 합니다.

## <a name="requirements"></a>요구 사항

**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
**헤더:** 없음을  
**라이브러리:** 없음을  
**.NET Framework 버전:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>참조

- [디버깅](index.md)
- [ISOSDacInterface 인터페이스](isosdacinterface-interface.md)
