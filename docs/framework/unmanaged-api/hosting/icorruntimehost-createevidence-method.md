---
title: ICorRuntimeHost::CreateEvidence 메서드
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.CreateEvidence
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::CreateEvidence
helpviewer_keywords:
- CreateEvidence method [.NET Framework hosting]
- ICorRuntimeHost::CreateEvidence method [.NET Framework hosting]
ms.assetid: e235ea80-b84c-4442-a4c3-fc96c25a8eb9
topic_type:
- apiref
ms.openlocfilehash: 429ce0510162b3256cdf58f4820b04dd80243e29
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139640"
---
# <a name="icorruntimehostcreateevidence-method"></a>ICorRuntimeHost::CreateEvidence 메서드
호스트가 [Createdomain](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomain-method.md) 또는 [createdomainex](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainex-method.md) 메서드에 전달할 보안 증명 정보를 만들 수 있도록 하는 <xref:System.Security.Principal.IIdentity?displayProperty=nameWithType>형식의 인터페이스 포인터를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT CreateEvidence (  
    [out] IUnknown** pEvidence  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `pEvidence`  
 제한이 보안 증명 정보를 만드는 데 사용 되는 <xref:System.Security.Principal.IIdentity?displayProperty=nameWithType> 인스턴스에 대 한 인터페이스 포인터입니다. 이 포인터는 `IUnknown`형식화 되므로 호출자는 일반적으로이 인터페이스에서 `QueryInterface`를 호출 하 여 <xref:System.Security.Principal.IIdentity?displayProperty=nameWithType>에 대 한 포인터를 가져와야 합니다.  
  
## <a name="return-value"></a>반환 값  
  
|HRESULT|설명|  
|-------------|-----------------|  
|S_OK|작업에 성공 했습니다.|  
|S_FALSE|작업을 완료 하지 못했습니다.|  
|E_FAIL|알 수 없는 치명적인 오류가 발생 했습니다. 메서드가 E_FAIL을 반환 하는 경우 프로세스에서 CLR (공용 언어 런타임)을 더 이상 사용할 수 없습니다. 모든 호스팅 Api에 대 한 후속 호출은 HOST_E_CLRNOTAVAILABLE을 반환 합니다.|  
|HOST_E_CLRNOTAVAILABLE|CLR이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.|  
  
## <a name="remarks"></a>주의  
 이 메서드는 네이티브 코드에서 채울 수 없는 빈 컬렉션을 반환 합니다. <xref:System.Security.Policy.Evidence> 메서드를 대신 사용 해야 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Mscoree.dll  
  
 **라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:** 1.0, 1.1  
  
## <a name="see-also"></a>참조

- <xref:System._AppDomain>
- <xref:System.AppDomain>
- [ICorRuntimeHost 인터페이스](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
