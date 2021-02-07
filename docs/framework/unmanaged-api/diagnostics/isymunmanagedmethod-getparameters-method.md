---
description: '자세히 알아보기: ISymUnmanagedMethod:: GetParameters 메서드'
title: ISymUnmanagedMethod::GetParameters 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedMethod.GetParameters
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod::GetParameters
helpviewer_keywords:
- ISymUnmanagedMethod::GetParameters method [.NET Framework debugging]
- GetParameters method [.NET Framework debugging]
ms.assetid: 3a8074f1-facc-4a3f-bb9b-d6574fc2fc74
topic_type:
- apiref
ms.openlocfilehash: c8860a4d42019aaacef01879b175fd45ea837f2b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99721374"
---
# <a name="isymunmanagedmethodgetparameters-method"></a>ISymUnmanagedMethod::GetParameters 메서드

이 메서드에 대 한 매개 변수를 가져옵니다. 매개 변수는 메서드 서명 내에서 정의 된 순서 대로 반환 됩니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetParameters(  
    [in]  ULONG32  cParams,  
    [out] ULONG32  *pcParams,  
    [out, size_is(cParams),  
        length_is(*pcParams)] ISymUnmanagedVariable*  params[]);  
```  
  
## <a name="parameters"></a>매개 변수  

 `cParams`  
 [in] `params` 배열의 크기입니다.  
  
 `pcParams`  
 진행 `ULONG32` 매개 변수를 포함 하는 데 필요한 버퍼의 크기를 수신 하는에 대 한 포인터입니다.  
  
 `params`  
 제한이 매개 변수를 받는 버퍼에 대 한 포인터입니다.  
  
## <a name="return-value"></a>Return Value  

 메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.  
  
## <a name="requirements"></a>요구 사항  

 **헤더:** CorSym, CorSym  
  
## <a name="see-also"></a>참고 항목

- [ISymUnmanagedMethod 인터페이스](isymunmanagedmethod-interface.md)
