---
description: '자세히 알아보기: ICorDebug:: Terminate 메서드'
title: ICorDebug::Terminate 메서드
ms.date: 03/30/2017
api_name:
- ICorDebug.Terminate
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebug::Terminate
helpviewer_keywords:
- Terminate method, ICorDebug interface [.NET Framework debugging]
- ICorDebug::Terminate method [.NET Framework debugging]
ms.assetid: fffe5616-0896-4426-ab5e-21869b514883
topic_type:
- apiref
ms.openlocfilehash: c2de27a47bfd4c364a09180c75109679234f3cae
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99754292"
---
# <a name="icordebugterminate-method"></a>ICorDebug::Terminate 메서드

개체를 종료 `ICorDebug` 합니다.  
  
> [!NOTE]
> `Terminate` 디버깅 중인 모든 프로세스에 대해 [ICorDebugManagedCallback:: ExitProcess](icordebugmanagedcallback-exitprocess-method.md) 콜백이 수신 될 때까지 호출 하면 안 됩니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT Terminate ();  
```  
  
## <a name="remarks"></a>설명  

 `Terminate``ICorDebug`개체가 더 이상 필요 하지 않을 때를 호출 해야 합니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [ICorDebug 인터페이스](icordebug-interface.md)
