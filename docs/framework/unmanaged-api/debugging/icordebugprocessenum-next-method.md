---
description: '자세히 알아보기: ICorDebugProcessEnum:: Next 메서드'
title: ICorDebugProcessEnum::Next 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugProcessEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcessEnum::Next
helpviewer_keywords:
- Next method, ICorDebugProcessEnum interface [.NET Framework debugging]
- ICorDebugProcessEnum::Next method [.NET Framework debugging]
ms.assetid: 4ac7077c-8d88-49c4-b360-b3af0c541c63
topic_type:
- apiref
ms.openlocfilehash: e32ff2e67f3f8a0242e0a0f93ed00229fee9cc26
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99691174"
---
# <a name="icordebugprocessenumnext-method"></a>ICorDebugProcessEnum::Next 메서드

현재 위치에서 시작 하 여 열거형에서 지정 된 수의 ICorDebugProcess 인스턴스를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT Next (  
    [in]  ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugProcess *processes[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `celt`  
 진행 `ICorDebugProcess` 검색할 인스턴스 수입니다.  
  
 `processes`  
 제한이 각각 프로세스를 나타내는 개체를 가리키는 포인터의 배열입니다 `ICorDebugProcess` .  
  
 `pceltFetched`  
 제한이 실제로 반환 된 인스턴스 수에 대 한 포인터 `ICorDebugProcess` 입니다. 이 일 경우이 값은 null 일 수 있습니다 `celt` .  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
