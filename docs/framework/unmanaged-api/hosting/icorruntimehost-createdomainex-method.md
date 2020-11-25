---
title: ICorRuntimeHost::CreateDomainEx 메서드
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.CreateDomainEx
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::CreateDomainEx
helpviewer_keywords:
- ICorRuntimeHost::CreateDomainEx method [.NET Framework hosting]
- CreateDomainEx method [.NET Framework hosting]
ms.assetid: 1bdde382-f8ba-4cc8-94b2-d1ac919c585e
topic_type:
- apiref
ms.openlocfilehash: d6d9e06b6ed40bb0e5a65fd64f8bca7abe3afa84
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95715682"
---
# <a name="icorruntimehostcreatedomainex-method"></a>ICorRuntimeHost::CreateDomainEx 메서드

응용 프로그램 도메인을 만듭니다. 호출자는 형식의 인스턴스에 대 한 형식의 인터페이스 포인터를 수신 합니다 <xref:System._AppDomain> <xref:System.AppDomain?displayProperty=nameWithType> . 이 메서드를 사용 하면 호출자가 IAppDomainSetup 인스턴스를 전달 하 여 반환 된 인스턴스의 추가 기능을 구성할 수 있습니다 <xref:System._AppDomain> .  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT CreateDomainEx (  
    [in] LPCWSTR     pwzFriendlyName,  
    [in] IUnknown*   pSetup,  
    [in] IUnknown*   pIdentityArray,  
    [out] IUnknown** pAppDomain  
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `pwzFriendlyName`  
 진행 도메인에 친숙 한 이름을 지정 하는 데 사용 되는 선택적 매개 변수입니다. 이 이름은 디버거와 같은 사용자 인터페이스에 표시 되어 도메인을 식별할 수 있습니다.  
  
 `pSetup`  
 진행 `IAppDomainSetup` [ICorRuntimeHost:: CreateDomainSetup](icorruntimehost-createdomainsetup-method.md) 메서드를 호출 하 여 얻은 형식의 선택적 인터페이스 포인터입니다.  
  
 `pIdentityArray`  
 진행 `IIdentity` 권한 집합을 설정 하기 위해 보안 정책을 통해 매핑된 증명 정보를 나타내는 인스턴스에 대 한 포인터의 선택적 배열입니다. `IIdentity` [Createevidence](icorruntimehost-createevidence-method.md) 메서드를 호출 하 여 개체를 가져올 수 있습니다.  
  
 `pAppDomain`  
 제한이 <xref:System._AppDomain> <xref:System.AppDomain?displayProperty=nameWithType> 도메인을 추가로 제어 하는 데 사용할 수 있는 인스턴스에 대 한 형식의 인터페이스 포인터입니다.  
  
## <a name="return-value"></a>반환 값  
  
|HRESULT|설명|  
|-------------|-----------------|  
|S_OK|작업이 완료되었습니다.|  
|S_FALSE|작업을 완료 하지 못했습니다.|  
|E_FAIL|알 수 없는 치명적인 오류가 발생 했습니다. 메서드가 E_FAIL 반환 하는 경우 해당 프로세스에서 CLR (공용 언어 런타임)을 더 이상 사용할 수 없습니다. 호스팅 Api에 대 한 후속 호출은 HOST_E_CLRNOTAVAILABLE을 반환 합니다.|  
|HOST_E_CLRNOTAVAILABLE|CLR이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.|  
  
## <a name="remarks"></a>설명  

 `CreateDomainEx` 호출자가 응용 프로그램 도메인을 구성 하기 위해 속성 값으로 인스턴스를 전달 하도록 허용 하 여 [Createdomain](icorruntimehost-createdomain-method.md) 의 기능을 확장 합니다 `IAppDomainSetup` .  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Mscoree.dll  
  
 **라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:** 1.0, 1.1  
  
## <a name="see-also"></a>참조

- <xref:System._AppDomain>
- <xref:System.AppDomain>
- <xref:System.IAppDomainSetup?displayProperty=nameWithType>
- [CreateDomain 메서드](icorruntimehost-createdomain-method.md)
- [ICorRuntimeHost 인터페이스](icorruntimehost-interface.md)
