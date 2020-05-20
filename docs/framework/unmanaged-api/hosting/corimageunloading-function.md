---
title: _CorImageUnloading 함수
ms.date: 03/30/2017
api_name:
- _CorImageUnloading
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- _CorImageUnloading
helpviewer_keywords:
- _CorImageUnloading function [.NET Framework hosting]
ms.assetid: b4367214-6dac-4280-aa11-fd487ff30bc4
topic_type:
- apiref
ms.openlocfilehash: 585287f63f57f55e877c94684820833b6d1add60
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616540"
---
# <a name="_corimageunloading-function"></a>_CorImageUnloading 함수
관리 되는 모듈 이미지가 언로드될 때 로더에 알립니다.  
  
 이 함수는 구현되지 않습니다. 이 메서드를 호출 하면 E_NOTIMPL 반환 됩니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
STDAPI (VOID) _CorImageUnloading(
   [in] PVOID* ImageBase  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `ImageBase`  
 진행 언로드할 이미지의 시작 위치에 대 한 포인터입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Cor  
  
 **라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [메타데이터 전역 정적 함수](../metadata/metadata-global-static-functions.md)
