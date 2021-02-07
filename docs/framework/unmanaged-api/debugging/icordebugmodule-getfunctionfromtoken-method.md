---
description: '자세히 알아보기: ICorDebugModule:: GetFunctionFromToken 메서드'
title: ICorDebugModule::GetFunctionFromToken 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugModule.GetFunctionFromToken
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::GetFunctionFromToken
helpviewer_keywords:
- GetFunctionFromToken method, ICorDebugModule interface [.NET Framework debugging]
- ICorDebugModule::GetFunctionFromToken method [.NET Framework debugging]
ms.assetid: 6fe12194-4ef7-43c1-9570-ade35ccf127a
topic_type:
- apiref
ms.openlocfilehash: d6da43441f3774cff44a6f867c3ccf2a8581ebab
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99691655"
---
# <a name="icordebugmodulegetfunctionfromtoken-method"></a>ICorDebugModule::GetFunctionFromToken 메서드

메타 데이터 토큰에 의해 지정 된 함수를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetFunctionFromToken(  
    [in] mdMethodDef methodDef,  
    [out] ICorDebugFunction **ppFunction  
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `methodDef`  
 진행 `mdMethodDef` 함수의 메타 데이터를 참조 하는 메타 데이터 토큰입니다.  
  
 `ppFunction`  
 제한이 함수를 나타내는 ICorDebugFunction interface 개체의 주소에 대 한 포인터입니다.  
  
## <a name="remarks"></a>설명  

 `GetFunctionFromToken`전달 된 값 `methodDef` 이 MSIL (Microsoft 중간 언어) 메서드를 참조 하지 않는 경우 메서드는 CORDBG_E_FUNCTION_NOT_IL HRESULT를 반환 합니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
