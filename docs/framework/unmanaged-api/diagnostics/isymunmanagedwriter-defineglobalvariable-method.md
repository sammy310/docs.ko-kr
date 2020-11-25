---
title: ISymUnmanagedWriter::DefineGlobalVariable 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.DefineGlobalVariable
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::DefineGlobalVariable
helpviewer_keywords:
- ISymUnmanagedWriter::DefineGlobalVariable method [.NET Framework debugging]
- DefineGlobalVariable method [.NET Framework debugging]
ms.assetid: 843c904a-8176-4d8f-bd47-b4d4c29f4c5c
topic_type:
- apiref
ms.openlocfilehash: bc389b7247a6b1d6ce16cb3cf350f1672213b2e2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95716423"
---
# <a name="isymunmanagedwriterdefineglobalvariable-method"></a>ISymUnmanagedWriter::DefineGlobalVariable 메서드

단일 전역 변수를 정의합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT DefineGlobalVariable(  
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

 `name`  
 진행 전역 변수 이름을 정의 하는에 대 한 포인터입니다 `WCHAR` .  
  
 `attributes`  
 진행 전역 변수 특성입니다.  
  
 `cSig`  
 진행 `ULONG32` 버퍼의 크기 (문자)를 나타내는입니다 `signature` .  
  
 `signature`  
 진행 전역 변수 서명입니다.  
  
 `addrKind`  
 진행 주소 유형입니다.  
  
 `addr1`  
 진행 매개 변수 사양의 첫 번째 주소입니다.  
  
 `addr2`  
 진행 매개 변수 사양의 두 번째 주소입니다.  
  
 `addr3`  
 진행 매개 변수 사양의 세 번째 주소입니다.  
  
## <a name="return-value"></a>반환 값  

 메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.  
  
## <a name="requirements"></a>요구 사항  

 **헤더:** CorSym, CorSym  
  
## <a name="see-also"></a>참조

- [ISymUnmanagedWriter 인터페이스](isymunmanagedwriter-interface.md)
- [DefineLocalVariable 메서드](isymunmanagedwriter-definelocalvariable-method.md)
- [DefineGlobalVariable2 메서드](isymunmanagedwriter2-defineglobalvariable2-method.md)
