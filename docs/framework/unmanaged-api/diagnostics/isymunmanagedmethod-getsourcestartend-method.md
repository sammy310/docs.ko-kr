---
title: ISymUnmanagedMethod::GetSourceStartEnd 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedMethod.GetSourceStartEnd
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod::GetSourceStartEnd
helpviewer_keywords:
- GetSourceStartEnd method [.NET Framework debugging]
- ISymUnmanagedMethod::GetSourceStartEnd method [.NET Framework debugging]
ms.assetid: 2a420900-01f1-4461-8777-3a34a6dc1426
topic_type:
- apiref
ms.openlocfilehash: 25e797fdf563a01ab727f16e7173eec2552eeb27
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614424"
---
# <a name="isymunmanagedmethodgetsourcestartend-method"></a>ISymUnmanagedMethod::GetSourceStartEnd 메서드
이 메서드의 소스에 대 한 시작 및 끝 문서 위치를 가져옵니다. 첫 번째 배열 위치는 시작이 고 두 번째 배열 위치는 끝입니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetSourceStartEnd(  
    [in]  ISymUnmanagedDocument  *docs[2],  
    [in]  ULONG32                lines[2],  
    [in]  ULONG32                columns[2],  
    [out] BOOL                   *pRetVal);  
```  
  
## <a name="parameters"></a>매개 변수  
 `docs`  
 진행 시작 및 종료 소스 문서입니다.  
  
 `lines`  
 진행 해당 소스 문서의 시작 및 종료 줄입니다.  
  
 `columns`  
 진행 해당 소스 문서의 시작 및 끝 열입니다.  
  
 `pRetVal`  
 [out] `true` 위치가 정의 되었으면이 고, 그렇지 않으면입니다. 그렇지 않으면 `false` 입니다.  
  
## <a name="return-value"></a>Return Value  
 메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** CorSym, CorSym  
  
## <a name="see-also"></a>참고 항목

- [ISymUnmanagedMethod 인터페이스](isymunmanagedmethod-interface.md)
