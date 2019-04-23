---
title: DacpGetModuleAddress::Request 메서드
ms.date: 01/16/2019
api.name:
- DacpGetModuleAddress::Request Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- DacpGetModuleAddress::Request Method
helpviewer.keywords:
- DacpGetModuleAddress::Request Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 298620092c37b2c02332e9135f73584272e326bd
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59111685"
---
# <a name="dacpgetmoduleaddressrequest-method"></a>DacpGetModuleAddress::Request 메서드

지정 된 런타임 구조에서 구조를 채우는 데 요청을 수행 합니다.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a>구문

```
HRESULT Request(
    [in] IXCLRDataModule* pDataModule
);
```

## <a name="parameters"></a>매개 변수

`pDataModule`\
[in] 초기값 데이터 모듈에 대 한 포인터입니다.

## <a name="remarks"></a>설명

이 구조는 런타임 내에서 있으며 모든 헤더 또는 라이브러리 파일을 통해 노출 되지 않습니다. 를 사용 하려면 구현을 모방 하는 가장 쉬운 방법은:

- 호출에서 얻은 값을 반환 합니다 `Request` 메서드는 `IXCLRDataModule*` 다음 매개 변수를 사용 하 여 매개 변수: `((uint32) 0xf0000000, 0, 0, (uint32) sizeof(*this), (uint8*) this)`

## <a name="requirements"></a>요구 사항

**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
**헤더:** 없음     
**라이브러리:** 없음  
**.NET Framework 버전:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>참고자료

- [디버깅](index.md)
- [DacpGetModuleAddress 인터페이스](dacpgetmoduleaddress-structure.md)