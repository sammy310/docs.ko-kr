---
title: ISymUnmanagedDocument::GetSourceLength 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocument.GetSourceLength
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument::GetSourceLength
helpviewer_keywords:
- GetSourceLength method [.NET Framework debugging]
- ISymUnmanagedDocument::GetSourceLength method [.NET Framework debugging]
ms.assetid: e087dbbb-f4fb-4fbe-8292-e4f1a14d0df2
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2717a279abf7fb1b704a769d54654d97949cc0a2
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59136905"
---
# <a name="isymunmanageddocumentgetsourcelength-method"></a>ISymUnmanagedDocument::GetSourceLength 메서드
포함 소스의 길이(바이트)를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetSourceLength(  
    [out, retval]  ULONG32*  pRetVal);  
```  
  
## <a name="parameters"></a>매개 변수  
 `pRetVal`  
 [out] 포함 소스의 길이 (바이트)를 지정 하는 변수에 대 한 포인터입니다.  
  
## <a name="return-value"></a>반환 값  
 메서드가 성공 하면 S_OK입니다.  
  
## <a name="see-also"></a>참고자료

- [ISymUnmanagedDocument 인터페이스](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)
