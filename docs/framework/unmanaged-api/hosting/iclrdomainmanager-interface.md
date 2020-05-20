---
title: ICLRDomainManager 인터페이스
ms.date: 03/30/2017
api_name:
- ICLRDomainManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRDomainManager
helpviewer_keywords:
- ICLRDomainManager interface [.NET Framework hosting]
ms.assetid: f08b2390-d872-4521-a815-e9c237c4c45d
ms.openlocfilehash: dda243ccbf18f396c1bcc03358997ea0f06c42a8
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615711"
---
# <a name="iclrdomainmanager-interface"></a>ICLRDomainManager 인터페이스
호스트에서 기본 응용 프로그램 도메인을 초기화 하는 데 사용 되는 응용 프로그램 도메인 관리자를 지정 하 고 초기화 속성을 지정할 수 있도록 합니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[SetAppDomainManagerType 메서드](iclrdomainmanager-setappdomainmanagertype-method.md)|<xref:System.AppDomainManager?displayProperty=nameWithType>기본 응용 프로그램 도메인을 초기화 하는 데 사용 되는 응용 프로그램 도메인 관리자의 클래스에서 파생 된 형식을 지정 합니다.|  
|[SetPropertiesForDefaultAppDomain 메서드](iclrdomainmanager-setpropertiesfordefaultappdomain-method.md)|기본 응용 프로그램 도메인을 초기화 하는 데 사용 되는 속성을 설정 합니다.|  
  
## <a name="remarks"></a>설명  
 이 인터페이스의 인스턴스를 가져오려면 관리자 유형 IID를 사용 하 여 [ICLRControl:: GetCLRManager](iclrcontrol-getclrmanager-method.md) 메서드를 호출 합니다 `IID_ICLRDomainManager` .  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** MetaHost  
  
 **라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [호스팅 인터페이스](hosting-interfaces.md)
- [호스팅](index.md)
