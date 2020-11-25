---
title: ISymUnmanagedSymbolSearchInfo::GetSearchPathLength 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedSymbolSearchInfo.GetSearchPathLength
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedSymbolSearchInfo::GetSearchPathLength
helpviewer_keywords:
- GetSearchPathLength method [.NET Framework debugging]
- ISymUnmanagedSymbolSearchInfo::GetSearchPathLength method [.NET Framework debugging]
ms.assetid: 274e73cf-8333-47ba-ac12-70214e2b0112
topic_type:
- apiref
ms.openlocfilehash: 9803094753dee27318af9981bd2e2ad196d434e5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729072"
---
# <a name="isymunmanagedsymbolsearchinfogetsearchpathlength-method"></a>ISymUnmanagedSymbolSearchInfo::GetSearchPathLength 메서드

검색 경로 길이를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetSearchPathLength(  
    [out] ULONG32 *pcchPath);  
```  
  
## <a name="parameters"></a>매개 변수  

 `pcchPath`  
 제한이 `ULONG32` 검색 경로 길이를 포함 하는 데 필요한 버퍼의 크기 (문자 수)를 수신 하는에 대 한 포인터입니다.  
  
## <a name="return-value"></a>반환 값  

 메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.  
  
## <a name="requirements"></a>요구 사항  

 **헤더:** CorSym, CorSym  
  
## <a name="see-also"></a>참조

- [ISymUnmanagedSymbolSearchInfo 인터페이스](isymunmanagedsymbolsearchinfo-interface.md)
