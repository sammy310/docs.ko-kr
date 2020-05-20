---
title: IAppDomainSetup 인터페이스
ms.date: 03/30/2017
api_name:
- IAppDomainSetup
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IAppDomainSetup
helpviewer_keywords:
- IAppDomainSetup interface [.NET Framework hosting]
ms.assetid: 1844da85-c031-40bf-bea4-1a3d12a36c8c
topic_type:
- apiref
ms.openlocfilehash: 1726f8929404e0dde979972d7830a6951dd71891
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83617063"
---
# <a name="iappdomainsetup-interface"></a>IAppDomainSetup 인터페이스
<xref:System.AppDomain?displayProperty=nameWithType> [ICorRuntimeHost:: CreateDomainEx](icorruntimehost-createdomainex-method.md) 메서드를 호출 하기 전에 호스트가 형식을 구성할 수 있도록 하는 속성을 제공 합니다.  
  
## <a name="properties"></a>속성  
  
|속성|설명|  
|--------------|-----------------|  
|<xref:System.AppDomainSetup.ApplicationBase%2A>|응용 프로그램을 포함 하는 디렉터리의 이름을 가져오거나 설정 합니다.|  
|<xref:System.AppDomainSetup.ApplicationName%2A>|애플리케이션의 이름을 가져오거나 설정합니다.|  
|<xref:System.AppDomainSetup.CachePath%2A>|파일을 섀도 복사한 응용 프로그램 관련 영역의 이름을 가져오거나 설정 합니다.|  
|<xref:System.AppDomainSetup.ConfigurationFile%2A>|응용 프로그램에 대 한 구성 파일의 이름을 가져오거나 설정 합니다.|  
|<xref:System.AppDomainSetup.DynamicBase%2A>|동적으로 생성 된 파일이 저장 되 고 액세스 되는 디렉터리의 이름을 가져오거나 설정 합니다.|  
|<xref:System.AppDomainSetup.LicenseFile%2A>|이 도메인에 연결 된 라이선스 파일의 경로를 가져오거나 설정 합니다.|  
|<xref:System.AppDomainSetup.PrivateBinPath%2A>|전용 어셈블리를 조사할 디렉터리와 결합 된 디렉터리의 목록을 가져오거나 설정 합니다 <xref:System.AppDomainSetup.ApplicationBase%2A> .|  
|<xref:System.AppDomainSetup.PrivateBinPathProbe%2A>|<xref:System.AppDomainSetup.ApplicationBase%2A>응용 프로그램의 검색 경로에서를 포함 하거나 제외 하는 문자열 값을 가져오거나 설정 합니다.|  
|<xref:System.AppDomainSetup.ShadowCopyDirectories%2A>|섀도 복사할 어셈블리가 들어 있는 디렉터리의 이름을 가져오거나 설정 합니다.|  
|<xref:System.AppDomainSetup.ShadowCopyFiles%2A>|섀도 복사를 설정 하거나 해제할지 여부를 나타내는 문자열을 가져오거나 설정 합니다. 유효한 값은 "true" 또는 "false"입니다.|  
  
## <a name="remarks"></a>설명  
 인터페이스는 형식이 구현 하는 `IAppDomainSetup` 관리 되는 인터페이스에 해당 합니다 <xref:System.IAppDomainSetup> <xref:System.AppDomainSetup> . <xref:System.IAppDomainSetup?displayProperty=nameWithType>해당 속성에 대 한 자세한 설명은를 참조 하세요.  
  
 `IAppDomainSetup`생성 하기 전에 인스턴스에 추가할 수 있는 어셈블리 바인딩 정보를 나타냅니다 <xref:System.AppDomain> . 예를 들어 호스트는 속성을 설정 <xref:System.AppDomainSetup.ApplicationBase%2A> 하 여 CLR (공용 언어 런타임)에서 관리 되는 어셈블리를 검색 하는 루트 디렉터리를 설정할 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Mscoree.dll  
  
 **라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- <xref:System.AppDomain>
- <xref:System.AppDomainSetup>
- <xref:System.IAppDomainSetup>
- [호스팅 인터페이스](hosting-interfaces.md)
