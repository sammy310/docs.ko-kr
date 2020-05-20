---
title: ISymUnmanagedReader::GetDocumentVersion 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetDocumentVersion
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetDocumentVersion
helpviewer_keywords:
- GetDocumentVersion method [.NET Framework debugging]
- ISymUnmanagedReader::GetDocumentVersion method [.NET Framework debugging]
ms.assetid: a51f1f64-e084-44c5-830c-2222da5a6bbf
topic_type:
- apiref
ms.openlocfilehash: c2cc541b2a78f16d5ca6b19405794faa825a9d72
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615035"
---
# <a name="isymunmanagedreadergetdocumentversion-method"></a>ISymUnmanagedReader::GetDocumentVersion 메서드
지정 된 문서의 지정 된 버전을 가져옵니다. 문서 버전은 1부터 시작 하 고 [UpdateSymbolStore](isymunmanagedreader-updatesymbolstore-method.md) 메서드를 사용 하 여 문서가 업데이트 될 때마다 증가 합니다. `pbCurrent`매개 변수가 이면 `true` 문서의 최신 버전입니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetDocumentVersion (  
    [in]  ISymUnmanagedDocument *pDoc,  
    [out] int* version,  
    [out] BOOL* pbCurrent);  
```  
  
## <a name="parameters"></a>매개 변수  
 `pDoc`  
 진행 지정 된 문서입니다.  
  
 `version`  
 제한이 지정 된 문서의 버전을 받는 변수에 대 한 포인터입니다.  
  
 `pbCurrent`  
 제한이 `true`최신 버전의 문서 이거나 최신 버전이 아닌 경우를 받는 변수에 대 한 포인터입니다 `false` .  
  
## <a name="return-value"></a>Return Value  
 메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** CorSym, CorSym  
  
## <a name="see-also"></a>참고 항목

- [ISymUnmanagedReader 인터페이스](isymunmanagedreader-interface.md)
