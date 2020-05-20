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
ms.openlocfilehash: 07d2de5d12fd769cb5cce243d9e721bb6fc185a7
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615477"
---
# <a name="isymunmanagedreaderinitialize-method"></a>ISymUnmanagedReader::Initialize 메서드
이 판독기가 연결 될 메타 데이터 가져오기 인터페이스를 사용 하 여 기호 판독기를 모듈의 파일 이름과 함께 초기화 합니다.  
  
> [!NOTE]
> 이 메서드는 한 번만 호출할 수 있으며 다른 판독기 메서드 보다 먼저 호출 해야 합니다.  
  
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
 진행 이 판독기가 연결 되는 메타 데이터 가져오기 인터페이스입니다.  
  
 `filename`  
 진행 모듈의 파일 이름입니다. 대신 매개 변수를 사용할 수 있습니다 `pIStream` .  
  
 `searchPath`  
 진행 검색할 경로입니다. 이 매개 변수는 선택 사항입니다.  
  
 `pIStream`  
 진행 Filename 매개 변수의 대 안으로 사용 되는 파일 스트림입니다.  
  
## <a name="return-value"></a>Return Value  
 메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.  
  
## <a name="remarks"></a>설명  
 또는 매개 변수 중 하나만 지정 해야 `filename` `pIStream` 합니다. `searchPath` 매개 변수는 선택 사항입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** CorSym, CorSym  
  
## <a name="see-also"></a>참고 항목

- [ISymUnmanagedReader 인터페이스](isymunmanagedreader-interface.md)
