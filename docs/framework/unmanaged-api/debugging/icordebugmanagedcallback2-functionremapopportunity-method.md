---
title: ICorDebugManagedCallback2::FunctionRemapOpportunity 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback2.FunctionRemapOpportunity
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback2::FunctionRemapOpportunity
helpviewer_keywords:
- FunctionRemapOpportunity method [.NET Framework debugging]
- ICorDebugManagedCallback2::FunctionRemapOpportunity method [.NET Framework debugging]
ms.assetid: 0d6471bc-ad9b-4b1d-a307-c10443918863
topic_type:
- apiref
ms.openlocfilehash: 50fabec08a63d348b0a1934f029582ae1446519e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729059"
---
# <a name="icordebugmanagedcallback2functionremapopportunity-method"></a>ICorDebugManagedCallback2::FunctionRemapOpportunity 메서드

코드 실행이 이전 버전의 편집 된 함수에서 시퀀스 위치에 도달 했음을 디버거에 알립니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT FunctionRemapOpportunity (  
    [in] ICorDebugAppDomain   *pAppDomain,  
    [in] ICorDebugThread      *pThread,  
    [in] ICorDebugFunction    *pOldFunction,  
    [in] ICorDebugFunction    *pNewFunction,  
    [in] ULONG32              oldILOffset  
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `pAppDomain`  
 진행 편집 된 함수를 포함 하는 응용 프로그램 도메인을 나타내는 ICorDebugAppDomain 개체에 대 한 포인터입니다.  
  
 `pThread`  
 진행 다시 매핑 중단점이 발생 한 스레드를 나타내는 ICorDebugThread 개체에 대 한 포인터입니다.  
  
 `pOldFunction`  
 진행 스레드에서 현재 실행 중인 함수의 버전을 나타내는 ICorDebugFunction 개체에 대 한 포인터입니다.  
  
 `pNewFunction`  
 진행 함수의 최신 버전을 나타내는 ICorDebugFunction 개체에 대 한 포인터입니다.  
  
 `oldILOffset`  
 진행 이전 버전의 함수에 있는 명령 포인터의 MSIL (Microsoft 중간 언어) 오프셋입니다.  
  
## <a name="remarks"></a>설명  

 이 콜백은 디버거가 [ICorDebugILFrame2:: RemapFunction](icordebugilframe2-remapfunction-method.md) 메서드를 호출 하 여 지정 된 함수의 새 버전에서 적절 한 위치에 명령 포인터를 다시 매핑할 수 있는 기회를 제공 합니다. 디버거가 `RemapFunction` [ICorDebugController:: Continue](icordebugcontroller-continue-method.md) 메서드를 호출 하기 전에를 호출 하지 않으면 런타임은 이전 코드를 계속 실행 하 고 `FunctionRemapOpportunity` 다음 시퀀스 위치에서 다른 콜백을 실행 합니다.  
  
 이 콜백은 디버거가 S_OK 반환 될 때까지 지정 된 함수의 이전 버전을 실행 하는 모든 프레임에 대해 호출 됩니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참조

- [ICorDebugManagedCallback2 인터페이스](icordebugmanagedcallback2-interface.md)
- [ICorDebugManagedCallback 인터페이스](icordebugmanagedcallback-interface.md)
