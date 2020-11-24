---
title: ISymUnmanagedWriter::SetMethodSourceRange 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.SetMethodSourceRange
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::SetMethodSourceRange
helpviewer_keywords:
- SetMethodSourceRange method [.NET Framework debugging]
- ISymUnmanagedWriter::SetMethodSourceRange method [.NET Framework debugging]
ms.assetid: c698b86e-ace7-4b21-9549-f52d6a034959
topic_type:
- apiref
ms.openlocfilehash: a918b5c2334683348adc6a7382527faedb52d7b6
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95683539"
---
# <a name="isymunmanagedwritersetmethodsourcerange-method"></a>ISymUnmanagedWriter::SetMethodSourceRange 메서드

소스 파일 내에서 메서드의 실제 시작과 끝을 지정합니다. 이 메서드를 사용 하 여 메서드 내에 있는 시퀀스 위치와 독립적으로 메서드 범위를 지정 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT SetMethodSourceRange(  
    [in] ISymUnmanagedDocumentWriter  *startDoc,  
    [in] ULONG32                      startLine,  
    [in] ULONG32                      startColumn,  
    [in] ISymUnmanagedDocumentWriter  *endDoc,  
    [in] ULONG32                      endLine,  
    [in] ULONG32                      endColumn);  
```  
  
## <a name="parameters"></a>매개 변수  

 `startDoc`  
 진행 시작 위치를 포함 하는 문서에 대 한 포인터입니다.  
  
 `startLine`  
 진행 시작 줄 번호입니다.  
  
 `startColumn`  
 진행 시작 열입니다.  
  
 `endDoc`  
 진행 끝 위치를 포함 하는 문서에 대 한 포인터입니다.  
  
 `endLine`  
 진행 끝 줄 번호입니다.  
  
 `endColumn`  
 진행 끝 열 번호입니다.  
  
## <a name="return-value"></a>반환 값  

 메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.  
  
## <a name="requirements"></a>요구 사항  

 **헤더:** CorSym, CorSym  
  
## <a name="see-also"></a>참조

- [ISymUnmanagedWriter 인터페이스](isymunmanagedwriter-interface.md)
