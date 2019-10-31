---
title: ICorDebugNativeFrame::GetIP 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame.GetIP
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame::GetIP
helpviewer_keywords:
- GetIP method, ICorDebugNativeFrame interface [.NET Framework debugging]
- ICorDebugNativeFrame::GetIP method [.NET Framework debugging]
ms.assetid: 99f693f3-d3b9-4fd8-9d09-b8efd03f7b67
topic_type:
- apiref
ms.openlocfilehash: 3011a8c7e5cf278768587633967b2e9491cf87ac
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137330"
---
# <a name="icordebugnativeframegetip-method"></a>ICorDebugNativeFrame::GetIP 메서드
명령 포인터가 현재 설정 된 네이티브 코드 오프셋 위치를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetIP (  
    [out] ULONG32           *pnOffset  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `pnOffset`  
 제한이 네이티브 코드의 오프셋 위치에 대 한 포인터입니다.  
  
## <a name="remarks"></a>주의  
 이 "ICorDebugNativeFrame"로 표시 되는 스택 프레임이 활성화 된 경우 오프셋은 실행할 다음 명령의 주소입니다. 이 스택 프레임이 활성화 되어 있지 않으면 오프셋은 스택 프레임을 다시 활성화할 때 실행 되는 다음 명령의 주소입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참조
