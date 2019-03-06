---
title: ISymUnmanagedAsyncMethod::IsAsyncMethod 메서드
ms.date: 03/30/2017
ms.assetid: 670a7653-dac6-4171-98ee-d669e3adf4b2
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 460d6781405b6042262d50e1aa79ee8c77f781a7
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57489725"
---
# <a name="isymunmanagedasyncmethodisasyncmethod-method"></a>ISymUnmanagedAsyncMethod::IsAsyncMethod 메서드
경우 메서드가 async 정보 여부를 확인 합니다.  
  
 이 메서드가 반환 하는 경우 `FALSE` 이 인터페이스에서 다른 메서드를 호출 하는 유효 하지 않습니다. 모든 반환 되며이 `E_UNEXPECTED` 이 경우.  
  
## <a name="syntax"></a>구문  
  
```idl  
HRESULT IsAsyncMethod(    [out, retval] BOOL* pRetVal);  
```  
  
## <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|`pRetVal`||  
  
## <a name="return-value"></a>반환 값  
 `HRESULT`을 반환합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>참고자료
- [ISymUnmanagedAsyncMethod 인터페이스](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-interface.md)
