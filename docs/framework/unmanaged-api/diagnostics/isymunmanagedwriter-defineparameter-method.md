---
title: ISymUnmanagedWriter::DefineParameter 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.DefineParameter
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::DefineParameter
helpviewer_keywords:
- DefineParameter method [.NET Framework debugging]
- ISymUnmanagedWriter::DefineParameter method [.NET Framework debugging]
ms.assetid: a8e3dd32-6a44-4371-9a74-f417b11998c8
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b81ee355fe375ca7a597d5f8f2fbf92f71e0bd9b
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57481460"
---
# <a name="isymunmanagedwriterdefineparameter-method"></a>ISymUnmanagedWriter::DefineParameter 메서드
현재 메서드의 단일 매개 변수를 정의합니다. 메서드 시그니처 내의 매개 변수의 위치 (시퀀스)에서 매개 변수 형식을 가져옵니다.  
  
 매개 변수에 지정 된 메서드에 대 한 메타 데이터에 정의 된 경우이 메서드를 사용 하 여를 다시 정의할 필요가 없습니다. 기호 판독기를 기호 저장소를 확인 하기 전에 매개 변수의 일반 메타 데이터를 확인 해야 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT DefineParameter(  
    [in] const WCHAR  *name,  
    [in] ULONG32      attributes,  
    [in] ULONG32      sequence,  
    [in] ULONG32      addrKind,  
    [in] ULONG32      addr1,  
    [in] ULONG32      addr2,  
    [in] ULONG32      addr3);  
```  
  
## <a name="parameters"></a>매개 변수  
 `name`  
 [in] 매개 변수 이름입니다.  
  
 `attributes`  
 [in] 매개 변수 특성입니다.  
  
 `sequence`  
 [in] 매개 변수 서명입니다.  
  
 `addrKind`  
 [in] 주소 유형입니다.  
  
 `addr1`  
 [in] 매개 변수 사양에 대 한 첫 번째 주소입니다.  
  
 `addr2`  
 [in] 매개 변수 사양에 대 한 두 번째 주소입니다.  
  
 `addr3`  
 [in] 매개 변수 사양의 세 번째 주소입니다.  
  
## <a name="return-value"></a>반환 값  
 메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>참고자료
- [ISymUnmanagedWriter 인터페이스](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
