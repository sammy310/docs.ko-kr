---
title: CreateIDispatchSTAForwarder 함수-WPF 관리 되지 않는 API 참조
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- CreateIDispatchSTAForwarder
api_location:
- PresentationHost_v0400.dll
ms.assetid: 57a02dfa-f091-4ace-9c06-1f4ab52b3527
ms.openlocfilehash: 67f2542733fb9c6af197c99ede2bd097ce876b5d
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76738033"
---
# <a name="createidispatchstaforwarder-function-wpf-unmanaged-api-reference"></a>CreateIDispatchSTAForwarder 함수 (WPF 관리 되지 않는 API 참조)
이 API는 Windows Presentation Foundation (WPF) 인프라를 지원 하며 사용자 코드에서 직접 사용 하기 위한 것이 아닙니다.  
  
 스레드 및 Windows 관리를 위한 WPF (Windows Presentation Foundation) 인프라에서 사용 됩니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT CreateIDispatchSTAForwarder(  
   __in IDispatch *pDispatchDelegate,   
   __deref_out IDispatch **ppForwarder  
)  
```  
  
## <a name="parameters"></a>매개 변수  
  
## <a name="property-valuereturn-value"></a>속성 값/반환 값  
 pDispatchDelegate  
 `IDispatch` 인터페이스에 대 한 포인터입니다.  
  
 ppForwarder  
 `IDispatch` 인터페이스의 주소에 대 한 포인터입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [.NET Framework 시스템 요구 사항](../../get-started/system-requirements.md)을 참조 하세요.  
  
 **DLL:**  
  
 .NET Framework 3.0 및 3.5: PresentationHostDLL에서  
  
 .NET Framework 4 이상: PresentationHost_v0400 .dll  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]  
  
## <a name="see-also"></a>참조

- [F 관리되지 않는 API 참조](wpf-unmanaged-api-reference.md)
