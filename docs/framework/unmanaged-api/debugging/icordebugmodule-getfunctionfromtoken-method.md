---
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c1af0f8f792c856c0b27b4d3d9ff557bcc5fce82
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57500072"
---
# <a name="icordebugmodulegetfunctionfromtoken-method"></a>ICorDebugModule::GetFunctionFromToken 메서드
메타 데이터 토큰이 지정 된 함수를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetFunctionFromToken(  
    [in] mdMethodDef methodDef,  
    [out] ICorDebugFunction **ppFunction  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `methodDef`  
 [in] `mdMethodDef` 함수의 메타 데이터를 참조 하는 메타 데이터 토큰입니다.  
  
 `ppFunction`  
 [out] 함수를 나타내는 ICorDebugFunction 인터페이스 개체의 주소에 대 한 포인터입니다.  
  
## <a name="remarks"></a>설명  
 합니다 `GetFunctionFromToken` 메서드 값을 전달 하는 경우 CORDBG_E_FUNCTION_NOT_IL HRESULT를 반환 합니다 `methodDef` Microsoft 중간 언어 (MSIL) 메서드를 참조 하지 않습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
