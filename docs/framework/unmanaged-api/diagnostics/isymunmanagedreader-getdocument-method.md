---
description: '자세히 알아보기: ISymUnmanagedReader:: GetDocument 메서드'
title: ISymUnmanagedReader::GetDocument 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetDocument
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetDocument
helpviewer_keywords:
- ISymUnmanagedReader::GetDocument method [.NET Framework debugging]
- GetDocument method [.NET Framework debugging]
ms.assetid: bb203853-6a6d-4027-b9e9-603a7f28b9d3
topic_type:
- apiref
ms.openlocfilehash: 7f2f31467cfd00de68737224a2c1af5b1e78efed
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99764101"
---
# <a name="isymunmanagedreadergetdocument-method"></a>ISymUnmanagedReader::GetDocument 메서드

문서를 찾습니다. 문서 언어, 공급 업체 및 형식은 선택 사항입니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetDocument (  
    [in]  WCHAR  *url,  
    [in]  GUID   language,  
    [in]  GUID   languageVendor,  
    [in]  GUID   documentType,  
    [out, retval] ISymUnmanagedDocument** pRetVal);  
```  
  
## <a name="parameters"></a>매개 변수  

 `url`  
 진행 문서를 식별 하는 URL입니다.  
  
 `language`  
 진행 문서 언어입니다. 이 매개 변수는 선택적 요소입니다.  
  
 `languageVendor`  
 진행 문서 언어의 공급 업체 id입니다. 이 매개 변수는 선택적 요소입니다.  
  
 `documentType`  
 진행 문서의 형식입니다. 이 매개 변수는 선택적 요소입니다.  
  
 `pRetVal`  
 제한이 반환 된 인터페이스에 대 한 포인터입니다.  
  
## <a name="return-value"></a>Return Value  

 메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.  
  
## <a name="requirements"></a>요구 사항  

 **헤더:** CorSym, CorSym  
  
## <a name="see-also"></a>참고 항목

- [ISymUnmanagedReader 인터페이스](isymunmanagedreader-interface.md)
