---
title: ISymENCUnmanagedMethod::GetDocumentsForMethod 메서드
ms.date: 03/30/2017
api_name:
- ISymENCUnmanagedMethod.GetDocumentsForMethod
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymENCUnmanagedMethod::GetDocumentsForMethod
helpviewer_keywords:
- GetDocumentsForMethod method [.NET Framework debugging]
- ISymENCUnmanagedMethod::GetDocumentsForMethod method [.NET Framework debugging]
ms.assetid: bd6ccde5-d578-48d8-abed-b474fbd48d13
topic_type:
- apiref
ms.openlocfilehash: 97f0d81c389ffd0bd8a69df2ca39322d726f98bc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176632"
---
# <a name="isymencunmanagedmethodgetdocumentsformethod-method"></a>ISymENCUnmanagedMethod::GetDocumentsForMethod 메서드
이 메서드에 줄이 있는 문서를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetDocumentsForMethod(  
    [in]  ULONG32  cDocs,  
    [out] ULONG32  *pcDocs,
    [in, size_is(cDocs)] ISymUnmanagedDocument* documents[]);  
```  
  
## <a name="parameters"></a>매개 변수  
 `cDocs`  
 【인】 을 가리키는 버퍼의 `pcDocs`길이입니다.  
  
 `pcDocs`  
 【아웃】 문서를 포함하는 `ULONG32` 데 필요한 버퍼의 크기(문자)를 받는 a에 대한 포인터입니다.  
  
 `documents`  
 【인】 문서를 포함하는 버퍼입니다.  
  
## <a name="return-value"></a>Return Value  
 메서드가 성공하면 S_OK. 그렇지 않으면 오류 코드입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** 코르심.idl, 코르심.h  
  
## <a name="see-also"></a>참고 항목

- [ISymENCUnmanagedMethod 인터페이스](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-interface.md)
