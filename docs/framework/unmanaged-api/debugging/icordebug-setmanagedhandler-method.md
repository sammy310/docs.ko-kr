---
title: ICorDebug::SetManagedHandler 메서드
ms.date: 03/30/2017
api_name:
- ICorDebug.SetManagedHandler
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebug::SetManagedHandler
helpviewer_keywords:
- ICorDebug::SetManagedHandler method [.NET Framework debugging]
- SetManagedHandler method [.NET Framework debugging]
ms.assetid: d079131b-685b-4869-95be-826b88d28bd2
topic_type:
- apiref
ms.openlocfilehash: 97a4a464d3dfb7b333f44ac4206bd880fd171e16
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723417"
---
# <a name="icordebugsetmanagedhandler-method"></a>ICorDebug::SetManagedHandler 메서드

관리 되는 이벤트에 대 한 이벤트 처리기 개체를 지정 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT SetManagedHandler (  
    [in] ICorDebugManagedCallback     *pCallback  
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `pCallback`  
 진행 이벤트 처리기 개체인 [ICorDebugManagedCallback](icordebugmanagedcallback-interface.md) 개체에 대 한 포인터입니다.  
  
## <a name="remarks"></a>설명  

 `SetManagedHandler` 만들 때를 호출 해야 합니다.  
  
 구현에 디버깅 `ICorDebugManagedCallback` 중인 응용 프로그램에 대 한 디버깅 이벤트를 처리 하기에 충분 한 인터페이스가 포함 되지 않은 경우 `SetManagedHandler` E_NOINTERFACE의 HRESULT를 반환 합니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참조

- [ICorDebug 인터페이스](icordebug-interface.md)
