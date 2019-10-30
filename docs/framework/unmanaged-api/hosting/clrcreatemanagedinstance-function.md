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
ms.openlocfilehash: 4e672030ae83b57da6f9ab66630513d79f28b8f1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131993"
---
# <a name="clrcreatemanagedinstance-function"></a>ClrCreateManagedInstance 함수
지정 된 관리 되는 형식의 인스턴스를 만듭니다.  
  
 이 함수는 .NET Framework 4에서 더 이상 사용 되지 않습니다. COM 활성화를 사용 하 여 관리 되는 형식의 인스턴스를 만들거나 호스팅을 사용 합니다 ( [.NET Framework 4 및 4.5에 추가 된 CLR 호스팅 인터페이스](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)참조).  
  
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
 진행 요청 되는 인스턴스 형식의 이름에 대 한 포인터입니다.  
  
 `riid`  
 진행 요청 중인 인스턴스 유형의 `IID`입니다.  
  
 `ppObject`  
 제한이 호출자가 요청한 관리 되는 형식의 인스턴스에 대 한 포인터에 대 한 포인터입니다.  
  
## <a name="remarks"></a>주의  
 공용 언어 런타임이 이미 프로세스에 로드 되어 있어야 합니다. 예를 들어 `ClrCreateManagedInstance` 함수를 호출 하기 전에 [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) 함수에 대 한 호출을 사용 하 여 로드할 수 있습니다. 런타임이 로드 되지 않은 경우 `ClrCreateManagedInstance` 먼저 런타임의 v v1.0.3705 로드를 시도 합니다. 이 작업이 실패 하면 최신 버전의 런타임을 로드 하려고 시도 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Mscoree.dll  
  
 **라이브러리:** Mscoree.dll  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참조

- [사용되지 않는 CLR 호스팅 함수](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
- [호스팅](../../../../docs/framework/unmanaged-api/hosting/index.md)
