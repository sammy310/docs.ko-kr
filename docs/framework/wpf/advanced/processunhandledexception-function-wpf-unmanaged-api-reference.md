---
title: ProcessUnhandledException 함수 (F 관리 되지 않는 API 참조)
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ProcessUnhandledException
api_location:
- PresentationHost_v0400.dll
ms.assetid: 495ce5f6-bb4d-4b30-807a-c3c35f1ca95c
ms.openlocfilehash: 3a95e8e68361f060d843247f400043a79dc28889
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57466867"
---
# <a name="processunhandledexception-function-wpf-unmanaged-api-reference"></a>ProcessUnhandledException 함수 (F 관리 되지 않는 API 참조)
이 API는 Windows Presentation Foundation (WPF) 인프라를 지원 하며 코드에서 직접 사용할 수 없습니다.  
  
 예외 처리에 대 한 Windows Presentation Foundation (WPF) 인프라에서 사용 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
void __stdcall ProcessUnhandledException(  
   __in_ecount(1) BSTR errorMsg  
)  
```  
  
## <a name="parameters"></a>매개 변수  
 errorMsg  
 오류 메시지입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [.NET Framework 시스템 요구 사항](../../get-started/system-requirements.md)합니다.  
  
 **DLL:**  
  
 .NET framework 3.0 및 3.5. PresentationHostDLL.dll  
  
 .NET framework 4 이상: PresentationHost_v0400.dll  
  
 **.NET framework 버전:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]  
  
## <a name="see-also"></a>참고자료
- [F 관리되지 않는 API 참조](wpf-unmanaged-api-reference.md)
