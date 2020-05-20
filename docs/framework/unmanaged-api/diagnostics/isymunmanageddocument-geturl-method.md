---
title: ISymUnmanagedDocument::GetURL 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocument.GetURL
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument::GetURL
helpviewer_keywords:
- GetURL method [.NET Framework debugging]
- ISymUnmanagedDocument::GetURL method [.NET Framework debugging]
ms.assetid: 60600178-c2b5-4cab-b3a5-f0f61acebaf1
topic_type:
- apiref
ms.openlocfilehash: 3685707f1983ffec413e9cea2df5034ac53f643a
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615594"
---
# <a name="isymunmanageddocumentgeturl-method"></a>ISymUnmanagedDocument::GetURL 메서드
이 문서에 대 한 URL (uniform resource locator)을 반환 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetURL(  
    [in]  ULONG32  cchUrl,  
    [out] ULONG32  *pcchUrl,  
    [out, size_is(cchUrl), length_is(*pcchUrl)] WCHAR szUrl[]);  
```  
  
## <a name="parameters"></a>매개 변수  
 `cchUrl`  
 진행 버퍼의 크기 (문자) `szURL` 입니다.  
  
 `pcchUrl`  
 제한이 Null 종료를 포함 하 여 URL의 크기를 받는 변수에 대 한 포인터입니다.  
  
 `szUrl`  
 제한이 URL을 포함 하는 버퍼입니다.  
  
## <a name="return-value"></a>Return Value  
 메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 오류 코드입니다.  
  
## <a name="see-also"></a>참고 항목

- [ISymUnmanagedDocument 인터페이스](isymunmanageddocument-interface.md)
