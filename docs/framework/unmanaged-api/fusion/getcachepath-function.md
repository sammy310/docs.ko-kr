---
description: '자세한 정보: GetCachePath 함수'
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
ms.openlocfilehash: 4f5045d4110ca9aae33ef54eb85a2146f855e6c7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99761044"
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
 [in, out] 요청 된 최대 길이 `pwzCachePath` 이며 반환 될 때의 실제 길이입니다 `pwzCachePath` .  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Fusion. h  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [ASM_CACHE_FLAGS 열거형](asm-cache-flags-enumeration.md)
- [Fusion 전역 정적 함수](fusion-global-static-functions.md)
