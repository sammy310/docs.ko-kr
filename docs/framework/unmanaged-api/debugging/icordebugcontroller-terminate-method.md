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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c4c8dd8795fc3699176490ea0bb9b2e999038afb
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59124880"
---
# <a name="icordebugcontrollerterminate-method"></a>ICorDebugController::Terminate 메서드
지정된 된 종료 코드를 사용 하 여 프로세스를 종료합니다.  
  
> [!NOTE]
>  이 메서드는 Win32에 대 한 래퍼 `TerminateProcess` 함수입니다. 따라서 `Terminate` 종료 코드를 사용 하 여 동일한 방식으로 Win32 `TerminateProcess` 함수 사용 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT Terminate (  
    [in] UINT exitCode  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `exitCode`  
 [in] 종료 코드는 숫자 값입니다. 유효한 숫자 값 Winbase.h에 정의 됩니다.  
  
## <a name="remarks"></a>설명  
 프로세스를 중지 될 때 `Terminate` 는 호출 프로세스는 계속 사용 하 여는 [icordebugcontroller:: Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) 메서드 디버거를 통해 종료에 대 한 확인을 받을 수 있도록는 [ Icordebugmanagedcallback:: Exitprocess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitprocess-method.md) 나 [icordebugmanagedcallback:: Exitappdomain](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitappdomain-method.md) 콜백 합니다.  
  
> [!NOTE]
>  이 메서드는 응용 프로그램 도메인 별로 구현 되지 않았습니다. 즉,에서 구현 되지 않습니다는 <xref:System.AppDomain> 수준입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고자료
