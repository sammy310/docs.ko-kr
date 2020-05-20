---
title: ICLRDomainManager::SetPropertiesForDefaultAppDomain 메서드
ms.date: 03/30/2017
api_name:
- ICLRDomainManager.SetPropertiesForDefaultAppDomain
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRDomainManager::SetPropertiesForDefaultAppDomain
helpviewer_keywords:
- ICLRDomainManager::SetPropertiesForDefaultAppDomain method [.NET Framework hosting]
- SetPropertiesForDefaultAppDomain method [.NET Framework hosting]
ms.assetid: 43e61c4b-c435-45ec-9ef6-c68403aa4200
ms.openlocfilehash: 5e1c1b1984c63bedb3c073f45a7b9a3574afdcec
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615685"
---
# <a name="iclrdomainmanagersetpropertiesfordefaultappdomain-method"></a>ICLRDomainManager::SetPropertiesForDefaultAppDomain 메서드
기본 응용 프로그램 도메인을 초기화 하는 데 사용 되는 속성을 설정 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT SetPropertiesForDefaultAppDomain(  
    [in] DWORD nProperties,  
    [in] LPCWSTR *pwszPropertyNames,  
    [in] LPCWSTR *pwszPropertyValues  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `nProperties`  
 진행 및의 항목 수입니다 `pwszPropertyNames` `pwszPropertyValues` .  
  
 `pwszPropertyNames`  
 진행 속성 이름의 배열 이거나, 속성이 없는 경우 null입니다. 현재이 메서드에서 인식 되는 유일한 속성 이름은 "PARTIAL_TRUST_VISIBLE_ASSEMBLIES"입니다.  
  
 `pwszPropertyValues`  
 진행 속성 값의 배열 이거나, 속성이 없는 경우 null입니다.  
  
## <a name="return-value"></a>Return Value  
 이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.  
  
|HRESULT|설명|  
|-------------|-----------------|  
|S_OK|메서드가 완료되었습니다.|  
|HRESULT_FROM_WIN32 (ERROR_UNKNOWN_PROPERTY)|`pwszPropertyNames`이 메서드에서 인식 하지 않는 속성 이름을 포함 하는 경우|  
  
## <a name="remarks"></a>설명  
 "PARTIAL_TRUST_VISIBLE_ASSEMBLIES"에 대 한 속성 값은 플래그를 사용 하는 조건부 (APTCA) 특성을 포함 하는 어셈블리 목록으로 <xref:System.Security.AllowPartiallyTrustedCallersAttribute> <xref:System.Security.PartialTrustVisibilityLevel.NotVisibleByDefault?displayProperty=nameWithType> , 기본 응용 프로그램 도메인에서 부분적으로 신뢰할 수 있는 호출자에 게 표시 됩니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** MetaHost  
  
 **라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [호스팅](index.md)
- [ICLRDomainManager 인터페이스](iclrdomainmanager-interface.md)
