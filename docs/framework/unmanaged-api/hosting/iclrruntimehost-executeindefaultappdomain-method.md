---
description: '자세히 알아보기: ICLRRuntimeHost:: ExecuteInDefaultAppDomain 메서드'
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
ms.openlocfilehash: 0fae9be69cf67da252dcdb423432ec922c0b00ac
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99785133"
---
# <a name="iclrruntimehostexecuteindefaultappdomain-method"></a>ICLRRuntimeHost::ExecuteInDefaultAppDomain 메서드

지정 된 관리 되는 어셈블리에서 지정 된 형식의 지정 된 메서드를 호출 합니다.  
  
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
 진행 해당 <xref:System.Reflection.Assembly> 메서드가 호출 될를 정의 하는의 경로입니다 <xref:System.Type> .  
  
 `pwzTypeName`  
 진행 <xref:System.Type> 호출할 메서드를 정의 하는의 이름입니다.  
  
 `pwzMethodName`  
 진행 호출할 메서드의 이름입니다.  
  
 `pwzArgument`  
 진행 메서드에 전달할 문자열 매개 변수입니다.  
  
 `pReturnValue`  
 제한이 호출 된 메서드가 반환 하는 정수 값입니다.  
  
## <a name="return-value"></a>Return Value  
  
|HRESULT|설명|  
|-------------|-----------------|  
|S_OK|`ExecuteInDefaultAppDomain` 성공적으로 반환 되었습니다.|  
|HOST_E_CLRNOTAVAILABLE|CLR (공용 언어 런타임)이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.|  
|HOST_E_TIMEOUT|호출 시간이 초과 되었습니다.|  
|HOST_E_NOT_OWNER|호출자가 잠금을 소유 하지 않습니다.|  
|HOST_E_ABANDONED|차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.|  
|E_FAIL|알 수 없는 치명적인 오류가 발생 했습니다. 메서드가 E_FAIL 반환 하는 경우 해당 프로세스 내에서 CRL을 더 이상 사용할 수 없습니다. 호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.|  
  
## <a name="remarks"></a>설명  

 호출 된 메서드의 시그니처는 다음과 같아야 합니다.  
  
```cpp  
static int pwzMethodName (String pwzArgument)  
```  
  
 여기서는 `pwzMethodName` 호출 된 메서드의 이름을 나타내고 `pwzArgument` 는 해당 메서드에 매개 변수로 전달 되는 문자열 값을 나타냅니다. HRESULT 값이 S_OK로 설정 된 경우 `pReturnValue` 는 호출 된 메서드에서 반환 되는 정수 값으로 설정 됩니다. 그렇지 않으면 `pReturnValue` 이 설정 되지 않습니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Mscoree.dll  
  
 **라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [ICLRRuntimeHost 인터페이스](iclrruntimehost-interface.md)
