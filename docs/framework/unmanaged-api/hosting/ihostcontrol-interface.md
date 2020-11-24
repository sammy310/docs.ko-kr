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
ms.openlocfilehash: 1bffef31702aa051d9ca865b18a67ac90c00cd00
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95680662"
---
# <a name="ihostcontrol-interface"></a>IHostControl 인터페이스

어셈블리 로드를 구성 하 고 호스트가 지 원하는 호스팅 인터페이스를 결정 하는 메서드를 제공 합니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[GetHostManager 메서드](ihostcontrol-gethostmanager-method.md)|지정 된을 사용 하 여 호스트의 인터페이스 구현에 대 한 인터페이스 포인터를 가져옵니다 `IID` .|  
|[SetAppDomainManager 메서드](ihostcontrol-setappdomainmanager-method.md)|응용 프로그램 도메인이 생성 되었음을 호스트에 알립니다.|  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Mscoree.dll  
  
 **라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참조

- <xref:System.AppDomainManager>
- [ICLRRuntimeHost 인터페이스](iclrruntimehost-interface.md)
- [ICLRControl 인터페이스](iclrcontrol-interface.md)
- [호스팅 인터페이스](hosting-interfaces.md)
