---
title: ICLRRuntimeHost::ExecuteInDefaultAppDomain 메서드
ms.date: 03/30/2017
api_name:
- ICLRRuntimeHost.ExecuteInDefaultAppDomain
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeHost::ExecuteInDefaultAppDomain
helpviewer_keywords:
- ICLRRuntimeHost::ExecuteInDefaultAppDomain method [.NET Framework hosting]
- ExecuteInDefaultAppDomain method [.NET Framework hosting]
ms.assetid: 30b5cf9a-a762-4bd4-be12-d6c1442b78b1
topic_type:
- apiref
ms.openlocfilehash: 1a1bc7609042422de876fe167a9e61655aaf62b4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176411"
---
# <a name="iclrruntimehostexecuteindefaultappdomain-method"></a>ICLRRuntimeHost::ExecuteInDefaultAppDomain 메서드
지정된 관리 되는 어셈블리에서 지정 된 형식의 지정된된 메서드를 호출 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT ExecuteInDefaultAppDomain (  
    [in] LPCWSTR pwzAssemblyPath,  
    [in] LPCWSTR pwzTypeName,
    [in] LPCWSTR pwzMethodName,  
    [in] LPCWSTR pwzArgument,  
    [out] DWORD *pReturnValue  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `pwzAssemblyPath`  
 【인】 호출할 메서드를 정의하는 <xref:System.Reflection.Assembly> 경로입니다. <xref:System.Type>  
  
 `pwzTypeName`  
 【인】 호출할 <xref:System.Type> 메서드를 정의하는 의 이름입니다.  
  
 `pwzMethodName`  
 【인】 호출할 메서드의 이름입니다.  
  
 `pwzArgument`  
 【인】 메서드에 전달할 문자열 매개 변수입니다.  
  
 `pReturnValue`  
 【아웃】 호출된 메서드에서 반환되는 정수 값입니다.  
  
## <a name="return-value"></a>Return Value  
  
|HRESULT|Description|  
|-------------|-----------------|  
|S_OK|`ExecuteInDefaultAppDomain`성공적으로 반환됩니다.|  
|HOST_E_CLRNOTAVAILABLE|공통 언어 런타임(CLR)이 프로세스에 로드되지 않았거나 CLR이 관리 코드를 실행하거나 호출을 성공적으로 처리할 수 없는 상태입니다.|  
|HOST_E_TIMEOUT|통화 시간이 시간 미정으로 확인되었습니다.|  
|HOST_E_NOT_OWNER|호출자는 잠금을 소유하지 않습니다.|  
|HOST_E_ABANDONED|차단된 스레드 또는 파이버가 대기하는 동안 이벤트가 취소되었습니다.|  
|E_FAIL|알 수 없는 치명적인 오류가 발생했습니다. 메서드가 E_FAIL 반환하면 프로세스 내에서 CRL을 더 이상 사용할 수 없습니다. 호스팅 메서드에 대한 후속 호출은 HOST_E_CLRNOTAVAILABLE 반환합니다.|  
  
## <a name="remarks"></a>설명  
 호출된 메서드에는 다음 서명이 있어야 합니다.  
  
```cpp  
static int pwzMethodName (String pwzArgument)  
```  
  
 여기서 `pwzMethodName` 호출된 메서드의 이름을 나타내고 `pwzArgument` 해당 메서드에 대한 매개 변수로 전달된 문자열 값을 나타냅니다. HRESULT 값이 S_OK 설정된 경우 `pReturnValue` 호출된 메서드에서 반환되는 정수 값으로 설정됩니다. `pReturnValue` 그렇지 않으면 설정되지 않습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** MSCorE.h  
  
 **라이브러리:** MSCorEE.dll의 리소스로 포함  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [ICLRRuntimeHost 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
