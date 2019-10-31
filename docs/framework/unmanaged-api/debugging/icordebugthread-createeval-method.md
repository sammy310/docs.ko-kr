---
title: ICorDebugThread::CreateEval 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugThread.CreateEval
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::CreateEval
helpviewer_keywords:
- CreateEval method [.NET Framework debugging]
- ICorDebugThread::CreateEval method [.NET Framework debugging]
ms.assetid: 36605067-33d3-4579-9c72-fb0e551ab0f1
topic_type:
- apiref
ms.openlocfilehash: 0c622e0eba27f501446d2b7d9d264ee0834e869c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133612"
---
# <a name="icordebugthreadcreateeval-method"></a>ICorDebugThread::CreateEval 메서드
이 ICorDebugThread의 기능을 수집 하 고 노출 하는 ICorDebugEval 개체를 만듭니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT CreateEval (  
    [out] ICorDebugEval   **ppEval  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `ppEval`  
 제한이 이 스레드의 기능을 수집 하 고 노출 하는 `ICorDebugEval` 개체의 주소에 대 한 포인터입니다.  
  
## <a name="remarks"></a>주의  
 계산 개체는 계산을 수행 하기 전에 스레드에 새 체인을 푸시합니다. 그러면 계산이 완료 될 때까지 현재 스레드에서 수행 중인 계산이 중단 됩니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
