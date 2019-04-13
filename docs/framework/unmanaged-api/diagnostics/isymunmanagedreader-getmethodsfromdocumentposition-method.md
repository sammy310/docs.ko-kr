---
title: ISymUnmanagedReader::GetMethodsFromDocumentPosition 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetMethodsFromDocumentPosition
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetMethodsFromDocumentPosition
helpviewer_keywords:
- GetMethodsFromDocumentPosition method [.NET Framework debugging]
- ISymUnmanagedReader::GetMethodsFromDocumentPosition method [.NET Framework debugging]
ms.assetid: 83605f1e-e4f3-49e6-859b-f13cad68bb54
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 64d7f138094e03ca76ec78a50a6f37aa3d9ca2f0
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59091735"
---
# <a name="isymunmanagedreadergetmethodsfromdocumentposition-method"></a>ISymUnmanagedReader::GetMethodsFromDocumentPosition 메서드
문서에서 지정된 된 위치에 중단점을 포함 하는 각 메서드의 배열을 반환 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetMethodsFromDocumentPosition (  
    [in]  ISymUnmanagedDocument* document,  
    [in]  ULONG32 line,  
    [in]  ULONG32 column,  
    [in]  ULONG32 cMethod,  
    [out] ULONG32* pcMethod,  
    [out, size_is (cMethod),  
        length_is (*pcMethod)] ISymUnmanagedMethod* pRetVal[]);  
```  
  
## <a name="parameters"></a>매개 변수  
 `document`  
 [in] 지정 된 문서입니다.  
  
 `line`  
 [in] 지정 된 문서 줄입니다.  
  
 `column`  
 [in] 지정 된 문서 열입니다.  
  
 `cMethod`  
 [in] `pRetVal` 배열의 크기입니다.  
  
 `pcMethod`  
 [out] 반환 된 요소의 수를 수신 하는 변수에 대 한 포인터를 `pRetVal` 배열입니다.  
  
 `pRetVal`  
 [out] 각각 가리키는 포인터 배열을 [ISymUnmanagedMethod](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md) 중단점을 포함 하는 메서드를 나타내는 개체입니다.  
  
## <a name="return-value"></a>반환 값  
 메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>참고자료

- [ISymUnmanagedReader 인터페이스](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
