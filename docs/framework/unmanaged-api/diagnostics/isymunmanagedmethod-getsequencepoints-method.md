---
description: '자세히 알아보기: ISymUnmanagedMethod:: GetSequencePoints 메서드'
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
ms.openlocfilehash: acdfcb014648593065bd1ae252ef936898a1e8b4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99721296"
---
# <a name="isymunmanagedmethodgetsequencepoints-method"></a>ISymUnmanagedMethod::GetSequencePoints 메서드

이 메서드 내의 모든 시퀀스 위치를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
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
 진행 `ULONG32` `offsets` ,,,, `documents` `lines` `columns` `endLines` 및 `endColumns` 배열의 크기를 받는입니다.  
  
 `pcPoints`  
 제한이 `ULONG32` 시퀀스 위치를 포함 하는 데 필요한 버퍼의 길이를 수신 하는에 대 한 포인터입니다.  
  
 `offsets`  
 진행 시퀀스 위치에 대 한 메서드의 시작 부분에서 MSIL (Microsoft 중간 언어) 오프셋을 저장할 배열입니다.  
  
 `documents`  
 진행 시퀀스 위치가 있는 문서를 저장할 배열입니다.  
  
 `lines`  
 진행 시퀀스 위치가 있는 문서의 줄을 저장할 배열입니다.  
  
 `columns`  
 진행 시퀀스 위치가 있는 문서의 열을 저장할 배열입니다.  
  
 `endLines`  
 진행 시퀀스 위치가 끝나는 문서의 줄 배열입니다.  
  
 `endColumns`  
 진행 시퀀스 위치가 끝나는 문서의 열 배열입니다.  
  
## <a name="return-value"></a>Return Value  

 메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.  
  
## <a name="requirements"></a>요구 사항  

 **헤더:** CorSym, CorSym  
  
## <a name="see-also"></a>참고 항목

- [ISymUnmanagedMethod 인터페이스](isymunmanagedmethod-interface.md)
