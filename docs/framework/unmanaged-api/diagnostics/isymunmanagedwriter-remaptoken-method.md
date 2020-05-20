---
title: ISymUnmanagedWriter::RemapToken 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.RemapToken
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::RemapToken
helpviewer_keywords:
- ISymUnmanagedWriter::RemapToken method [.NET Framework debugging]
- RemapToken method [.NET Framework debugging]
ms.assetid: bca92682-ee1e-467f-8fb0-d8d4617f82fe
topic_type:
- apiref
ms.openlocfilehash: 53cc908e0dc8cc5cc980ec365ccac0df4e620cac
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83609770"
---
# <a name="isymunmanagedwriterremaptoken-method"></a>ISymUnmanagedWriter::RemapToken 메서드
메타 데이터를 내보낼 때 메타 데이터 토큰이 다시 매핑되고 있음을 기호 작성기에 알립니다. 기호 작성기가 기호 저장소 내에 이전 토큰을 저장 한 경우 저장 된 토큰을 새 값으로 업데이트 해야 합니다. 그렇지 않으면 읽기 단계에서 다시 매핑할 해당 기호 판독기에 대 한 맵을 저장 해야 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT RemapToken(  
    [in] mdToken  oldToken,  
    [in] mdToken  newToken);  
```  
  
## <a name="parameters"></a>매개 변수  
 `oldToken`  
 진행 다시 매핑된 메타 데이터 토큰입니다.  
  
 `newToken`  
 진행 가 다시 매핑되는 새 메타 데이터 토큰입니다 `oldToken` .  
  
## <a name="return-value"></a>Return Value  
 메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** CorSym, CorSym  
  
## <a name="see-also"></a>참고 항목

- [ISymUnmanagedWriter 인터페이스](isymunmanagedwriter-interface.md)
