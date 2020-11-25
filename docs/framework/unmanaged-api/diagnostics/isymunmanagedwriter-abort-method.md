---
title: ISymUnmanagedWriter::Abort 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.Abort
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::Abort
helpviewer_keywords:
- ISymUnmanagedWriter::Abort method [.NET Framework debugging]
- Abort method, ISymUnmanagedWriter interface [.NET Framework debugging]
ms.assetid: 416b220f-38d4-48e0-bb49-d2faa7366702
topic_type:
- apiref
ms.openlocfilehash: 2136eb32f147b8928e6ac90b99bbdf66804f244d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95733271"
---
# <a name="isymunmanagedwriterabort-method"></a>ISymUnmanagedWriter::Abort 메서드

기호를 기호 저장소에 커밋하지 않고 기호 작성기를 닫습니다. 이 호출 후에는 기호 작성기에서 추가 업데이트를 사용할 수 없게 됩니다. 기호를 커밋하고 기호 작성기를 닫으려면 [ISymUnmanagedWriter:: close](isymunmanagedwriter-close-method.md) 메서드를 대신 사용 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT Abort();  
```  
  
## <a name="return-value"></a>Return Value  

 메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.  
  
## <a name="requirements"></a>요구 사항  

 **헤더:** CorSym, CorSym  
  
## <a name="see-also"></a>참조

- [ISymUnmanagedWriter 인터페이스](isymunmanagedwriter-interface.md)
