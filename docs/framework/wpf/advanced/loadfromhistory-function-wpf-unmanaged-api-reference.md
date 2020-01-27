---
title: LoadFromHistory 함수-WPF 관리 되지 않는 API 참조
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- LoadFromHistory
api_location:
- PresentationHost_v0400.dll
ms.assetid: d037c062-a911-4949-b251-ccd3e48b1d17
ms.openlocfilehash: 7807e073d1f09ac6a6213aee6d86d53cc75a3c56
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76727932"
---
# <a name="loadfromhistory-function-wpf-unmanaged-api-reference"></a>LoadFromHistory 함수 (WPF 관리 되지 않는 API 참조)
이 API는 Windows Presentation Foundation (WPF) 인프라를 지원 하며 사용자 코드에서 직접 사용 하기 위한 것이 아닙니다.  
  
 Windows 관리를 위한 WPF (Windows Presentation Foundation) 인프라에서 사용 됩니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT LoadFromHistory_export(  
        IStream* pHistoryStream,   
        IBindCtx* pBindCtx  
)  
```  
  
## <a name="parameters"></a>매개 변수  
 pHistoryStream  
 기록 정보 스트림에 대 한 포인터입니다.  
  
 pBindCtx  
 바인드 컨텍스트에 대 한 포인터입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [.NET Framework 시스템 요구 사항](../../get-started/system-requirements.md)을 참조 하세요.  
  
 **DLL:**  
  
 .NET Framework 3.0 및 3.5: PresentationHostDLL에서  
  
 .NET Framework 4 이상: PresentationHost_v0400 .dll  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]  
  
## <a name="see-also"></a>참조

- [F 관리되지 않는 API 참조](wpf-unmanaged-api-reference.md)
