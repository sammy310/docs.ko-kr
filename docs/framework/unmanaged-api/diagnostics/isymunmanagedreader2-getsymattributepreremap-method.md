---
title: ISymUnmanagedReader2::GetSymAttributePreRemap 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader2.GetSymAttributePreRemap
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader2::GetSymAttributePreRemap
helpviewer_keywords:
- GetSymAttributePreRemap method [.NET Framework debugging]
- ISymUnmanagedReader2::GetSymAttributePreRemap method [.NET Framework debugging]
ms.assetid: 7580d546-a709-40c5-ad02-aa70d774fd0b
topic_type:
- apiref
ms.openlocfilehash: e6248aba1c41b2815f2806942d419da869ed94b4
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614918"
---
# <a name="isymunmanagedreader2getsymattributepreremap-method"></a>ISymUnmanagedReader2::GetSymAttributePreRemap 메서드
이름에 따라 사용자 지정 특성을 가져옵니다. 메타 데이터 사용자 지정 특성과 달리 이러한 특성은 기호 저장소에 저장 됩니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetSymAttributePreRemap(  
    [in]  mdToken  parent,  
    [in]  WCHAR    *name,  
    [in]  ULONG32  cBuffer,  
    [out] ULONG32  *pcBuffer,  
    [out, size_is(cBuffer),  
        length_is(*pcBuffer)] BYTE buffer[]);  
```  
  
## <a name="parameters"></a>매개 변수  
 `parent`  
 진행 부모의 메타 데이터 토큰입니다.  
  
 `name`  
 진행 이름을 포함 하는에 대 한 포인터입니다 `WCHAR` .  
  
 `cBuffer`  
 진행 `ULONG32`배열의 크기를 나타내는입니다 `buffer` .  
  
 `pcBuffer`  
 제한이 `ULONG32`특성 바이트를 포함 하는 데 필요한 버퍼의 크기를 수신 하는에 대 한 포인터입니다.  
  
 `buffer`  
 제한이 특성 바이트를 받는 버퍼에 대 한 포인터입니다.  
  
## <a name="return-value"></a>Return Value  
 메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** CorSym, CorSym  
  
## <a name="see-also"></a>참고 항목

- [ISymUnmanagedReader2 인터페이스](isymunmanagedreader2-interface.md)
