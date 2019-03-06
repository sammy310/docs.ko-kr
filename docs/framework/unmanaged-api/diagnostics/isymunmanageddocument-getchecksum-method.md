---
title: ISymUnmanagedDocument::GetCheckSum 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocument.GetCheckSum
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument::GetCheckSum
helpviewer_keywords:
- ISymUnmanagedDocument::GetCheckSum method [.NET Framework debugging]
- GetCheckSum method [.NET Framework debugging]
ms.assetid: 9bc881b3-e2ce-48a7-ad69-17eaaa304120
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 80cda4c31ca78e0350639df809ec1e9f1dcbbaea
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57498252"
---
# <a name="isymunmanageddocumentgetchecksum-method"></a>ISymUnmanagedDocument::GetCheckSum 메서드
체크섬을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetCheckSum(  
    [in]  ULONG32  cData,  
    [out] ULONG32  *pcData,  
    [out, size_is(cData), length_is(*pcData)] BYTE data[]);  
```  
  
## <a name="parameters"></a>매개 변수  
 `cData`  
 [in] 제공 하는 버퍼의 길이 `data` 매개 변수  
  
 `pcData`  
 [out] 크기와 체크섬, 바이트의 길이입니다.  
  
 `data`  
 [out] 체크섬을 수신 하는 버퍼입니다.  
  
## <a name="return-value"></a>반환 값  
 메서드가 성공 하면 s_ok이 고 그렇지 않으면 오류 코드입니다.  
  
## <a name="see-also"></a>참고자료
- [ISymUnmanagedDocument 인터페이스](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)
