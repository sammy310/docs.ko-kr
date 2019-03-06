---
title: ISOSDacInterface::GetMethodDescData 메서드
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
ms.openlocfilehash: 4e32facc65162c4deb853cd507a00126e5f786e7
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57352596"
---
# <a name="isosdacinterfacegetmethoddescdata-method"></a>ISOSDacInterface::GetMethodDescData 메서드

지정된 된 MethodDesc 포인터에 대 한 데이터를 가져옵니다.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a>구문

```
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
[in] 주소는 MethodDesc입니다.

`ip`\
[in] 메서드의 IP 주소입니다.

`data`\
[out] 내부 Api에서 반환 되는 MethodDesc와 연결 된 데이터입니다.

`cRevertedRejitVersions`\
[out] 되돌린된 rejit 버전 수입니다.

`rgRevertedRejitData`\
[out] 내부 Api에서 반환 된 되돌린된 rejit 버전과 연결 된 데이터입니다.

`pcNeededRevertedRejitData`\
[out] 되돌린된 ReJit 버전과 연결 된 데이터를 저장 하는 데 필요한 바이트 수입니다.

## <a name="remarks"></a>설명

제공 된 메서드는의 일부는 `ISOSDacInterface` 인터페이스 및 가상 메서드 테이블의 20 슬롯에 해당 합니다. 사용할 수 있으려면 [ `CLRDATA_ADDRESS` ](../common-data-types-unmanaged-api-reference.md) 64 비트 부호 없는 정수로 정의 해야 합니다.

## <a name="requirements"></a>요구 사항

**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
**헤더:** 없음  
**라이브러리:** 없음  
**.NET Framework 버전:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>참고자료

- [디버깅](index.md)
- [ISOSDacInterface 인터페이스](isosdacinterface-interface.md)