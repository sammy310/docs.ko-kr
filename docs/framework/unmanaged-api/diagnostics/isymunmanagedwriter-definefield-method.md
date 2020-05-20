---
title: ISymUnmanagedWriter::DefineField 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.DefineField
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::DefineField
helpviewer_keywords:
- ISymUnmanagedWriter::DefineField method [.NET Framework debugging]
- DefineField method, ISymUnmanagedWriter interface [.NET Framework debugging]
ms.assetid: c6a1f797-dbf4-40f5-ab99-d9b4bfb26148
topic_type:
- apiref
ms.openlocfilehash: aba551a1973a41a909869316cda07e8d655e9882
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614840"
---
# <a name="isymunmanagedwriterdefinefield-method"></a>ISymUnmanagedWriter::DefineField 메서드
메서드 내에 없는 단일 변수를 정의 합니다. 이 메서드는 클래스, 비트 필드 등의 특정 필드에 사용 됩니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT DefineField(  
    [in] mdTypeDef    parent,  
    [in] const WCHAR  *name,  
    [in] ULONG32      attributes,  
    [in] ULONG32      cSig,  
    [in, size_is(cSig)] unsigned char signature[],  
    [in] ULONG32      addrKind,  
    [in] ULONG32      addr1,  
    [in] ULONG32      addr2,  
    [in] ULONG32      addr3);  
```  
  
## <a name="parameters"></a>매개 변수  
 `parent`  
 진행 메타 데이터 형식 또는 메서드 토큰입니다.  
  
 `name`  
 진행 필드 이름입니다.  
  
 `attributes`  
 진행 필드 특성입니다.  
  
 `cSig`  
 진행 `ULONG32`필드 시그니처를 포함 하는 데 필요한 버퍼의 크기 (문자 수)입니다.  
  
 `signature`  
 진행 필드 시그니처의 배열입니다.  
  
 `addrKind`  
 진행 주소 유형입니다.  
  
 `addr1`  
 진행 필드 사양의 첫 번째 주소입니다.  
  
 `addr2`  
 진행 필드 사양의 두 번째 주소입니다.  
  
 `addr3`  
 진행 필드 사양의 세 번째 주소입니다.  
  
## <a name="return-value"></a>Return Value  
 메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** CorSym, CorSym  
  
## <a name="see-also"></a>참고 항목

- [ISymUnmanagedWriter 인터페이스](isymunmanagedwriter-interface.md)
