---
title: NukeDownloadedCache 함수
ms.date: 03/30/2017
api_name:
- NukeDownloadedCache
api_location:
- fusion.dll
- clr.dll
- mscorwks.dll
api_type:
- DLLExport
f1_keywords:
- NukeDownloadedCache
helpviewer_keywords:
- NukeDownloadedCache function [.NET Framework fusion]
ms.assetid: fac2b1c6-6fa3-4818-805b-b63972024c86
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4e549e13c0d51e4aa708a674a2224168ab66f8ad
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61774532"
---
# <a name="nukedownloadedcache-function"></a>NukeDownloadedCache 함수
공용 언어 런타임 (CLR) 다운로드 캐시를 삭제합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT NukeDownloadedCache();  
```  
  
## <a name="return-value"></a>반환 값  
 이 메서드는 Winerror에 정의 된 대로 표준 COM 오류 코드를 반환 합니다.  
  
## <a name="remarks"></a>설명  
 CLR 다운로드 캐시에 다시 사용할 수 있도록 URL에서 다운로드 하는 강력한 이름의 어셈블리를 저장할 영역입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** Fusion.h  
  
 **라이브러리:** Fusion.dll 및 Mscorwks.dll 합니다. 올바른 버전의.NET Framework 대상 지정 하는 데 Mscorwks.dll 대신 Fusion.dll를 사용 합니다.  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a>참고자료

- [CreateHistoryReader 함수](../../../../docs/framework/unmanaged-api/fusion/createhistoryreader-function.md)
- [GetHistoryFileDirectory 함수](../../../../docs/framework/unmanaged-api/fusion/gethistoryfiledirectory-function.md)
- [Fusion 전역 정적 함수](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
