---
title: ICLRControl 인터페이스
ms.date: 03/30/2017
api_name:
- ICLRControl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRControl
helpviewer_keywords:
- ICLRControl interface [.NET Framework hosting]
ms.assetid: a24fd905-1fa6-45a0-ad65-e9e2ee58861e
topic_type:
- apiref
ms.openlocfilehash: acf449014f5bf5683d5488f8ed2ead963676fe6b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728344"
---
# <a name="iclrcontrol-interface"></a>ICLRControl 인터페이스

호스트가 CLR (공용 언어 런타임)에 대 한 참조를 가져오고의 측면을 구성 하는 데 사용할 수 있는 메서드를 제공 합니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[GetCLRManager 메서드](iclrcontrol-getclrmanager-method.md)|호스트가 CLR을 구성 하는 데 사용할 수 있는 관리자 형식의 인스턴스에 대 한 인터페이스 포인터를 가져옵니다.|  
|[SetAppDomainManagerType 메서드](iclrcontrol-setappdomainmanagertype-method.md)|에서 파생 된 형식을 <xref:System.AppDomainManager> 응용 프로그램 도메인 관리자의 형식으로 설정 합니다.|  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Mscoree.dll  
  
 **라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참조

- [ICLRAssemblyIdentityManager 인터페이스](iclrassemblyidentitymanager-interface.md)
- [ICLRDebugManager 인터페이스](iclrdebugmanager-interface.md)
- [ICLRGCManager 인터페이스](iclrgcmanager-interface.md)
- [ICLRHostBindingPolicyManager 인터페이스](iclrhostbindingpolicymanager-interface.md)
- [ICLRHostProtectionManager 인터페이스](iclrhostprotectionmanager-interface.md)
- [ICLROnEventManager 인터페이스](iclroneventmanager-interface.md)
- [ICLRPolicyManager 인터페이스](iclrpolicymanager-interface.md)
- [IHostControl 인터페이스](ihostcontrol-interface.md)
- [호스팅 인터페이스](hosting-interfaces.md)
