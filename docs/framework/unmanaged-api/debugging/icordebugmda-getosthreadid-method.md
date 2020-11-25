---
title: ICorDebugMDA::GetOSThreadId 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugMDA.GetOSThreadId
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugMDA::GetOSThreadId
helpviewer_keywords:
- ICorDebugMDA::GetOSThreadId method [.NET Framework debugging]
- GetOSThreadId method [.NET Framework debugging]
ms.assetid: 7ca7c364-ade4-4219-b434-9f6ae2359be6
topic_type:
- apiref
ms.openlocfilehash: 80248bba6d11b8af07aa0517cb41c8a4f783b5e0
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95710898"
---
# <a name="icordebugmdagetosthreadid-method"></a>ICorDebugMDA::GetOSThreadId 메서드

[ICorDebugMDA](icordebugmda-interface.md) 가 나타내는 MDA (관리 디버깅 도우미)가 실행 중인 os (운영 체제) 스레드 식별자를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetOSThreadId (  
    [out] DWORD    *pOsTid  
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `pOsTid`  
 제한이 OS 스레드 식별자에 대 한 포인터입니다.  
  
## <a name="remarks"></a>설명  

 ICorDebugThread 대신 OS 스레드를 사용 하 여 네이티브 스레드나 관리 코드를 아직 입력 하지 않은 관리 되는 스레드에서 MDA가 발생 하는 상황을 허용할 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참조

- [ICorDebugMDA 인터페이스](icordebugmda-interface.md)
- [관리 디버깅 도우미를 사용하여 오류 진단](../../debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
