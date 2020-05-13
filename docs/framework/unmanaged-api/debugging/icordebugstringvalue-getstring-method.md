---
title: ICorDebugStringValue::GetString 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugStringValue.GetString
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStringValue::GetString
helpviewer_keywords:
- ICorDebugStringValue::GetString method [.NET Framework debugging]
- GetString method, ICorDebugStringValue interface [.NET Framework debugging]
ms.assetid: 2b94bda7-09ee-435d-91b9-c4e31af1896c
topic_type:
- apiref
ms.openlocfilehash: 9c154d4ad561e0bd9d82adaca77d2e30f11a5237
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379661"
---
# <a name="icordebugstringvaluegetstring-method"></a>ICorDebugStringValue::GetString 메서드
이 ICorDebugStringValue에서 참조 하는 문자열을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetString (  
    [in] ULONG32    cchString,  
    [out] ULONG32   *pcchString,  
    [out, size_is(cchString), length_is(*pcchString)]
        WCHAR       szString[]  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `cchString`  
 [in] `szString` 배열의 크기입니다.  
  
 `pcchString`  
 제한이 배열에 반환 된 문자 수에 대 한 포인터 `szString` 입니다.  
  
 `szString`  
 제한이 검색 된 문자열을 저장 하는 배열입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
