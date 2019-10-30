---
title: ICLRMetaHost 인터페이스
ms.date: 03/30/2017
api_name:
- ICLRMetaHost
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMetaHost
helpviewer_keywords:
- ICLRMetaHost interface [.NET Framework hosting]
ms.assetid: c627fcdd-fc4f-4b1c-8e91-df8536f627d8
topic_type:
- apiref
ms.openlocfilehash: bb760f4923cc3530a28bc68180db743ee468b51d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140904"
---
# <a name="iclrmetahost-interface"></a>ICLRMetaHost 인터페이스
버전 번호를 기반으로 CLR (공용 언어 런타임)의 특정 버전을 반환 하 고, 설치 된 모든 Clr을 나열 하 고, 지정 된 프로세스에 로드 된 모든 런타임을 나열 하 고, 어셈블리를 컴파일하는 데 사용 되는 CLR 버전을 검색 하 고, 프로세스를 종료 하는 메서드를 제공 정리 런타임을 종료 하 고 레거시 API 바인딩을 쿼리 합니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[EnumerateInstalledRuntimes 메서드](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-enumerateinstalledruntimes-method.md)|컴퓨터에 설치 된 각 CLR 버전에 대 한 유효한 [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) 인터페이스 포인터를 포함 하는 열거형을 반환 합니다.|  
|[EnumerateLoadedRuntimes 메서드](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-enumerateloadedruntimes-method.md)|지정 된 프로세스에 로드 된 각 CLR에 대해 유효한 [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) 인터페이스 포인터를 포함 하는 열거형을 반환 합니다. 이 메서드는 [Getversionfromprocess](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md)를 대체 합니다.|  
|[ExitProcess 메서드](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-exitprocess-method.md)|로드 된 모든 런타임을 정상적으로 종료 하 고 프로세스를 종료 하려고 합니다. [Corexitprocess](../../../../docs/framework/unmanaged-api/hosting/corexitprocess-function.md) 함수를 대체 합니다.|  
|[GetRuntime 메서드](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-getruntime-method.md)|특정 CLR 버전에 해당 하는 [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) 인터페이스를 가져옵니다. 이 메서드는 [STARTUP_LOADER_SAFEMODE](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) 플래그와 함께 사용 되는 [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) 함수를 대체 합니다.|  
|[GetVersionFromFile 메서드](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-getversionfromfile-method.md)|해당 파일 경로가 지정 된 경우 메타 데이터에 저장 된 어셈블리의 원래 .NET Framework 컴파일 버전을 가져옵니다. 이 메서드는 [GetFileVersion](../../../../docs/framework/unmanaged-api/hosting/getfileversion-function.md)을 대체 합니다.|  
|[QueryLegacyV2RuntimeBinding 메서드](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-querylegacyv2runtimebinding-method.md)|레거시 활성화 정책이 바인딩된 런타임을 나타내는 인터페이스를 반환 합니다. 예를 들어 [\<시작 > 요소](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md) 구성 파일 항목에 `useLegacyV2RuntimeActivationPolicy` 특성을 사용 하거나 레거시 활성화 api를 직접 사용 하거나 [ICLRRuntimeInfo:: BindAsLegacyV2Runtime](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-bindaslegacyv2runtime-method.md) 메서드를 호출 합니다.|  
|[RequestRuntimeLoadedNotification 메서드](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-requestruntimeloadednotification-method.md)|CLR 버전이 처음 로드 되었지만 아직 시작 되지 않은 경우 지정 된 함수 포인터에 대 한 콜백을 보장 합니다. 이 메서드는 [Lockclrversion](../../../../docs/framework/unmanaged-api/hosting/lockclrversion-function.md) 을 대체 합니다.|  
  
## <a name="remarks"></a>주의  
 이 인터페이스의 인스턴스를 가져오는 유일한 방법은 다음과 같이 [Clrcreateinstance](../../../../docs/framework/unmanaged-api/hosting/clrcreateinstance-function.md) 함수를 호출 하는 것입니다.  
  
```cpp  
ICLRMetaHost *pMetaHost = NULL;  
HRESULT hr = CLRCreateInstance(CLSID_CLRMetaHost,  
                   IID_ICLRMetaHost, (LPVOID*)&pMetaHost);  
```  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** MetaHost  
  
 **라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>참조

- [호스팅 인터페이스](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [호스팅](../../../../docs/framework/unmanaged-api/hosting/index.md)
