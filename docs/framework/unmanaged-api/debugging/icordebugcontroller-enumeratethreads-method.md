---
description: '자세히 알아보기: ICorDebugController:: EnumerateThreads 메서드'
title: ICorDebugController::EnumerateThreads 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugController.EnumerateThreads
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugController::EnumerateThreads
helpviewer_keywords:
- ICorDebugController::EnumerateThreads method [.NET Framework debugging]
- EnumerateThreads method [.NET Framework debugging]
ms.assetid: 73f536f6-4668-4a4a-b3e4-ac7df862d5be
topic_type:
- apiref
ms.openlocfilehash: b53425de36be5a435ef0dac538c5165f41db63f2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99710779"
---
# <a name="icordebugcontrollerenumeratethreads-method"></a>ICorDebugController::EnumerateThreads 메서드

프로세스의 활성 관리 되는 스레드에 대 한 열거자를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT EnumerateThreads (  
    [out] ICorDebugThreadEnum **ppThreads  
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `ppThreads`  
 제한이 프로세스에서 활성화 된 모든 관리 되는 스레드에 대 한 열거자를 나타내는 "ICorDebugThreadEnum" 개체의 주소에 대 한 포인터입니다.  
  
## <a name="remarks"></a>설명  

 [ICorDebugManagedCallback:: CreateThread](icordebugmanagedcallback-createthread-method.md) 콜백이 디스패치 된 후, [ICorDebugManagedCallback:: exitthread](icordebugmanagedcallback-exitthread-method.md) 콜백이 디스패치 되기 전에는 스레드가 활성 상태인 것으로 간주 됩니다. 관리 되는 스레드의 스택에 관리 되는 프레임이 반드시 있어야 하는 것은 아닙니다. [ICorDebugManagedCallback:: CreateProcess](icordebugmanagedcallback-createprocess-method.md) 콜백 전에도 스레드를 열거할 수 있습니다. 열거형은 자연스럽 게 비어 있습니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목
