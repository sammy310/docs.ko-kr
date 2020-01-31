---
title: ICorDebugManagedCallback::EvalException 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.EvalException
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::EvalException
helpviewer_keywords:
- EvalException method [.NET Framework debugging]
- ICorDebugManagedCallback::EvalException method [.NET Framework debugging]
ms.assetid: d6036345-18a3-45c1-a302-b1c6f2dced9b
topic_type:
- apiref
ms.openlocfilehash: 3ae93081bd201f745fa47bc01a9c6fcbf6e9f63c
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76781867"
---
# <a name="icordebugmanagedcallbackevalexception-method"></a>ICorDebugManagedCallback::EvalException 메서드
처리 되지 않은 예외를 사용 하 여 평가가 종료 되었음을 디버거에 알립니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT EvalException (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread    *pThread,  
    [in] ICorDebugEval      *pEval  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `pAppDomain`  
 진행 평가가 종료 된 응용 프로그램 도메인을 나타내는 ICorDebugAppDomain 개체에 대 한 포인터입니다.  
  
 `pThread`  
 진행 평가가 종료 된 스레드를 나타내는 ICorDebugThread 개체에 대 한 포인터입니다.  
  
 `pEval`  
 진행 계산을 수행 하는 코드를 나타내는 ICorDebugEval 개체에 대 한 포인터입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참조

- [ICorDebugManagedCallback 인터페이스](icordebugmanagedcallback-interface.md)
