---
title: 만들기IDispatchSTA포워더 기능 - WPF 관리되지 않는 API 참조
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- CreateIDispatchSTAForwarder
api_location:
- PresentationHost_v0400.dll
ms.assetid: 57a02dfa-f091-4ace-9c06-1f4ab52b3527
ms.openlocfilehash: e151ffa6eb5f1dc7479c699e0d7f9f3f57833ebd
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174721"
---
# <a name="createidispatchstaforwarder-function-wpf-unmanaged-api-reference"></a>생성IDispatchSTA포이퍼 함수(WPF 관리되지 않는 API 참조)
이 API는 WPF(Windows 프레젠테이션 기반) 인프라를 지원하며 코드에서 직접 사용할 수 없습니다.  
  
 스레드 및 창 관리를 위해 WPF(Windows 프레젠테이션 재단) 인프라에서 사용합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT CreateIDispatchSTAForwarder(  
   __in IDispatch *pDispatchDelegate,
   __deref_out IDispatch **ppForwarder  
)  
```  
  
## <a name="parameters"></a>매개 변수  
  
## <a name="property-valuereturn-value"></a>속성 값/반환 값  
 p디스패치대리자  
 인터페이스에 대한 `IDispatch` 포인터입니다.  
  
 ppForwarder  
 인터페이스의 주소에 대한 `IDispatch` 포인터입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [.NET 프레임워크 시스템 요구 사항을 참조하십시오.](../../get-started/system-requirements.md)  
  
 **Dll:**  
  
 .NET 프레임워크 3.0 및 3.5: 프레젠테이션호스트DLL.dll  
  
 .NET 프레임워크 4 이상에서 PresentationHost_v0400.dll  
  
 **.NET 프레임워크 버전:**[!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [WPF 비관리형 API 참조](wpf-unmanaged-api-reference.md)
