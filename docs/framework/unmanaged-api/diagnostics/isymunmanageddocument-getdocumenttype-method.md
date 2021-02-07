---
description: '자세히 알아보기: ISymUnmanagedDocument:: GetDocumentType 메서드'
title: ISymUnmanagedDocument::GetDocumentType 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocument.GetDocumentType
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument::GetDocumentType
helpviewer_keywords:
- ISymUnmanagedDocument::GetDocumentType method [.NET Framework debugging]
- GetDocumentType method [.NET Framework debugging]
ms.assetid: 2d381ab1-7e7c-4281-af2b-e54d879b3ef8
topic_type:
- apiref
ms.openlocfilehash: cf2ceffccb33eb7cba0d45af203e12d1e4244f60
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99710324"
---
# <a name="isymunmanageddocumentgetdocumenttype-method"></a>ISymUnmanagedDocument::GetDocumentType 메서드

이 문서의 문서 유형을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetDocumentType(  
    [out, retval] GUID*  pRetVal);  
```  
  
## <a name="parameters"></a>매개 변수  

 `pRetVal`  
 제한이 문서 유형을 받는 변수에 대 한 포인터입니다.  
  
## <a name="return-value"></a>Return Value  

 메서드가 성공 하면 S_OK 합니다.  
  
## <a name="see-also"></a>참고 항목

- [ISymUnmanagedDocument 인터페이스](isymunmanageddocument-interface.md)
