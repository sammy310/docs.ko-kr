---
title: ICorDebugILFrame::GetIP 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame.GetIP
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame::GetIP
helpviewer_keywords:
- GetIP method, ICorDebugILFrame interface [.NET Framework debugging]
- ICorDebugILFrame::GetIP method [.NET Framework debugging]
ms.assetid: 18217ba1-1776-4297-a3b9-f77e64b0fead
topic_type:
- apiref
ms.openlocfilehash: 314d2a06c8e246a42b315690dc9fe4b507db285a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95703176"
---
# <a name="icordebugilframegetip-method"></a>ICorDebugILFrame::GetIP 메서드

명령 포인터의 값과 명령 포인터의 값을 가져오는 방법을 설명 하는 비트 조합 값을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetIP (  
    [out] ULONG32               *pnOffset,
    [out] CorDebugMappingResult *pMappingResult  
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `pnOffset`  
 제한이 명령 포인터의 값입니다.  
  
 `pMappingResult`  
 제한이 명령 포인터의 값을 가져오는 방법을 설명 하는 CorDebugMappingResult 열거형 값의 비트 조합에 대 한 포인터입니다.  
  
## <a name="remarks"></a>설명  

 명령 포인터의 값은 함수의 MSIL (Microsoft 중간 언어) 코드에 대 한 스택 프레임의 오프셋입니다. 스택 프레임이 활성 상태인 경우이 주소는 다음에 실행할 명령입니다. 스택 프레임이 활성 상태가 아닌 경우이 주소는 스택 프레임이 다시 활성화 될 때 실행할 다음 명령입니다.  
  
 이 프레임이 JIT (just-in-time) 컴파일된 프레임 인 경우 실제 네이티브 명령 포인터에서 역방향으로 매핑하여 명령 포인터의 값이 결정 되므로 값은 근사값이 될 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
