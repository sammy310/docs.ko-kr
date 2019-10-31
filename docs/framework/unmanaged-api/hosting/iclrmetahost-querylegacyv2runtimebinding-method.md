---
title: ICLRMetaHost::QueryLegacyV2RuntimeBinding 메서드
ms.date: 03/30/2017
api_name:
- ICLRMetaHost.RequestRuntimeLoadedNotification
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMetaHost::QueryLegacyV2RuntimeBinding
helpviewer_keywords:
- QueryLegacyV2RuntimeBinding method [.NET Framework hosting]
- ICLRMetaHost::QueryLegacyV2RuntimeBinding method [.NET Framework hosting]
ms.assetid: 9929817e-acc9-40b7-960c-598664e04b60
topic_type:
- apiref
ms.openlocfilehash: 90474a61b16d65565889bd69ef75616804d8bc60
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140889"
---
# <a name="iclrmetahostquerylegacyv2runtimebinding-method"></a>ICLRMetaHost::QueryLegacyV2RuntimeBinding 메서드
레거시 정품 인증 Api를 직접 사용 하 여 [\<시작 > 요소](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md) 구성 파일 항목에 `useLegacyV2RuntimeActivationPolicy` 특성을 사용 하는 등의 방법으로 레거시 활성화 정책이 바인딩된 런타임을 나타내는 인터페이스를 반환 합니다. [ICLRRuntimeInfo:: BindAsLegacyV2Runtime](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-bindaslegacyv2runtime-method.md) 메서드를 호출 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT QueryLegacyV2RuntimeBinding (  
    [in] REFIID riid,  
    [out, iid_is(riid), retval] LPVOID *ppUnk);  
```  
  
## <a name="parameters"></a>매개 변수  
 `riid`  
 진행 필수입니다. 현재이 매개 변수에 유효한 값은 `IID_ICLRRuntimeInfo`입니다.  
  
 `ppUnk`  
 [out] 필수입니다. 이 메서드는 반환 될 때 레거시 활성화 정책에 바인딩된 런타임을 나타내는 [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) 인터페이스에 대 한 포인터를 포함 합니다.  
  
## <a name="return-value"></a>반환 값  
 이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.  
  
|HRESULT|설명|  
|-------------|-----------------|  
|S_OK|메서드가 성공적으로 완료되고 레거시 활성화 정책에 바인딩된 런타임을 반환했습니다.|  
|S_FALSE|메서드가 성공적으로 완료되지만 레거시 런타임이 아직 바인딩되지 않았습니다.|  
|E_NOINTERFACE|메서드가 레거시 활성화 정책에 바인딩된 런타임을 찾았지만 `riid`는 해당 런타임에서 지원되지 않습니다.|  
  
## <a name="remarks"></a>주의  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** MetaHost  
  
 **라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>참조

- [ICLRMetaHost 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md)
- [호스팅](../../../../docs/framework/unmanaged-api/hosting/index.md)
