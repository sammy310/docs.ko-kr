---
description: '자세히 알아보기: ICorDebugArrayValue:: GetDimensions 메서드'
title: ICorDebugArrayValue::GetDimensions 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugArrayValue.GetDimensions
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugArrayValue::GetDimensions
helpviewer_keywords:
- ICorDebugArrayValue::GetDimensions method [.NET Framework debugging]
- GetDimensions method [.NET Framework debugging]
ms.assetid: 6c116592-134b-4ef2-a319-680e92d013aa
topic_type:
- apiref
ms.openlocfilehash: 007a48891a01e5779e3f9ef10cec720d6647c8f3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99723103"
---
# <a name="icordebugarrayvaluegetdimensions-method"></a>ICorDebugArrayValue::GetDimensions 메서드

이 배열의 각 차원에 있는 요소의 수를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetDimensions (  
    [in] ULONG32         cdim,  
    [out, size_is(cdim), length_is(cdim)]
        ULONG32          dims[]  
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `cdim`  
 진행 이 ICorDebugArrayValue 개체의 차원 수입니다.  
  
 이 값은 `dims` 배열의 크기가 개체의 차원 수와 같으므로 배열의 크기 이기도 합니다 `ICorDebugArrayValue` .  
  
 `dims`  
 제한이 이 개체의 차원에 있는 요소의 수를 지정 하는 정수 배열입니다 `ICorDebugArrayValue` .  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
