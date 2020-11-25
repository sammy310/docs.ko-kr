---
title: ICorDebugProcess::IsOSSuspended 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.IsOSSuspended
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::IsOSSuspended
helpviewer_keywords:
- IsOSSuspended method [.NET Framework debugging]
- ICorDebugProcess::IsOSSuspended method [.NET Framework debugging]
ms.assetid: 83406cb2-5797-4402-872d-89c9516aefec
topic_type:
- apiref
ms.openlocfilehash: fffa61d8e406162251b0934a9846e5a813422798
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724587"
---
# <a name="icordebugprocessisossuspended-method"></a>ICorDebugProcess::IsOSSuspended 메서드

디버거에서이 프로세스를 중지 한 결과로 지정 된 스레드가 일시 중단 되었는지 여부를 나타내는 값을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT IsOSSuspended(  
    [in]  DWORD threadID,  
    [out] BOOL  *pbSuspended);  
```  
  
## <a name="parameters"></a>매개 변수  

 `threadID`  
 진행 해당 스레드의 ID입니다.  
  
 `pbSuspended`  
 제한이 `true` 지정 된 스레드가 일시 중단 되었으면이 고, 그렇지 않으면 인 부울 값에 대 한 포인터 `pbSuspended` 입니다 `false` .  
  
## <a name="remarks"></a>설명  

 디버거가이 프로세스를 중지 한 결과로 지정 된 스레드가 일시 중단 되 면 지정 된 스레드의 Win32 일시 중단 횟수가 1 씩 증가 합니다. 디버거 UI (사용자 인터페이스)는 사용자에 게 스레드의 OS (운영 체제) 일시 중단 횟수가 표시 되는 경우이 정보를 고려 하는 것이 좋습니다.  
  
 `IsOSSuspended`메서드는 관리 되지 않는 디버깅 컨텍스트에서만 의미가 있습니다. 관리 디버깅 중에는 스레드가 OS 일시 중단 되지 않고 협조적으로 일시 중단 됩니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
