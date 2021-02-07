---
description: '자세히 알아보기: ISymUnmanagedDocument:: GetURL 메서드'
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
ms.openlocfilehash: b39b36054d80f9ad2f9dd076e2055ccbc6526973
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99710194"
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
