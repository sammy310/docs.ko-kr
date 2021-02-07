---
description: '자세히 알아보기: ISymUnmanagedDocumentWriter:: SetCheckSum 메서드'
title: ISymUnmanagedDocumentWriter::SetCheckSum 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocumentWriter.SetCheckSum
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocumentWriter::SetCheckSum
helpviewer_keywords:
- ISymUnmanagedDocumentWriter::SetCheckSum method [.NET Framework debugging]
- SetCheckSum method [.NET Framework debugging]
ms.assetid: c7e99879-421f-43ce-b193-34733cf30085
topic_type:
- apiref
ms.openlocfilehash: ac2ba9654f3610dca333cf0e06c20696cf31bd1f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99710090"
---
# <a name="isymunmanageddocumentwritersetchecksum-method"></a>ISymUnmanagedDocumentWriter::SetCheckSum 메서드

체크섬 정보를 설정합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT SetCheckSum(  
    [in]  GUID     algorithmId,  
    [in]  ULONG32  checkSumSize,  
    [in, size_is(checkSumSize)]  BYTE checkSum[]);  
```  
  
## <a name="parameters"></a>매개 변수  

 `algorithmId`  
 진행 알고리즘 식별자를 나타내는 GUID입니다.  
  
 `checkSumSize`  
 진행 `ULONG32` 버퍼의 크기 (바이트)를 나타내는입니다 `checkSum` .  
  
 `checkSum`  
 진행 체크섬 정보를 저장 하는 버퍼입니다.  
  
## <a name="return-value"></a>Return Value  

 메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.  
  
## <a name="requirements"></a>요구 사항  

 **헤더:** CorSym, CorSym  
  
## <a name="see-also"></a>참고 항목

- [ISymUnmanagedDocumentWriter 인터페이스](isymunmanageddocumentwriter-interface.md)
