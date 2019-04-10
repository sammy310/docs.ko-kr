---
title: ICLRMetaHostPolicy 인터페이스
ms.date: 03/30/2017
api_name:
- ICLRMetaHostPolicy
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMetaHostPolicy
helpviewer_keywords:
- ICLRMetaHostPolicy interface [.NET Framework hosting]
ms.assetid: 1bdeccb6-0698-4c97-ad69-eae2b69e59f1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 93507ac72b79210dc3a267fea39a6a7b2874916a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59188573"
---
# <a name="iclrmetahostpolicy-interface"></a>ICLRMetaHostPolicy 인터페이스
제공 된 [GetRequestedRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md) 메서드 정책 조건에 따라 공용 언어 런타임 (CLR) 인터페이스에 대 한 포인터를 반환 하는 어셈블리, 버전 및 구성 파일을 관리 합니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[GetRequestedRuntime 메서드](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md)|기본 CLR 인터페이스 정책 조건에 따라, 어셈블리, 버전 및 구성 파일을 관리를 제공 합니다.|  
  
## <a name="remarks"></a>설명  
 호출 하 여이 인터페이스에 대 한 참조를 가져올 수 있습니다는 [CLRCreateInstance](../../../../docs/framework/unmanaged-api/hosting/clrcreateinstance-function.md) 다음 코드 에서처럼 작동 합니다.  
  
```  
ICLRMetaHostPolicy *pMetaHostPolicy = NULL;  
HRESULT hr = CLRCreateInstance(CLSID_CLRMetaHostPolicy,  
                   IID_ICLRMetaHostPolicy, (LPVOID*)&pMetaHostPolicy);  
```  
  
> [!NOTE]
>  이 인터페이스를 로드 하거나 CLR, 하지만 기본 CLR 버전 설치 되거나 로드 된 사용 가능한 버전에 따라 반환 단순히 활성화 실제로 않습니다.  
  
 [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)] 특정 요구 사항이 있는 호스트 의도 하지 않은 저하를 초래 하지 않고 기본 기능을 사용할 수 있도록 정책을 통합 API를 호스트 합니다. 예를 들어 MSCorEE.dll 내보내기의 여러 바인딩될 특정 CLR 메서드 필요 하지 않을 있지만 논리적으로 해당 합니다. 합니다 [METAHOST_POLICY_FLAGS](../../../../docs/framework/unmanaged-api/hosting/metahost-policy-flags-enumeration.md) 열거형은 대부분의 호스트에 공통 되는 바인딩 정책을 제공 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** MetaHost.h  
  
 **라이브러리:** MSCorEE.dll에 리소스로 포함  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>참고자료

- [.NET Framework 4 및 4.5에 추가된 CLR 호스팅 인터페이스](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)
- [호스팅 인터페이스](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [호스팅](../../../../docs/framework/unmanaged-api/hosting/index.md)
