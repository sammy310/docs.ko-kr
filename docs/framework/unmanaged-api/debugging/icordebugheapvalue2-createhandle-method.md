---
title: ICorDebugHeapValue2::CreateHandle 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugHeapValue2.CreateHandle
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHeapValue2::CreateHandle
helpviewer_keywords:
- CreateHandle method [.NET Framework debugging]
- ICorDebugHeapValue2::CreateHandle method [.NET Framework debugging]
ms.assetid: fbc418e8-fa22-420d-84ec-e0e1800db041
topic_type:
- apiref
ms.openlocfilehash: c7a1bf3cb10cbc8cdae2788b45e1badaf66a9dbd
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178875"
---
# <a name="icordebugheapvalue2createhandle-method"></a>ICorDebugHeapValue2::CreateHandle 메서드
이 ICorDebugHeapValue2 개체로 표시되는 힙 값에 대해 지정된 형식의 핸들을 만듭니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT CreateHandle (  
    [in] CorDebugHandleType      type,
    [out] ICorDebugHandleValue   **ppHandle  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `type`  
 【인】 만들 핸들 의 형식을 지정 하는 CorDebugHandleType 열거형의 값입니다.  
  
 `ppHandle`  
 【아웃】 이 힙 값에 대한 새 핸들을 나타내는 ICorDebugHandleValue 개체의 주소에 대한 포인터입니다.  
  
## <a name="remarks"></a>설명  
 핸들은 힙 값과 연결된 응용 프로그램 도메인에서 만들어지며 응용 프로그램 도메인이 언로드되면 유효하지 않게 됩니다.  
  
 동일한 힙 값에 대해 이 함수를 여러 번 호출하면 여러 핸들이 생성됩니다. 핸들은 가비지 수집기의 성능에 영향을 미치기 때문에 디버거는 한 번에 활성 상태인 비교적 적은 수의 핸들(약 256개)으로 제한해야 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
