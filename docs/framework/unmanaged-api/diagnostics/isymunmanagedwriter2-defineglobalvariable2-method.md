---
title: ISymUnmanagedWriter2::DefineGlobalVariable2 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter2.DefineGlobalVariable2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter2::DefineGlobalVariable2
helpviewer_keywords:
- ISymUnmanagedWriter2::DefineGlobalVariable2 method [.NET Framework debugging]
- DefineGlobalVariable2 method [.NET Framework debugging]
ms.assetid: 04d569d6-a151-4957-9872-f3f694c3e4a9
topic_type:
- apiref
ms.openlocfilehash: ed3c841c34b71b30f740117899353aa289e478d5
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614710"
---
# <a name="isymunmanagedwriter2defineglobalvariable2-method"></a>ISymUnmanagedWriter2::DefineGlobalVariable2 메서드
단일 전역 변수를 정의합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT DefineGlobalVariable2(  
    [in] const WCHAR  *name,  
    [in] ULONG32      attributes,  
    [in] mdSignature  sigToken,  
    [in] ULONG32      addrKind,  
    [in] ULONG32      addr1,  
    [in] ULONG32      addr2,  
    [in] ULONG32      addr3);  
```  
  
## <a name="parameters"></a>매개 변수  
 `name`  
 진행 전역 변수 이름입니다.  
  
 `attributes`  
 진행 전역 변수 특성입니다.  
  
 `sigToken`  
 진행 시그니처의 메타 데이터 토큰입니다.  
  
 `addrKind`  
 진행 주소 유형입니다.  
  
 `addr1`  
 진행 매개 변수 사양의 첫 번째 주소입니다.  
  
 `addr2`  
 진행 매개 변수 사양의 두 번째 주소입니다.  
  
 `addr3`  
 진행 매개 변수 사양의 세 번째 주소입니다.  
  
## <a name="return-value"></a>Return Value  
 메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** CorSym  
  
## <a name="see-also"></a>참고 항목

- [ISymUnmanagedWriter2 인터페이스](isymunmanagedwriter2-interface.md)
- [DefineGlobalVariable 메서드](isymunmanagedwriter-defineglobalvariable-method.md)
