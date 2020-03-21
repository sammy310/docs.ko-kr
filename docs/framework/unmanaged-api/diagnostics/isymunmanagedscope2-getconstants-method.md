---
title: ISymUnmanagedScope2::GetConstants 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope2.GetConstants
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope2::GetConstants
helpviewer_keywords:
- ISymUnmanagedScope2::GetConstants method [.NET Framework debugging]
- GetConstants method [.NET Framework debugging]
ms.assetid: f241b620-9ec5-42fd-92ef-3b22329db72a
topic_type:
- apiref
ms.openlocfilehash: 45268929b6e9ad6ac6423aa0fa2b7b5022bc9179
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176619"
---
# <a name="isymunmanagedscope2getconstants-method"></a>ISymUnmanagedScope2::GetConstants 메서드
이 범위 내에서 정의된 로컬 상수를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetConstants(  
     [in]  ULONG32  cConstants,  
     [out] ULONG32  *pcConstants,  
     [out, size_is(cConstants),  
         length_is(*pcConstants)] ISymUnmanagedConstant*
             constants[]);  
```  
  
## <a name="parameters"></a>매개 변수  
 `cConstants`  
 【인】 매개 변수가 가리키는 `pcConstants` 버퍼의 길이입니다.  
  
 `pcConstants`  
 【아웃】 상수를 포함 `ULONG32` 하는 데 필요한 버퍼의 크기(문자)를 받는 a에 대한 포인터입니다.  
  
 `constants`  
 【아웃】 상수를 저장하는 버퍼입니다.  
  
## <a name="return-value"></a>Return Value  
 메서드가 성공하면 S_OK. 그렇지 않으면 E_FAIL 또는 다른 오류 코드가 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** 코르심.idl, 코르심.h  
  
## <a name="see-also"></a>참고 항목

- [ISymUnmanagedScope2 인터페이스](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope2-interface.md)
