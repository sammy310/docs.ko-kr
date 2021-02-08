---
description: '자세히 알아보기: ISymUnmanagedDocument:: GetSourceRange 메서드'
title: ISymUnmanagedDocument::GetSourceRange 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocument.GetSourceRange
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument::GetSourceRange
helpviewer_keywords:
- ISymUnmanagedDocument::GetSourceRange method [.NET Framework debugging]
- GetSourceRange method [.NET Framework debugging]
ms.assetid: 20fefee7-1040-41ba-93dc-bd42f68b90c2
topic_type:
- apiref
ms.openlocfilehash: 98718298d7bf2f44d418a40f17ad19cdee0b6771
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99790167"
---
# <a name="isymunmanageddocumentgetsourcerange-method"></a>ISymUnmanagedDocument::GetSourceRange 메서드

포함 된 소스의 지정 된 범위를 지정 된 버퍼에 반환 합니다. 버퍼는 원본을 저장할 수 있을 만큼 커야 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetSourceRange(  
    [in]  ULONG32  startLine,  
    [in]  ULONG32  startColumn,  
    [in]  ULONG32  endLine,  
    [in]  ULONG32  endColumn,  
    [in]  ULONG32  cSourceBytes,  
    [out] ULONG32  *pcSourceBytes,  
    [out, size_is(cSourceBytes),  
        length_is(*pcSourceBytes)] BYTE source[]);  
```  
  
## <a name="parameters"></a>매개 변수  

 `startLine`  
 진행 현재 문서의 시작 줄입니다.  
  
 `startColumn`  
 진행 현재 문서의 시작 열입니다.  
  
 `endLine`  
 진행 현재 문서의 마지막 줄입니다.  
  
 `endColumn`  
 진행 현재 문서의 마지막 열입니다.  
  
 `cSourceBytes`  
 진행 소스의 크기 (바이트)입니다.  
  
 `pcSourceBytes`  
 제한이 원본 크기를 받는 변수에 대 한 포인터입니다.  
  
 `source`  
 제한이 지정 된 소스 문서 범위의 크기와 길이 (바이트)입니다.  
  
## <a name="return-value"></a>Return Value  

 메서드가 성공 하면 S_OK 합니다.  
  
## <a name="see-also"></a>참고 항목

- [ISymUnmanagedDocument 인터페이스](isymunmanageddocument-interface.md)
