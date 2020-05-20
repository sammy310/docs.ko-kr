---
title: ISymUnmanagedBinder::GetReaderFromStream 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedBinder.GetReaderFromStream
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedBinder::GetReaderFromStream
helpviewer_keywords:
- ISymUnmanagedBinder::GetReaderFromStream method [.NET Framework debugging]
- GetReaderFromStream method [.NET Framework debugging]
ms.assetid: aa38efd4-de7e-4482-a5d3-adc152093460
topic_type:
- apiref
ms.openlocfilehash: 351bb2a1eb03684a0498fba35270e1bda44a93c0
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/16/2020
ms.locfileid: "83441749"
---
# <a name="isymunmanagedbindergetreaderfromstream-method"></a>ISymUnmanagedBinder::GetReaderFromStream 메서드
메타 데이터 인터페이스 및 기호 저장소를 포함 하는 스트림이 지정 된 경우 지정 된 기호 저장소에서 디버깅 기호를 읽을 올바른 [ISymUnmanagedReader](isymunmanagedreader-interface.md) 구조체를 반환 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetReaderFromStream(  
    [in]  IUnknown  *importer,  
    [in]  IStream   *pstream,  
    [out,retval] ISymUnmanagedReader **pRetVal);  
```  
  
## <a name="parameters"></a>매개 변수  
 `importer`  
 진행 메타 데이터 가져오기 인터페이스에 대 한 포인터입니다.  
  
 `pstream`  
 진행 기호 저장소를 포함 하는 스트림에 대 한 포인터입니다.  
  
 `pRetVal`  
 제한이 반환 된 [ISymUnmanagedReader](isymunmanagedreader-interface.md) interface로 설정 된 포인터입니다.  
  
## <a name="return-value"></a>Return Value  
 메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** CorSym, CorSym  
  
## <a name="see-also"></a>참고 항목

- [ISymUnmanagedBinder 인터페이스](isymunmanagedbinder-interface.md)
