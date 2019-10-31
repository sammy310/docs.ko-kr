---
title: ICorDebugController::Terminate 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugController.Terminate
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugController::Terminate
helpviewer_keywords:
- Terminate method, ICorDebugController interface [.NET Framework debugging]
- ICorDebugController::Terminate method [.NET Framework debugging]
ms.assetid: 4275af0c-b5a7-4e4c-97c9-7e41f36b2dd8
topic_type:
- apiref
ms.openlocfilehash: fb8cfb2d1c5902ecd0d5858ef21ba48b65b12506
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125326"
---
# <a name="icordebugcontrollerterminate-method"></a>ICorDebugController::Terminate 메서드
지정 된 종료 코드를 사용 하 여 프로세스를 종료 합니다.  
  
> [!NOTE]
> 이 메서드는 Win32 `TerminateProcess` 함수에 대 한 래퍼입니다. 따라서 `Terminate`는 Win32 `TerminateProcess` 함수에서 사용 하는 것과 동일한 방식으로 종료 코드를 사용 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT Terminate (  
    [in] UINT exitCode  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `exitCode`  
 진행 종료 코드 인 숫자 값입니다. 유효한 숫자 값은 Winbase. h에 정의 되어 있습니다.  
  
## <a name="remarks"></a>주의  
 `Terminate`가 호출 될 때 프로세스가 중지 되는 경우 디버거는 ICorDebugManagedCallback::를 통해 종료에 대 한 확인을 받을 수 있도록 [ICorDebugController:: Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) 메서드를 사용 하 여 프로세스를 계속 진행 해야 합니다. [ ExitProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitprocess-method.md) 또는 [ICorDebugManagedCallback:: exitprocess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitappdomain-method.md) 콜백입니다.  
  
> [!NOTE]
> 이 메서드는 응용 프로그램 도메인에서 구현 되지 않습니다. 즉, <xref:System.AppDomain> 수준에서 구현 되지 않습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참조
