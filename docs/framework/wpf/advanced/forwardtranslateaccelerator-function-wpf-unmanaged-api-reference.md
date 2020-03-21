---
title: 포워드번역가속기 함수 - WPF 관리되지 않는 API 참조
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ForwardTranslateAccelerator
api_location:
- PresentationHost_v0400.dll
ms.assetid: fff47a86-9d9f-4176-9530-10e1876e393f
ms.openlocfilehash: a0a01be3000dc53df7855cb74015ba1164206838
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186627"
---
# <a name="forwardtranslateaccelerator-function-wpf-unmanaged-api-reference"></a>포워드번역가속기 함수(WPF 비관리 API 참조)
이 API는 WPF(Windows 프레젠테이션 기반) 인프라를 지원하며 코드에서 직접 사용할 수 없습니다.  
  
 Windows 관리를 위한 WPF(Windows 프레젠테이션 재단) 인프라에서 사용합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT ForwardTranslateAccelerator(  
   MSG* pMsg,
   VARIANT_BOOL appUnhandled  
)  
```  
  
## <a name="parameters"></a>매개 변수  
 pMsg  
 메시지에 대한 포인터입니다.  
  
 app처리되지 않음  
 `true`앱에 입력 메시지를 처리할 수 있는 기회가 이미 주어졌지만 처리하지 않은 경우 그렇지 `false`않으면 .  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [.NET 프레임워크 시스템 요구 사항을 참조하십시오.](../../get-started/system-requirements.md)  
  
 **Dll:**  
  
 .NET 프레임워크 3.0 및 3.5: 프레젠테이션호스트DLL.dll  
  
 .NET 프레임워크 4 이상에서 PresentationHost_v0400.dll  
  
 **.NET 프레임워크 버전:**[!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [WPF 비관리형 API 참조](wpf-unmanaged-api-reference.md)
