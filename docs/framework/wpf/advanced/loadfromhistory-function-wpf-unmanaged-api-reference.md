---
title: LoadFromHistory 함수 (F 관리 되지 않는 API 참조)
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- LoadFromHistory
api_location:
- PresentationHost_v0400.dll
ms.assetid: d037c062-a911-4949-b251-ccd3e48b1d17
ms.openlocfilehash: 4fc083313c99b1b93db380bfbf6ddeacbc784dcb
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57487410"
---
# <a name="loadfromhistory-function-wpf-unmanaged-api-reference"></a>LoadFromHistory 함수 (F 관리 되지 않는 API 참조)
이 API는 Windows Presentation Foundation (WPF) 인프라를 지원 하며 코드에서 직접 사용할 수 없습니다.  
  
 Windows 관리에 대 한 Windows Presentation Foundation (WPF) 인프라에서 사용 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT LoadFromHistory_export(  
        IStream* pHistoryStream,   
        IBindCtx* pBindCtx  
)  
```  
  
## <a name="parameters"></a>매개 변수  
 pHistoryStream  
 기록 정보 스트림으로 포인터입니다.  
  
 pBindCtx  
 바인드 컨텍스트에 대 한 포인터입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [.NET Framework 시스템 요구 사항](../../get-started/system-requirements.md)합니다.  
  
 **DLL:**  
  
 .NET framework 3.0 및 3.5. PresentationHostDLL.dll  
  
 .NET framework 4 이상: PresentationHost_v0400.dll  
  
 **.NET framework 버전:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]  
  
## <a name="see-also"></a>참고자료
- [F 관리되지 않는 API 참조](wpf-unmanaged-api-reference.md)
