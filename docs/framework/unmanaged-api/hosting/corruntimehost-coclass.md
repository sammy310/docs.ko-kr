---
title: CorRuntimeHost Coclass
ms.date: 03/30/2017
api_name:
- CorRuntimeHost Coclass
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorRuntimeHost
helpviewer_keywords:
- CoRuntimeHost coclass [.NET Framework hosting]
ms.assetid: 5833740b-7d67-44b4-865c-b5bf45e291e3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2143fc13db1757ac2fa8a9c5a43f104a0c519ca0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61985831"
---
# <a name="corruntimehost-coclass"></a>CorRuntimeHost Coclass
공용 언어 런타임에서 실행 되는 응용 프로그램 관리에 대 한 인터페이스를 제공 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
coclass CorRuntimeHost {  
    [default] interface ICorRuntimeHost;  
    interface IGCHost;  
    interface ICorConfiguration;  
    interface IValidator;  
    interface IDebuggerInfo;  
};  
```  
  
## <a name="interfaces"></a>인터페이스  
  
|인터페이스|설명|  
|---------------|-----------------|  
|[ICorConfiguration 인터페이스](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md)|CLR (공용 언어 런타임) 구성 하기 위한 메서드를 제공 합니다.|  
|[ICorRuntimeHost 인터페이스](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)|시작 하 고 만들고 기본 도메인에 액세스 하 고 프로세스에서 실행 되는 모든 도메인을 열거 하는 데 응용 프로그램 도메인을 구성 하려면 공용 언어 런타임을 명시적으로 중지할 호스트를 사용할 수 있는 메서드를 제공 합니다.|  
|[IDebuggerInfo 인터페이스](../../../../docs/framework/unmanaged-api/hosting/idebuggerinfo-interface.md)|디버깅 서비스의 상태에 대 한 정보를 가져오기 위한 메서드를 제공 합니다.|  
|[IGCHost 인터페이스](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)|가비지 컬렉션 시스템에 대 한 정보를 얻기 위한 고 가비지 컬렉션의 일부 측면을 제어 하기 위한 메서드를 제공 합니다.|  
|"IValidator"|이식 가능한 실행 가능 이미지의 유효성 검사 및 유효성 검사 오류를 자세히 보고에 대 한 메서드를 제공 합니다.|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** MSCorEE.idl  
  
 **라이브러리:** MSCorEE.dll에 리소스로 포함  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고자료

- [호스팅 Coclass](../../../../docs/framework/unmanaged-api/hosting/hosting-coclasses.md)
