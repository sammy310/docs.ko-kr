---
title: ForwardTranslateAccelerator 함수-WPF 관리 되지 않는 API 참조
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ForwardTranslateAccelerator
api_location:
- PresentationHost_v0400.dll
ms.assetid: fff47a86-9d9f-4176-9530-10e1876e393f
ms.openlocfilehash: f6e8208ffe2c186234f30f31e346ca6b1d0be4c0
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76747043"
---
# <a name="forwardtranslateaccelerator-function-wpf-unmanaged-api-reference"></a>ForwardTranslateAccelerator 함수 (WPF 관리 되지 않는 API 참조)
이 API는 Windows Presentation Foundation (WPF) 인프라를 지원 하며 사용자 코드에서 직접 사용 하기 위한 것이 아닙니다.  
  
 Windows 관리를 위한 WPF (Windows Presentation Foundation) 인프라에서 사용 됩니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT ForwardTranslateAccelerator(  
   MSG* pMsg,   
   VARIANT_BOOL appUnhandled  
)  
```  
  
## <a name="parameters"></a>매개 변수  
 pMsg  
 메시지에 대 한 포인터입니다.  
  
 appUnhandled  
 앱이 이미 입력 메시지를 처리할 수 있는 기회를 제공 했지만 처리 하지 않은 경우를 `true` 합니다. 그렇지 않으면 `false`합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [.NET Framework 시스템 요구 사항](../../get-started/system-requirements.md)을 참조 하세요.  
  
 **DLL:**  
  
 .NET Framework 3.0 및 3.5: PresentationHostDLL에서  
  
 .NET Framework 4 이상: PresentationHost_v0400 .dll  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]  
  
## <a name="see-also"></a>참조

- [F 관리되지 않는 API 참조](wpf-unmanaged-api-reference.md)
