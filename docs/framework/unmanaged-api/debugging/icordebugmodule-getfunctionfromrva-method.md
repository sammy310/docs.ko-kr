---
title: ICorDebugModule::GetFunctionFromRVA 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugModule.GetFunctionFromRVA
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::GetFunctionFromRVA
helpviewer_keywords:
- GetFunctionFromRVA method [.NET Framework debugging]
- ICorDebugModule::GetFunctionFromRVA method [.NET Framework debugging]
ms.assetid: f5a34517-2422-484f-be89-2ce0b4bce195
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: edd9407f05e30eb420e83fb042c2412e99b0a022
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61953753"
---
# <a name="icordebugmodulegetfunctionfromrva-method"></a>ICorDebugModule::GetFunctionFromRVA 메서드
이 메서드는 현재 버전의.NET Framework에서 구현 되지에.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetFunctionFromRVA(  
    [in]  CORDB_ADDRESS      rva,  
    [out] ICorDebugFunction  **ppFunction  
);  
```  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** CorDebug.idl, CorDebug.h  
  
## <a name="see-also"></a>참고자료
