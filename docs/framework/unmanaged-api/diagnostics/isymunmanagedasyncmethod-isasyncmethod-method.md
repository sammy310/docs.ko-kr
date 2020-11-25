---
title: ISymUnmanagedAsyncMethod::IsAsyncMethod 메서드
ms.date: 03/30/2017
ms.assetid: 670a7653-dac6-4171-98ee-d669e3adf4b2
ms.openlocfilehash: af02aba1a0d390c103e8c6108f90b93fe2a98ff3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95707154"
---
# <a name="isymunmanagedasyncmethodisasyncmethod-method"></a>ISymUnmanagedAsyncMethod::IsAsyncMethod 메서드

메서드에 비동기 정보가 있는지 여부를 확인 합니다.  
  
 이 메서드가를 반환 `FALSE` 하는 경우이 인터페이스에서 다른 메서드를 호출할 수 없습니다. 이 경우 모두 반환 됩니다 `E_UNEXPECTED` .  
  
## <a name="syntax"></a>구문  
  
```idl  
HRESULT IsAsyncMethod(    [out, retval] BOOL* pRetVal);  
```  
  
## <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|`pRetVal`||  
  
## <a name="return-value"></a>반환 값  

 `HRESULT`를 반환합니다.  
  
## <a name="requirements"></a>요구 사항  

 **헤더:** CorSym, CorSym  
  
## <a name="see-also"></a>참조

- [ISymUnmanagedAsyncMethod 인터페이스](isymunmanagedasyncmethod-interface.md)
