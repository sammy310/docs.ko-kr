---
title: ICorPublishAppDomain::GetName 메서드
ms.date: 03/30/2017
api_name:
- ICorPublishAppDomain.GetName
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishAppDomain::GetName
helpviewer_keywords:
- GetName method, ICorPublishAppDomain interface [.NET Framework debugging]
- ICorPublishAppDomain::GetName method [.NET Framework debugging]
ms.assetid: 6ef8ac9b-9803-4b65-8b13-25f3e0b1bc6b
topic_type:
- apiref
ms.openlocfilehash: 2f91891164f1f80617cab10347eb4a7a08762c10
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140344"
---
# <a name="icorpublishappdomaingetname-method"></a>ICorPublishAppDomain::GetName 메서드
이 [ICorPublishAppDomain](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md)가 나타내는 응용 프로그램 도메인의 이름을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetName (  
    [in]  ULONG32   cchName,   
    [out] ULONG32   *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]   
        WCHAR       *szName  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `cchName`  
 [in] `szName` 배열의 크기입니다.  
  
 `pcchName`  
 제한이 `szName` 배열에 반환 된 null 문자를 포함 하는 와이드 문자 수에 대 한 포인터입니다.  
  
 `szName`  
 제한이 이름을 저장할 배열입니다.  
  
## <a name="remarks"></a>주의  
 `szName` null이 아닌 경우 `GetName` 메서드는 최대 `cchName` 문자 (null 종결자 포함)를 `szName`로 복사 합니다. `pcchName`에서 null이 아닌이 반환 되는 경우에는 이름 (null 종결자 포함)의 실제 문자 수가 `szName` 배열에 저장 됩니다.  
  
 `GetName` 메서드는 복사 된 문자 수에 관계 없이 S_OK HRESULT를 반환 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorPub .idl, CorPub. h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참조

- [ICorPublishAppDomain 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md)
