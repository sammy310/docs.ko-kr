---
title: ISymUnmanagedDocument::FindClosestLine 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocument.FindClosestLine
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument::FindClosestLine
helpviewer_keywords:
- FindClosestLine method [.NET Framework debugging]
- ISymUnmanagedDocument::FindClosestLine method [.NET Framework debugging]
ms.assetid: 628f2a04-e529-407d-841e-3b3da219a9cb
topic_type:
- apiref
ms.openlocfilehash: 9e6134d39096c4ab157aa545646d83339f92a0b8
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/16/2020
ms.locfileid: "83441034"
---
# <a name="isymunmanageddocumentfindclosestline-method"></a>ISymUnmanagedDocument::FindClosestLine 메서드
이 문서에서 시퀀스 위치가 될 수도 있고 그렇지 않을 수도 있는 줄을 지정 하 여 시퀀스 위치인 가장 가까운 줄을 반환 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT FindClosestLine(  
    [in]  ULONG32  line,  
    [out, retval] ULONG32*  pRetVal);  
```  
  
## <a name="parameters"></a>매개 변수  
 `line`  
 진행 이 문서의 한 줄입니다.  
  
 `pRetVal`  
 제한이 줄을 받는 변수에 대 한 포인터입니다.  
  
## <a name="return-value"></a>Return Value  
 메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 오류 코드입니다.  
  
## <a name="see-also"></a>참고 항목

- [ISymUnmanagedDocument 인터페이스](isymunmanageddocument-interface.md)
