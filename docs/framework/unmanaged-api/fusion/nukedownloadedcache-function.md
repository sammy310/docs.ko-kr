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
ms.openlocfilehash: 8f97614412eb2d49b202e86bdabc727159deb5d6
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131692"
---
# <a name="nukedownloadedcache-function"></a>NukeDownloadedCache 함수
CLR (공용 언어 런타임) 다운로드 캐시를 삭제 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT NukeDownloadedCache();  
```  
  
## <a name="return-value"></a>반환 값  
 이 메서드는 Winerror.h에 정의 된 대로 표준 COM 오류 코드를 반환 합니다.  
  
## <a name="remarks"></a>주의  
 CLR 다운로드 캐시는 다시 사용할 수 있도록 URL에서 다운로드 되는 강력한 이름의 어셈블리를 저장 하는 영역입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Fusion. h  
  
 **라이브러리:** Fusion 및 Mscorwks.dll. Mscorwks.dll 대신 Fusion을 사용 하 여 올바른 버전의 .NET Framework를 대상으로 하는지 확인 합니다.  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a>참조

- [CreateHistoryReader 함수](createhistoryreader-function.md)
- [GetHistoryFileDirectory 함수](gethistoryfiledirectory-function.md)
- [Fusion 전역 정적 함수](fusion-global-static-functions.md)
