---
description: ISymUnmanagedWriter::D efineSequencePoints 메서드에 대해 자세히 알아보세요.
title: ISymUnmanagedWriter::DefineSequencePoints 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.DefineSequencePoints
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::DefineSequencePoints
helpviewer_keywords:
- DefineSequencePoints method [.NET Framework debugging]
- ISymUnmanagedWriter::DefineSequencePoints method [.NET Framework debugging]
ms.assetid: 64202baf-be6b-40ba-8162-8cc6c0c9b8e1
topic_type:
- apiref
ms.openlocfilehash: 0c5ac9854ef341512f58cb1cd63ed7dfcde9962e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99762333"
---
# <a name="isymunmanagedwriterdefinesequencepoints-method"></a>ISymUnmanagedWriter::DefineSequencePoints 메서드

현재 메서드 내에서 시퀀스 위치 그룹을 정의합니다. 각 시작 줄과 시작 열은 메서드 내에서 문의 시작을 정의 합니다. 각 끝 줄과 끝 열은 메서드 내에서 문의 끝을 정의 합니다. 배열은 오프셋의 오름차순으로 정렬 되어야 합니다. 오프셋은 항상 메서드의 시작 부분에서 바이트 단위로 측정 됩니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT DefineSequencePoints(  
    [in] ISymUnmanagedDocumentWriter*  document,  
    [in] ULONG32 spCount,  
    [in, size_is(spCount)] ULONG32     offsets[],  
    [in, size_is(spCount)] ULONG32     lines[],  
    [in, size_is(spCount)] ULONG32     columns[],  
    [in, size_is(spCount)] ULONG32     endLines[],  
    [in, size_is(spCount)] ULONG32     endColumns[]);  
```  
  
## <a name="parameters"></a>매개 변수  

 `document`  
 진행 시퀀스 위치를 정의할 문서 개체입니다.  
  
 `spCount`  
 진행 `ULONG32` 각 `offsets` ,, `lines` `columns` , `endLines` 및 `endColumns` 버퍼의 크기를 나타내는입니다.  
  
 `offsets`  
 진행 메서드의 시작 부분에서 측정 한 시퀀스 위치의 오프셋입니다.  
  
 `lines`  
 진행 시퀀스 위치의 시작 줄 번호입니다.  
  
 `columns`  
 진행 시퀀스 위치의 시작 열 번호입니다.  
  
 `endLines`  
 진행 시퀀스 위치의 끝 줄 번호입니다. 이 매개 변수는 선택적 요소입니다.  
  
 `endColumns`  
 진행 시퀀스 위치의 끝 열 번호입니다. 이 매개 변수는 선택적 요소입니다.  
  
## <a name="return-value"></a>Return Value  

 메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.  
  
## <a name="requirements"></a>요구 사항  

 **헤더:** CorSym, CorSym  
  
## <a name="see-also"></a>참고 항목

- [ISymUnmanagedWriter 인터페이스](isymunmanagedwriter-interface.md)
