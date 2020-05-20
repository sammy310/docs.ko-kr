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
ms.openlocfilehash: cd5d1f2d59d3e55ba454f23d2e5dd4b1316c0df4
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615178"
---
# <a name="isymunmanagedmethodgetranges-method"></a>ISymUnmanagedMethod::GetRanges 메서드
문서에서 위치가 지정 된 경우이 메서드 내에서 위치가 포함 되는 MSIL (Microsoft 중간 언어)의 범위에 해당 하는 시작 및 종료 오프셋 쌍의 배열을 반환 합니다. 배열은 정수 배열이 며 [start, end, start, end] 형식을 갖습니다. 범위 쌍의 수는 배열 길이를 2로 나눈 값입니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
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
 진행 오프셋이 요청 된 문서입니다.  
  
 `line`  
 진행 범위에 해당 하는 문서 줄입니다.  
  
 `column`  
 진행 범위에 해당 하는 문서 열입니다.  
  
 `cRanges`  
 [in] `ranges` 배열의 크기입니다.  
  
 `pcRanges`  
 제한이 `ULONG32`범위를 포함 하는 데 필요한 버퍼의 크기를 수신 하는에 대 한 포인터입니다.  
  
 `ranges`  
 제한이 범위를 받는 버퍼에 대 한 포인터입니다.  
  
## <a name="return-value"></a>Return Value  
 메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** CorSym, CorSym  
  
## <a name="see-also"></a>참고 항목

- [ISymUnmanagedMethod 인터페이스](isymunmanagedmethod-interface.md)
