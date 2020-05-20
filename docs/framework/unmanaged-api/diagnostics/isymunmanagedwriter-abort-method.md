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
ms.openlocfilehash: 09f39d3b6486e2ec3c04c5d1858a85ce56895527
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83610160"
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
  
## <a name="see-also"></a>참고 항목

- [ISymUnmanagedWriter 인터페이스](isymunmanagedwriter-interface.md)
