---
title: ISymUnmanagedMethod::GetSequencePoints 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedMethod.GetSequencePoints
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod::GetSequencePoints
helpviewer_keywords:
- ISymUnmanagedMethod::GetSequencePoints method [.NET Framework debugging]
- GetSequencePoints method [.NET Framework debugging]
ms.assetid: f909ac48-3d8f-49fb-a369-e3d9959151cd
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f6b1e253fb7bf1a97f44e1eb05676fc356af9837
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59123710"
---
# <a name="isymunmanagedmethodgetsequencepoints-method"></a>ISymUnmanagedMethod::GetSequencePoints 메서드
이 메서드 내에서 모든 시퀀스 위치를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetSequencePoints(  
    [in]  ULONG32  cPoints,  
    [out] ULONG32  *pcPoints,  
    [in, size_is(cPoints)] ULONG32  offsets[],  
    [in, size_is(cPoints)] ISymUnmanagedDocument* documents[],  
    [in, size_is(cPoints)] ULONG32  lines[],  
    [in, size_is(cPoints)] ULONG32  columns[],  
    [in, size_is(cPoints)] ULONG32  endLines[],  
    [in, size_is(cPoints)] ULONG32  endColumns[]);  
```  
  
## <a name="parameters"></a>매개 변수  
 `cPoints`  
 [in] `ULONG32` 의 크기를 받는 합니다 `offsets`, `documents`, `lines`, `columns`를 `endLines`, 및 `endColumns` 배열입니다.  
  
 `pcPoints`  
 [out] 에 대 한 포인터를 `ULONG32` 시퀀스 위치를 포함 하는 데 필요한 버퍼의 길이 받는입니다.  
  
 `offsets`  
 [in] 저장할 Microsoft 중간 언어 (MSIL) 시퀀스 위치에 대 한 메서드 시작 부분 으로부터의 오프셋 배열입니다.  
  
 `documents`  
 [in] 시퀀스 위치가 있는 문서를 저장 하는 배열입니다.  
  
 `lines`  
 [in] 시퀀스 위치가 있는 문서의 줄을 저장할 배열입니다.  
  
 `columns`  
 [in] 시퀀스 위치가 있는 문서의 열을 저장 하는 배열입니다.  
  
 `endLines`  
 [in] 시퀀스 위치가 끝나는 문서의 줄 배열입니다.  
  
 `endColumns`  
 [in] 시퀀스 위치가 끝나는 문서의 열 배열입니다.  
  
## <a name="return-value"></a>반환 값  
 메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>참고자료

- [ISymUnmanagedMethod 인터페이스](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)
