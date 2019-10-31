---
title: IHostControl 인터페이스
ms.date: 03/30/2017
api_name:
- IHostControl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostControl
helpviewer_keywords:
- IHostControl interface [.NET Framework hosting]
ms.assetid: a4ae0d1f-ade9-4b0a-a122-93ed11a5e6b3
topic_type:
- apiref
ms.openlocfilehash: 444a78705c61d5a53764f55185ef1a907830bd71
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73195876"
---
# <a name="ihostcontrol-interface"></a>IHostControl 인터페이스
어셈블리 로드를 구성 하 고 호스트가 지 원하는 호스팅 인터페이스를 결정 하는 메서드를 제공 합니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[GetHostManager 메서드](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-gethostmanager-method.md)|지정 된 `IID`를 사용 하 여 호스트의 인터페이스 구현에 대 한 인터페이스 포인터를 가져옵니다.|  
|[SetAppDomainManager 메서드](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-setappdomainmanager-method.md)|응용 프로그램 도메인이 생성 되었음을 호스트에 알립니다.|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Mscoree.dll  
  
 **라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참조

- <xref:System.AppDomainManager>
- [ICLRRuntimeHost 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
- [ICLRControl 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [호스팅 인터페이스](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
