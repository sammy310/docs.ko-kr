---
title: ISymUnmanagedMethod::GetRanges 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedMethod.GetRanges
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod::GetRanges
helpviewer_keywords:
- ISymUnmanagedMethod::GetRanges method [.NET Framework debugging]
- GetRanges method [.NET Framework debugging]
ms.assetid: a85283d8-379c-417a-9736-ddeeef9bcf50
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 94ca1db2bf85f42117f686a8cb483907003927c6
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59205851"
---
# <a name="isymunmanagedmethodgetranges-method"></a>ISymUnmanagedMethod::GetRanges 메서드
문서의 위치를 지정 된 MSIL (Microsoft intermediate language)이이 메서드 내에서 위치를 포함 하는 범위에 해당 하는 시작 및 종료 오프셋된 쌍의 배열을 반환 합니다. 정수 배열이 배열과 [시작, 종료, 시작, 종료] 형식은입니다. 범위 쌍의 개수는 2로 나눈 결과 배열의 길이입니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetRanges(  
    [in]  ISymUnmanagedDocument* document,  
    [in]  ULONG32                line,  
    [in]  ULONG32                column,  
    [in]  ULONG32                cRanges,  
    [out] ULONG32                *pcRanges,  
    [out, size_is(cRanges),  
        length_is(*pcRanges)] ULONG32 ranges[]);  
```  
  
## <a name="parameters"></a>매개 변수  
 `document`  
 [in] 오프셋이 요청 된 문서입니다.  
  
 `line`  
 [in] 범위에 해당 하는 문서 줄.  
  
 `column`  
 [in] 범위에 해당 하는 문서 열입니다.  
  
 `cRanges`  
 [in] `ranges` 배열의 크기입니다.  
  
 `pcRanges`  
 [out] 에 대 한 포인터를 `ULONG32` 범위를 포함 하는 데 필요한 버퍼의 크기를 받는 합니다.  
  
 `ranges`  
 [out] 범위를 받는 버퍼에 대 한 포인터입니다.  
  
## <a name="return-value"></a>반환 값  
 메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>참고자료

- [ISymUnmanagedMethod 인터페이스](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)
