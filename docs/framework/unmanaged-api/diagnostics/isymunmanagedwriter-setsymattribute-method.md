---
title: ISymUnmanagedWriter::SetSymAttribute 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.SetSymAttribute
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::SetSymAttribute
helpviewer_keywords:
- SetSymAttribute method [.NET Framework debugging]
- ISymUnmanagedWriter::SetSymAttribute method [.NET Framework debugging]
ms.assetid: 64d9b80e-b883-4539-89c7-03573185a1eb
topic_type:
- apiref
ms.openlocfilehash: 39b0c065a324f2b3939467901739f995bc9abbad
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614762"
---
# <a name="isymunmanagedwritersetsymattribute-method"></a>ISymUnmanagedWriter::SetSymAttribute 메서드
이름에 따라 사용자 지정 특성을 정의 합니다. 이러한 특성은 메타 데이터 사용자 지정 특성과 달리 기호 저장소에 저장 됩니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT SetSymAttribute(  
    [in] mdToken parent,  
    [in] const WCHAR *name,  
    [in] ULONG32 cData,  
    [in, size_is(cData)] unsigned char data[]);  
```  
  
## <a name="parameters"></a>매개 변수  
 `parent`  
 진행 특성이 정의 되는 메타 데이터 토큰입니다.  
  
 `name`  
 진행 `WCHAR`특성 이름을 포함 하는에 대 한 포인터입니다.  
  
 `cData`  
 진행 `ULONG32`배열의 크기를 나타내는입니다 `data` .  
  
 `data`  
 진행 특성 값입니다.  
  
## <a name="return-value"></a>Return Value  
 메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** CorSym, CorSym  
  
## <a name="see-also"></a>참고 항목

- [ISymUnmanagedWriter 인터페이스](isymunmanagedwriter-interface.md)
