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
ms.openlocfilehash: 278120c6e1bc87a061a3f81f71bdb7b89cd421be
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726563"
---
# <a name="icordebugheapvalue2createhandle-method"></a>ICorDebugHeapValue2::CreateHandle 메서드

이 ICorDebugHeapValue2 개체가 나타내는 힙 값에 대해 지정 된 형식의 핸들을 만듭니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT CreateHandle (  
    [in] CorDebugHandleType      type,
    [out] ICorDebugHandleValue   **ppHandle  
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `type`  
 진행 만들 핸들의 유형을 지정 하는 CorDebugHandleType 열거형의 값입니다.  
  
 `ppHandle`  
 제한이 이 힙 값의 새 핸들을 나타내는 ICorDebugHandleValue 개체의 주소에 대 한 포인터입니다.  
  
## <a name="remarks"></a>설명  

 이 핸들은 힙 값과 연결 된 응용 프로그램 도메인에 생성 되며 응용 프로그램 도메인이 언로드될 경우 유효 하지 않게 됩니다.  
  
 동일한 힙 값에 대해이 함수를 여러 번 호출 하면 여러 개의 핸들이 생성 됩니다. 핸들이 가비지 수집기의 성능에 영향을 주므로 디버거는 한 번에 활성 상태인 상대적으로 적은 수의 핸들 (약 256)으로 제한 해야 합니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
