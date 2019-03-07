---
title: ISymUnmanagedWriter::SetSymAttribute 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.SetSymAttribute
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::SetSymAttribute
helpviewer_keywords:
- SetSymAttribute method [.NET Framework debugging]
- ISymUnmanagedWriter::SetSymAttribute method [.NET Framework debugging]
ms.assetid: 64d9b80e-b883-4539-89c7-03573185a1eb
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3ee3e96a25a224fb5b025e22fa43169a64f6c0d2
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57501671"
---
# <a name="isymunmanagedwritersetsymattribute-method"></a>ISymUnmanagedWriter::SetSymAttribute 메서드
해당 이름을 기준으로 사용자 지정 특성을 정의 합니다. 이러한 특성은 사용자 지정 특성 메타 데이터와 달리 기호 저장소에 보관 됩니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT SetSymAttribute(  
    [in] mdToken parent,  
    [in] const WCHAR *name,  
    [in] ULONG32 cData,  
    [in, size_is(cData)] unsigned char data[]);  
```  
  
## <a name="parameters"></a>매개 변수  
 `parent`  
 [in] 특성 정의 되는 메타 데이터 토큰입니다.  
  
 `name`  
 [in] 에 대 한 포인터를 `WCHAR` 특성 이름을 포함 하는 합니다.  
  
 `cData`  
 [in] A `ULONG32` 의 크기를 나타내는 `data` 배열입니다.  
  
 `data`  
 [in] 특성 값입니다.  
  
## <a name="return-value"></a>반환 값  
 메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>참고자료
- [ISymUnmanagedWriter 인터페이스](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
