---
title: ICorDebugClass2::SetJMCStatus 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugClass2.SetJMCStatus
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugClass2::SetJMCStatus
helpviewer_keywords:
- ICorDebugClass2::SetJMCStatus method [.NET Framework debugging]
- SetJMCStatus method, ICorDebugClass2 interface [.NET Framework debugging]
ms.assetid: 077e6c7f-f857-480c-bebb-76ee1de4e8fc
topic_type:
- apiref
ms.openlocfilehash: a862dd3f6a9c10c6b3a5a0bb41208d351c4ca9f1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125697"
---
# <a name="icordebugclass2setjmcstatus-method"></a>ICorDebugClass2::SetJMCStatus 메서드
클래스의 각 메서드에 대해 메서드가 사용자 정의 코드 인지 여부를 나타내는 값을 설정 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT SetJMCStatus (  
    [in] BOOL   bIsJustMyCode  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `bIsJustMyCode`  
 진행 메서드가 사용자 정의 코드 임을 나타내려면 `true`로 설정 합니다. 그렇지 않으면 `false`로 설정 합니다.  
  
## <a name="remarks"></a>주의  
 내 코드만 (JMC) 스텝 퍼는 사용자가 정의 하지 않은 코드를 건너뜁니다. 사용자 정의 코드는 디버깅 가능한 코드의 하위 집합 이어야 합니다.  
  
 모든 메서드에 대 한 값을 설정 하는 데 실패 한 경우에도 모든 메서드에 대 한 값을 설정 하는 데 실패 하는 경우 `SetJMCStatus` HRESULT 값을 반환 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
