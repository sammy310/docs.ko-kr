---
description: '자세히 알아보기: ISymUnmanagedReader:: GetSymAttribute 메서드'
title: ISymUnmanagedReader::GetSymAttribute 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetSymAttribute
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetSymAttribute
helpviewer_keywords:
- GetSymAttribute method [.NET Framework debugging]
- ISymUnmanagedReader::GetSymAttribute method [.NET Framework debugging]
ms.assetid: c675ce7e-76e7-45ff-8273-3b6489a2767c
topic_type:
- apiref
ms.openlocfilehash: cd1c453e9f2ef68799fc5eccf1288a7665c5cfdf
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99763971"
---
# <a name="isymunmanagedreadergetsymattribute-method"></a>ISymUnmanagedReader::GetSymAttribute 메서드

이름에 따라 사용자 지정 특성을 가져옵니다. 메타 데이터 사용자 지정 특성과 달리 이러한 사용자 지정 특성은 기호 저장소에 저장 됩니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetSymAttribute (  
    [in]  mdToken  parent,  
    [in]  WCHAR    *name,  
    [in]  ULONG32  cBuffer,  
    [out] ULONG32  *pcBuffer,  
    [out, size_is (cBuffer),  
        length_is (*pcBuffer)] BYTE buffer[]);  
```  
  
## <a name="parameters"></a>매개 변수  

 `parent`  
 진행 특성이 요청 된 개체에 대 한 메타 데이터 토큰입니다.  
  
 `name`  
 진행 검색할 특성을 나타내는 변수에 대 한 포인터입니다.  
  
 `cBuffer`  
 [in] `buffer` 배열의 크기입니다.  
  
 `pcBuffer`  
 제한이 특성 데이터의 길이를 받는 변수에 대 한 포인터입니다.  
  
 `buffer`  
 제한이 특성 데이터를 받는 변수에 대 한 포인터입니다.  
  
## <a name="return-value"></a>Return Value  

 메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.  
  
## <a name="requirements"></a>요구 사항  

 **헤더:** CorSym, CorSym  
  
## <a name="see-also"></a>참고 항목

- [ISymUnmanagedReader 인터페이스](isymunmanagedreader-interface.md)
