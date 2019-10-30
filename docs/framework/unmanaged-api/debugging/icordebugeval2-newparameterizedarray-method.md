---
title: ICorDebugEval2::NewParameterizedArray 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugEval2.NewParameterizedArray
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval2::NewParameterizedArray
helpviewer_keywords:
- ICorDebugEval2::NewParameterizedArray method [.NET Framework debugging]
- NewParameterizedArray method [.NET Framework debugging]
ms.assetid: 45efb8ba-c4de-4109-945f-e734d376b43c
topic_type:
- apiref
ms.openlocfilehash: 9476bcc9706e89fd3d7e0abc14031f70a0aa0ad0
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73084834"
---
# <a name="icordebugeval2newparameterizedarray-method"></a>ICorDebugEval2::NewParameterizedArray 메서드
지정 된 요소 형식 및 차원의 새 배열을 할당 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT NewParameterizedArray(  
    [in] ICorDebugType          *pElementType,  
    [in] ULONG32                rank,  
    [in, size_is(rank)] ULONG32 dims[],  
    [in, size_is(rank)] ULONG32 lowBounds[]  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `pElementType`  
 진행 배열에 저장 된 요소의 형식을 나타내는 ICorDebugType 개체에 대 한 포인터입니다.  
  
 `rank`  
 진행 배열의 차원 수입니다. .NET Framework 버전 2.0에서이 값은 1 이어야 합니다.  
  
 `dims`  
 진행 배열의 각 차원 크기 (바이트)입니다.  
  
 `lowBounds`  
 [in] 선택적 항목으로, 배열의 각 차원에 대 한 하 한입니다. 이 값을 생략 하면 각 차원에 대해 하 한이 0이 됩니다.  
  
## <a name="remarks"></a>주의  
 배열의 요소는 제네릭 형식의 인스턴스인 것일 수 있습니다. 배열은 항상 스레드가 현재 실행 중인 응용 프로그램 도메인에 만들어집니다. .NET Framework 2.0에서 `rank` 값은 1 이어야 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
