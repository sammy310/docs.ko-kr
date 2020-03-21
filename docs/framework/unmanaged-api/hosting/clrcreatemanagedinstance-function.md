---
title: ClrCreateManagedInstance 함수
ms.date: 03/30/2017
api_name:
- ClrCreateManagedInstance
api_location:
- mscoree.dll
- clr.dll
- mscorwks.dll
- mscoreei.dll
- mscorsvr.dll
api_type:
- DLLExport
f1_keywords:
- ClrCreateManagedInstance
helpviewer_keywords:
- ClrCreateManagedInstance function [.NET Framework hosting]
ms.assetid: 58ba42c0-4857-43bf-a039-73a4dc6544c2
topic_type:
- apiref
ms.openlocfilehash: 7fbe0cf3e93d75749fa3f463f3f97dbd1bfe27a0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176541"
---
# <a name="clrcreatemanagedinstance-function"></a>ClrCreateManagedInstance 함수
지정된 관리 되는 형식의 인스턴스를 만듭니다.  
  
 이 함수는 .NET 프레임워크 4에서 더 이상 사용되지 않습니다. COM 활성화를 사용하여 관리되는 형식의 인스턴스를 만들거나 [호스팅을 사용합니다(.NET Framework 4 및 4.5에 추가된 CLR 호스팅 인터페이스](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)참조).  
  
## <a name="syntax"></a>구문  
  
```cpp  
STDAPI ClrCreateManagedInstance (  
    [in]  LPCWSTR  pTypeName,
    [in]  REFIID   riid,
    [out] void     **ppObject  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `pTypeName`  
 【인】 요청되는 인스턴스 유형의 이름에 대한 포인터입니다.  
  
 `riid`  
 【인】 요청중인 인스턴스 `IID` 유형의 입니다.  
  
 `ppObject`  
 【아웃】 호출자에서 요청한 관리 되는 형식의 인스턴스에 대 한 포인터입니다.  
  
## <a name="remarks"></a>설명  
 공통 언어 런타임은 이미 프로세스에 로드되어야 합니다. 예를 들어 함수가 호출되기 전에 [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) 함수에 `ClrCreateManagedInstance` 대한 호출을 사용하여 로드할 수 있습니다. 런타임이 로드되지 않은 `ClrCreateManagedInstance` 경우 먼저 런타임의 v1.0.3705를 로드하려고 합니다. 실패하면 최신 버전의 런타임을 로드하려고 시도합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** MSCorE.h  
  
 **라이브러리:** Mscoree.dll  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [사용되지 않는 CLR 호스팅 함수](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
- [호스팅](../../../../docs/framework/unmanaged-api/hosting/index.md)
