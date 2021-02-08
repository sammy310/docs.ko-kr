---
description: '자세히 알아보기: ICorDebugManagedCallback2:: Exception 메서드'
title: ICorDebugManagedCallback2::Exception 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback2.Exception
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback2::Exception
helpviewer_keywords:
- ICorDebugManagedCallback2::Exception method [.NET Framework debugging]
- Exception method, ICorDebugManagedCallback2 interface [.NET Framework debugging]
ms.assetid: 78b0f14f-2fae-4e63-8412-4df119ee8468
topic_type:
- apiref
ms.openlocfilehash: 18fd4efcfbd1f13ce527b212d7450ba0d7651a3c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99790883"
---
# <a name="icordebugmanagedcallback2exception-method"></a>ICorDebugManagedCallback2::Exception 메서드

예외 처리기에 대 한 검색이 시작 되었음을 디버거에 알립니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT Exception (  
    [in] ICorDebugAppDomain   *pAppDomain,  
    [in] ICorDebugThread      *pThread,  
    [in] ICorDebugFrame       *pFrame,  
    [in] ULONG32              nOffset,  
    [in] CorDebugExceptionCallbackType dwEventType,  
    [in] DWORD                dwFlags  
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `pAppDomain`  
 진행 예외가 throw 된 스레드를 포함 하는 응용 프로그램 도메인을 나타내는 ICorDebugAppDomain 개체에 대 한 포인터입니다.  
  
 `pThread`  
 진행 예외가 throw 된 스레드를 나타내는 ICorDebugThread 개체에 대 한 포인터입니다.  
  
 `pFrame`  
 진행 매개 변수에 의해 결정 되는 프레임을 나타내는 ICorDebugFrame 개체에 대 한 포인터입니다 `dwEventType` . 자세한 내용은 주의 섹션의 표를 참조 하십시오.  
  
 `nOffset`  
 진행 매개 변수에 의해 결정 되는 오프셋을 지정 하는 정수입니다 `dwEventType` . 자세한 내용은 주의 섹션의 표를 참조 하십시오.  
  
 `dwEventType`  
 진행 이 예외 콜백의 형식을 지정 하는 CorDebugExceptionCallbackType 열거형의 값입니다.  
  
 `dwFlags`  
 진행 예외에 대 한 추가 정보를 지정 하는 [Cordebugexceptionflags](cordebugexceptionflags-enumeration.md) 열거형의 값입니다.  
  
## <a name="remarks"></a>설명  

 `Exception`콜백은 예외 처리 프로세스의 검색 단계 중에 다양 한 지점에서 호출 됩니다. 즉, 예외를 해제 하는 동안 두 번 이상 호출할 수 있습니다.  
  
 처리 되는 예외는 매개 변수에서 참조 하는 ICorDebugThread 개체에서 검색할 수 있습니다 `pThread` .  
  
 특정 프레임과 오프셋은 매개 변수에 의해 다음과 같이 결정 됩니다 `dwEventType` .  
  
|`dwEventType`의 값|`pFrame`의 값|`nOffset`의 값|  
|----------------------------|-----------------------|------------------------|  
|DEBUG_EXCEPTION_FIRST_CHANCE|예외를 throw 한 프레임입니다.|프레임의 명령 포인터입니다.|  
|DEBUG_EXCEPTION_USER_FIRST_CHANCE|Throw 된 예외의 지점에 가장 가까운 사용자 코드 프레임입니다.|프레임의 명령 포인터입니다.|  
|DEBUG_EXCEPTION_CATCH_HANDLER_FOUND|Catch 처리기를 포함 하는 프레임입니다.|Catch 처리기 시작 부분의 MSIL (Microsoft 중간 언어) 오프셋입니다.|  
|DEBUG_EXCEPTION_UNHANDLED|NULL|정의되지 않았습니다.|  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [ICorDebugManagedCallback2 인터페이스](icordebugmanagedcallback2-interface.md)
- [ICorDebugManagedCallback 인터페이스](icordebugmanagedcallback-interface.md)
