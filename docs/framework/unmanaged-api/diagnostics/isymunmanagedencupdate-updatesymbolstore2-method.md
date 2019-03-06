---
title: ISymUnmanagedENCUpdate::UpdateSymbolStore2 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedENCUpdate.UpdateSymbolStore2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedENCUpdate::UpdateSymbolStore2
helpviewer_keywords:
- ISymUnmanagedENCUpdate::UpdateSymbolStore2 method [.NET Framework debugging]
- UpdateSymbolStore2 method [.NET Framework debugging]
ms.assetid: 35588317-6184-485c-ab41-4b15fc1765d9
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5a4bcc4e6994f06fabf69e5548ad6922343b7dd5
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57479794"
---
# <a name="isymunmanagedencupdateupdatesymbolstore2-method"></a>ISymUnmanagedENCUpdate::UpdateSymbolStore2 메서드
컴파일러가 줄 정보를 요구 사항을 충족 하는 제공 된 프로그램 데이터베이스 (PDB) 스트림, 수정 되지 않은 함수를 생략할 수 있도록 합니다. 이전 PDB 줄 정보를 및 모든 줄은 함수에 대 한 델타를 사용 하 여 올바른 줄 정보를 확인할 수 있습니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT UpdateSymbolStore2(  
    [in]  IStream      *pIStream,  
    [in]  SYMLINEDELTA* pDeltaLines,  
    [in]  ULONG         cDeltaLines);  
```  
  
## <a name="parameters"></a>매개 변수  
 `pIStream`  
 [in] 에 대 한 포인터를 [IStream](/windows/desktop/api/objidl/nn-objidl-istream) 줄 정보를 포함 하는 합니다.  
  
 `pDeltaLines`  
 [in] 에 대 한 포인터를 [SYMLINEDELTA](../../../../docs/framework/unmanaged-api/diagnostics/symlinedelta-structure.md) 변경 된 줄을 포함 하는 구조입니다.  
  
 `cDeltaLines`  
 [in] `ULONG` 변경 된 줄 수를 나타내는입니다.  
  
## <a name="return-value"></a>반환 값  
 메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>참고자료
- [ISymUnmanagedENCUpdate 인터페이스](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-interface.md)
