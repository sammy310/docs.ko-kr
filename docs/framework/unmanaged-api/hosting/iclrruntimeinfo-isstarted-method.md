---
title: ICLRRuntimeInfo::IsStarted 메서드
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.IsStarted
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::IsStarted
helpviewer_keywords:
- IsStarted method [.NET Framework hosting]
- ICLRRuntimeInfo::IsStarted method [.NET Framework hosting]
ms.assetid: ef6f2662-323b-4534-aa82-6d1afb7b9309
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1297c84acadf0a53b418b06afe806237d374ee25
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59073899"
---
# <a name="iclrruntimeinfoisstarted-method"></a>ICLRRuntimeInfo::IsStarted 메서드
런타임이 시작 되었는지 여부를 나타냅니다 (있는지, 즉 합니다 [iclrruntimehost:: Start 메서드](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) 이 호출 되었고, 했습니다).  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT IsStarted(  
        [out] BOOL     *pbStarted,  
        [out] DWORD    *pdwStartupFlags);  
```  
  
## <a name="parameters"></a>매개 변수  
 `pbStarted`  
 [out] `true` 이 런타임에서이 고, 그렇지 않으면 시작 경우 `false`합니다.  
  
 `pdwStartupFlags`  
 [out] 런타임을 시작 하는 데 사용 된 플래그를 반환 합니다.  
  
## <a name="return-value"></a>반환 값  
 이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.  
  
|HRESULT|설명|  
|-------------|-----------------|  
|S_OK|메서드가 완료되었습니다.|  
|E_NOTIMPL|공용 언어 런타임 (CLR) 버전에서 CLR 버전 보다 이전 인지를 [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]입니다.|  
  
## <a name="remarks"></a>설명  
 이 메서드는 사용 하지 않고 CLR 버전에서 CLR 버전 보다 이전는 [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)]합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** MetaHost.h  
  
 **라이브러리:** MSCorEE.dll에 리소스로 포함  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>참고자료

- [ICLRRuntimeInfo 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)
- [호스팅 인터페이스](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [호스팅](../../../../docs/framework/unmanaged-api/hosting/index.md)
