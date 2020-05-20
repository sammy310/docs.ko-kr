---
title: ISymUnmanagedAsyncMethod::IsAsyncMethod 메서드
ms.date: 03/30/2017
ms.assetid: 670a7653-dac6-4171-98ee-d669e3adf4b2
ms.openlocfilehash: 91b4c2688dadf12fa4a835a662622267d7831cf8
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/16/2020
ms.locfileid: "83441801"
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
  
## <a name="return-value"></a>Return Value  
 `HRESULT`를 반환합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** CorSym, CorSym  
  
## <a name="see-also"></a>참고 항목

- [ISymUnmanagedAsyncMethod 인터페이스](isymunmanagedasyncmethod-interface.md)
