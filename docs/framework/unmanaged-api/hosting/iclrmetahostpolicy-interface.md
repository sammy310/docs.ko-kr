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
ms.openlocfilehash: 515b73b019c683bd3e5aa3b895ee5623e75e4ad0
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95707609"
---
# <a name="iclrmetahostpolicy-interface"></a>ICLRMetaHostPolicy 인터페이스

정책 기준, 관리 되는 어셈블리, 버전 및 구성 파일을 기반으로 CLR (공용 언어 런타임) 인터페이스에 대 한 포인터를 반환 하는 [GetRequestedRuntime](iclrmetahostpolicy-getrequestedruntime-method.md) 메서드를 제공 합니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[GetRequestedRuntime 메서드](iclrmetahostpolicy-getrequestedruntime-method.md)|정책 기준, 관리 되는 어셈블리, 버전 및 구성 파일을 기반으로 기본 CLR 인터페이스를 제공 합니다.|  
  
## <a name="remarks"></a>설명  

 다음 코드와 같이 [Clrcreateinstance](clrcreateinstance-function.md) 함수를 호출 하 여이 인터페이스에 대 한 참조를 가져올 수 있습니다.  
  
```cpp  
ICLRMetaHostPolicy *pMetaHostPolicy = NULL;  
HRESULT hr = CLRCreateInstance(CLSID_CLRMetaHostPolicy,  
                   IID_ICLRMetaHostPolicy, (LPVOID*)&pMetaHostPolicy);  
```  
  
> [!NOTE]
> 이 인터페이스는 실제로 CLR을 로드 하거나 활성화 하지 않지만 설치 또는 로드 된 사용 가능한 버전에 따라 기본 CLR 버전을 반환 합니다.  
  
 .NET Framework 4 호스팅 API는 정책을 통합 하므로 특정 요구 사항이 있는 호스트에서 의도 하지 않은 페널티를 발생 시 키 지 않고 기본 기능을 사용할 수 있습니다. 예를 들어, 메서드는 논리적으로 필요 하지 않지만 대부분의 MSCorEE.dll 내보내기는 특정 CLR에 바인딩합니다. [METAHOST_POLICY_FLAGS](metahost-policy-flags-enumeration.md) 열거형은 대부분의 호스트에 공통 되는 바인딩 정책을 제공 합니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** MetaHost  
  
 **라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>참조

- [.NET Framework 4 및 4.5에 추가된 CLR 호스팅 인터페이스](clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)
- [호스팅 인터페이스](hosting-interfaces.md)
- [호스팅](index.md)
