---
title: GetCachePath 함수
ms.date: 03/30/2017
api_name:
- GetCachePath
api_location:
- fusion.dll
- clr.dll
- mscorwks.dll
api_type:
- DLLExport
f1_keywords:
- GetCachePath
helpviewer_keywords:
- GetCachePath function [.NET Framework fusion]
ms.assetid: d977ad29-6619-42e1-b0be-bc25ea950e80
topic_type:
- apiref
ms.openlocfilehash: 13e1468ef5a48f18910c1f8082cdd7c4849da14a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132692"
---
# <a name="getcachepath-function"></a>GetCachePath 함수
지정 된 플래그를 사용 하 여 캐시 된 어셈블리에 대 한 경로를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetCachePath (  
    [in]      ASM_CACHE_FLAGS  dwCacheFlags,  
    [in]      LPWSTR           pwzCachePath,  
    [in, out] PDWORD           pcchPath  
 );  
```  
  
## <a name="parameters"></a>매개 변수  
 `dwCacheFlags`  
 진행 캐시 된 어셈블리의 소스를 나타내는 [ASM_CACHE_FLAGS](asm-cache-flags-enumeration.md) 값입니다.  
  
 `pwzCachePath`  
 제한이 경로에 대 한 반환 포인터입니다.  
  
 `pcchPath`  
 [in, out] 요청 된 최대 `pwzCachePath`길이 이며 반환 시 `pwzCachePath`의 실제 길이입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Fusion. h  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참조

- [ASM_CACHE_FLAGS 열거형](asm-cache-flags-enumeration.md)
- [Fusion 전역 정적 함수](fusion-global-static-functions.md)
