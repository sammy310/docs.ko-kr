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
ms.openlocfilehash: fe378307ce2bda6e1a267e46433ead70a0e2299e
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616523"
---
# <a name="corruntimehost-coclass"></a>CorRuntimeHost Coclass
공용 언어 런타임에서 실행 되는 응용 프로그램을 관리 하기 위한 인터페이스를 제공 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
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
|[ICorConfiguration 인터페이스](icorconfiguration-interface.md)|CLR (공용 언어 런타임)을 구성 하는 메서드를 제공 합니다.|  
|[ICorRuntimeHost 인터페이스](icorruntimehost-interface.md)|호스트에서 공용 언어 런타임을 명시적으로 시작 및 중지 하 고, 응용 프로그램 도메인을 만들고 구성 하 고, 기본 도메인에 액세스 하 고, 프로세스에서 실행 되는 모든 도메인을 열거 하는 데 사용할 수 있는 메서드를 제공 합니다.|  
|[IDebuggerInfo 인터페이스](idebuggerinfo-interface.md)|디버깅 서비스의 상태에 대 한 정보를 가져오는 메서드를 제공 합니다.|  
|[IGCHost 인터페이스](igchost-interface.md)|가비지 컬렉션 시스템에 대 한 정보를 가져오고 가비지 수집의 일부 측면을 제어 하기 위한 메서드를 제공 합니다.|  
|IValidator|이식 가능한 실행 가능한 이미지의 유효성을 검사 하 고 유효성 검사 오류에 대 한 자세한 보고 메서드를 제공 합니다.|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Mscoree.dll  
  
 **라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [호스팅 Coclass](hosting-coclasses.md)
