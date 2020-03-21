---
title: 로드로부터 역사 함수 - WPF 관리되지 않는 API 참조
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- LoadFromHistory
api_location:
- PresentationHost_v0400.dll
ms.assetid: d037c062-a911-4949-b251-ccd3e48b1d17
ms.openlocfilehash: be9b8658614e678b4370044a753554859d230fed
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79141577"
---
# <a name="loadfromhistory-function-wpf-unmanaged-api-reference"></a>로드로부터 역사 함수 (WPF 관리되지 않는 API 참조)
이 API는 WPF(Windows 프레젠테이션 기반) 인프라를 지원하며 코드에서 직접 사용할 수 없습니다.  
  
 Windows 관리를 위한 WPF(Windows 프레젠테이션 재단) 인프라에서 사용합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT LoadFromHistory_export(  
        IStream* pHistoryStream,
        IBindCtx* pBindCtx  
)  
```  
  
## <a name="parameters"></a>매개 변수  
 p히스토리스트림  
 기록 정보 스트림에 대한 포인터입니다.  
  
 pBindCtx  
 바인딩 컨텍스트에 대한 포인터입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [.NET 프레임워크 시스템 요구 사항을 참조하십시오.](../../get-started/system-requirements.md)  
  
 **Dll:**  
  
 .NET 프레임워크 3.0 및 3.5: 프레젠테이션호스트DLL.dll  
  
 .NET 프레임워크 4 이상에서 PresentationHost_v0400.dll  
  
 **.NET 프레임워크 버전:**[!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [WPF 비관리형 API 참조](wpf-unmanaged-api-reference.md)
