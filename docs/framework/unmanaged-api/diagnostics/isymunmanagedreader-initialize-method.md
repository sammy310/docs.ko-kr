---
title: ISymUnmanagedReader::Initialize 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.Initialize
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::Initialize
helpviewer_keywords:
- ISymUnmanagedReader::Initialize method [.NET Framework debugging]
- Initialize method, ISymUnmanagedReader interface [.NET Framework debugging]
ms.assetid: 8f0dd2fe-7df7-464e-91f4-5518c586bb5f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1986ed730c6f0a1ba8a2d8e3c688e6872184da9d
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67736759"
---
# <a name="isymunmanagedreaderinitialize-method"></a>ISymUnmanagedReader::Initialize 메서드
이 판독기가 모듈의 파일 이름과 함께, 연결 되는 메타 데이터 가져오기 인터페이스를 사용 하 여 기호 판독기를 초기화 합니다.  
  
> [!NOTE]
>  이 메서드는 한 번만 호출할 수 있습니다 및 다른 판독기 메서드보다 먼저 호출 해야 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT Initialize (  
    [in]  IUnknown     *importer,  
    [in]  const WCHAR  *filename,  
    [in]  const WCHAR  *searchPath,  
    [in]  IStream      *pIStream);  
```  
  
## <a name="parameters"></a>매개 변수  
 `importer`  
 [in] 이 판독기가 연결 될 하는 메타 데이터 가져오기 인터페이스입니다.  
  
 `filename`  
 [in] 모듈의 파일 이름입니다. 사용할 수는 `pIStream` 매개 변수 대신 합니다.  
  
 `searchPath`  
 [in] 검색할 경로입니다. 이 매개 변수는 선택 사항입니다.  
  
 `pIStream`  
 [in] Filename 매개 변수에 대 안으로 사용 되는 파일 스트림.  
  
## <a name="return-value"></a>반환 값  
 메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.  
  
## <a name="remarks"></a>설명  
 중 하나만 지정 해야 합니다 `filename` 또는 `pIStream` 매개 변수를 둘 다. `searchPath` 매개 변수는 선택적 요소입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>참고자료

- [ISymUnmanagedReader 인터페이스](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
