---
title: ICorDebugThread2::GetTaskID 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugThread2.GetTaskID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread2::GetTaskID
helpviewer_keywords:
- ICorDebugThread2::GetTaskID method [.NET Framework debugging]
- GetTaskID method [.NET Framework debugging]
ms.assetid: 6ba3c6ee-4ba1-4c98-bf1e-8531acd3da09
topic_type:
- apiref
ms.openlocfilehash: 9b17a179745af65bde05527bd0157f3ce06c12c6
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95678670"
---
# <a name="icordebugthread2gettaskid-method"></a>ICorDebugThread2::GetTaskID 메서드

이 스레드에서 실행 중인 작업의 식별자를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetTaskID (  
    [out] TASKID  *pTaskId  
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `pTaskId`  
 제한이 이 ICorDebugThread2 개체가 나타내는 스레드에서 실행 중인 작업의 식별자에 대 한 포인터입니다.  
  
## <a name="remarks"></a>설명  

 스레드가 연결과 연결 된 경우에만 스레드에서 작업을 실행할 수 있습니다. `GetTaskID``pTaskId`스레드가 연결과 연결 되어 있지 않으면에서 0을 반환 합니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
