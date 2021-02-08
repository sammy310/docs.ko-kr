---
description: '자세히 알아보기: EInitializeNewDomainFlags 열거형'
title: EInitializeNewDomainFlags 열거형
ms.date: 03/30/2017
api_name:
- EInitializeNewDomainFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EInitializeNewDomainFlags
helpviewer_keywords:
- EInitializeNewDomainFlags enumeration [.NET Framework hosting]
ms.assetid: 3a120ab2-f5ef-4c9b-8595-d3ed7247c342
ms.openlocfilehash: b856d061e86c0c79b35f842975378307b79a37e7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99785467"
---
# <a name="einitializenewdomainflags-enumeration"></a>EInitializeNewDomainFlags 열거형

호스트에서 응용 프로그램 도메인 초기화에 대 한 정보를 런타임에 제공할 수 있도록 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
typedef enum {  
    eInitializeNewDomainFlags_None              = 0x0000,  
    eInitializeNewDomainFlags_NoSecurityChanges = 0x0002  
} EInitializeNewDomainFlags;  
```  
  
## <a name="members"></a>구성원  
  
|멤버|설명|  
|------------|-----------------|  
|`eInitializeNewDomainFlags_None`|플래그가 없습니다.|  
|`eInitializeNewDomainFlags_NoSecurityChanges`|호스트가 메서드에서 응용 프로그램 도메인의 보안 상태를 변경 하지 않는다는 것을 CLR (공용 언어 런타임)에 알립니다 <xref:System.AppDomainManager.InitializeNewDomain%2A> .|  
  
## <a name="remarks"></a>설명  

 [ICLRDomainManager:: SetAppDomainManagerType](iclrdomainmanager-setappdomainmanagertype-method.md) 메서드는 형식의 매개 변수를 사용 합니다 `EInitializeNewDomainFlags` .  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Mscoree.dll  
  
 **라이브러리:** MSCorEE.dll  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [호스팅 열거형](hosting-enumerations.md)
- [SetAppDomainManagerType 메서드](iclrdomainmanager-setappdomainmanagertype-method.md)
