---
title: ICorDebugFunction::GetNativeCode 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugFunction.GetNativeCode
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction::GetNativeCode
helpviewer_keywords:
- GetNativeCode method [.NET Framework debugging]
- ICorDebugFunction::GetNativeCode method [.NET Framework debugging]
ms.assetid: c8a34916-0eef-4987-8d29-c8bcb4be9cf6
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bb85c4b2c26c136a5f9fc05221a42c4bc99f37f9
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57470174"
---
# <a name="icordebugfunctiongetnativecode-method"></a>ICorDebugFunction::GetNativeCode 메서드
ICorDebugFunction 인스턴스에 의해 표현 되는 함수에 대 한 네이티브 코드를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetNativeCode (  
    [out] ICorDebugCode **ppCode  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `ppCode`  
 [out] 이 함수는 Microsoft intermediate language (MSIL) 코드-just-in-time (JIT) 컴파일된 되지 않은 경우이 함수 또는 null에 대 한 네이티브 코드를 나타내는 ICorDebugCode 인스턴스에 대 한 포인터입니다.  
  
## <a name="remarks"></a>설명  
 하는 경우이 표시 되는 함수 `ICorDebugFunction` 인스턴스는 JIT 컴파일된 두 번 이상 제네릭 형식을 경우와 같이 `GetNativeCode` 임의 네이티브 코드 개체를 반환 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
