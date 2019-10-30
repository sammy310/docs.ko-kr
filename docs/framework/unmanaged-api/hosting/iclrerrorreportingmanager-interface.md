---
title: ICLRErrorReportingManager 인터페이스
ms.date: 03/30/2017
api_name:
- ICLRErrorReportingManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRErrorReportingManager
helpviewer_keywords:
- ICLRErrorReportingManager interface [.NET Framework hosting]
ms.assetid: ea8af0d5-4133-4472-8a1f-50570d7e85fa
topic_type:
- apiref
ms.openlocfilehash: 49a60b6b9b076138d8ff1f8a15041e9a6bacfede
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129250"
---
# <a name="iclrerrorreportingmanager-interface"></a>ICLRErrorReportingManager 인터페이스
호스트에서 오류 보고를 위해 사용자 지정 스택 덤프를 구성할 수 있도록 하는 메서드를 제공 합니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[BeginCustomDump 메서드](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-begincustomdump-method.md)|오류 보고에 대 한 사용자 지정 스택 덤프의 구성을 지정 합니다.|  
|[EndCustomDump 메서드](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-endcustomdump-method.md)|`BeginCustomDump`에 대 한 이전 호출에 의해 설정 된 사용자 지정 스택 덤프 구성을 지웁니다.|  
|[GetBucketParametersForCurrentException 메서드](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-getbucketparametersforcurrentexception-method.md)|호출 스레드의 현재 예외에 대 한 Watson 버킷을 가져옵니다.|  
  
## <a name="remarks"></a>주의  
 `BeginCustomDump` 메서드는 사용자 지정 스택 덤프 구성을 설정 합니다. `EndCustomDump` 메서드는 사용자 지정 스택 덤프 구성을 지우고 연결 된 상태를 해제 합니다. 사용자 지정 덤프가 완료 된 후이 메서드를 호출 해야 합니다.  
  
> [!IMPORTANT]
> `EndCustomDump` 호출 하지 못하면 메모리 누수가 발생 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Mscoree.dll  
  
 **라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참조

- [ECustomDumpItemKind 열거형](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpitemkind-enumeration.md)
- [호스팅 인터페이스](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
