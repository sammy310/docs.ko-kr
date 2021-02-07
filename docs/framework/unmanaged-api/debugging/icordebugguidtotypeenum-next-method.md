---
description: '자세히 알아보기: ICorDebugGuidToTypeEnum:: Next 메서드'
title: ICorDebugGuidToTypeEnum::Next 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugGuidToTypeEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugGuidToTypeEnum::Next
helpviewer_keywords:
- ICorDebugGuidToTypeEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugGuidToTypeEnum interface [.NET Framework debugging]
ms.assetid: c9937666-8e18-484d-9fe0-b9ac95199530
topic_type:
- apiref
ms.openlocfilehash: 0ab05cc0689c76c0bb185205ea00c5ccebfcbe03
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99661001"
---
# <a name="icordebugguidtotypeenumnext-method"></a>ICorDebugGuidToTypeEnum::Next 메서드

Guid를 형식 정보에 매핑하는 지정 된 수의 [CorDebugGuidToTypeMapping](cordebugguidtotypemapping-structure.md) 인스턴스를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT Next(  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched] CorDebugGuidToTypeMapping values[  ],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `celt`  
 진행 검색할 GUID-형식 매핑 개체의 수입니다.  
  
 `values`  
 제한이 각각 Windows 런타임 GUID를 해당 ICorDebugType 개체에 매핑하는 [CorDebugGuidToTypeMapping](cordebugguidtotypemapping-structure.md) 개체를 가리키는 포인터의 배열입니다.  
  
 `pceltFetched`  
 제한이 에 실제로 반환 된 [CorDebugGuidToTypeMapping](cordebugguidtotypemapping-structure.md) 개체 수에 대 한 포인터입니다 `values` .  
  
## <a name="remarks"></a>설명  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:** Windows 런타임  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [ICorDebugGuidToTypeEnum 인터페이스](icordebugguidtotypeenum-interface.md)
- [디버깅 인터페이스](debugging-interfaces.md)
