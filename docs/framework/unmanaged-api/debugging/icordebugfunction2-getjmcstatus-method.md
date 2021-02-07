---
description: '자세히 알아보기: ICorDebugFunction2:: GetJMCStatus 메서드'
title: ICorDebugFunction2::GetJMCStatus 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugFunction2.GetJMCStatus
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction2::GetJMCStatus
helpviewer_keywords:
- ICorDebugFunction2::GetJMCStatus method [.NET Framework debugging]
- GetJMCStatus method [.NET Framework debugging]
ms.assetid: 840a71ed-bf5a-4f5e-8ed6-762222b34493
topic_type:
- apiref
ms.openlocfilehash: 42c72256df57b96a52737f4a0e5e90d6ba5d4e0c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99692292"
---
# <a name="icordebugfunction2getjmcstatus-method"></a>ICorDebugFunction2::GetJMCStatus 메서드

이 ICorDebugFunction2 개체가 나타내는 함수가 사용자 코드로 표시 되는지 여부를 나타내는 값을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetJMCStatus (  
    [out] BOOL   *pbIsJustMyCode  
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `pbIsJustMyCode`  
 제한이 부울 값에 대 한 포인터입니다 `true` .이 함수가 사용자 코드로 표시 되 면이 고, 그렇지 않으면 값은 `false` 입니다.  
  
## <a name="remarks"></a>설명  

 이가 나타내는 함수를 `ICorDebugFunction2` 디버그할 수 없는 경우 `pbIsJustMyCode` 는 항상 `false` 입니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
