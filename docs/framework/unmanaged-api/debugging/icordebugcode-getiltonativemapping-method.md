---
description: '자세히 알아보기: ICorDebugCode:: GetILToNativeMapping 메서드'
title: ICorDebugCode::GetILToNativeMapping 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugCode.GetILToNativeMapping
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode::GetILToNativeMapping
helpviewer_keywords:
- GetILToNativeMapping method, ICorDebugCode interface [.NET Framework debugging]
- ICorDebugCode::GetILToNativeMapping method [.NET Framework debugging]
ms.assetid: a8ecd8c8-9627-4356-9c6f-bd05e24637c0
topic_type:
- apiref
ms.openlocfilehash: 808ed450fced8afecc2b637a3b990a894897b350
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99711195"
---
# <a name="icordebugcodegetiltonativemapping-method"></a>ICorDebugCode::GetILToNativeMapping 메서드

MSIL (Microsoft 중간 언어) 오프셋에서 네이티브 오프셋으로의 매핑을 나타내는 "COR_DEBUG_IL_TO_NATIVE_MAP" 인스턴스의 배열을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetILToNativeMapping (  
    [in]  ULONG32    cMap,  
    [out] ULONG32    *pcMap,  
    [out, size_is(cMap), length_is(*pcMap)]  
        COR_DEBUG_IL_TO_NATIVE_MAP map[]  
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `cMap`  
 [in] `map` 배열의 크기입니다.  
  
 `pcMap`  
 제한이 배열에 반환 된 실제 요소 수에 대 한 포인터 `map` 입니다.  
  
 `map`  
 제한이 `COR_DEBUG_IL_TO_NATIVE_MAP` 각각 MSIL 오프셋에서 네이티브 오프셋으로의 매핑을 나타내는 구조체의 배열입니다.  
  
 반환 되는 요소의 배열에 대 한 순서는 없습니다.  
  
## <a name="remarks"></a>설명  

 `GetILToNativeMapping`메서드는이 "ICorDebugCode" 인스턴스가 MSIL 코드에서 JIT (just-in-time) 컴파일된 네이티브 코드를 나타내는 경우에만 의미 있는 결과를 반환 합니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [ICorDebugCode 인터페이스](icordebugcode-interface1.md)
