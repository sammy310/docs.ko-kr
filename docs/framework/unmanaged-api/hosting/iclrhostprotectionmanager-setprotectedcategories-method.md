---
description: '자세히 알아보기: ICLRHostProtectionManager:: SetProtectedCategories 메서드'
title: ICLRHostProtectionManager::SetProtectedCategories 메서드
ms.date: 03/30/2017
api_name:
- ICLRHostProtectionManager.SetProtectedCategories
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRHostProtectionManager::SetProtectedCategories
helpviewer_keywords:
- SetProtectedCategories method [.NET Framework hosting]
- ICLRHostProtectionManager::SetProtectedCategories method [.NET Framework hosting]
ms.assetid: fa21dc7b-5da7-440b-b59e-9180e5181f9d
topic_type:
- apiref
ms.openlocfilehash: 9138c31ea1a2d9b7ebeaeac8ef5ef9305eabef8d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99637536"
---
# <a name="iclrhostprotectionmanagersetprotectedcategories-method"></a>ICLRHostProtectionManager::SetProtectedCategories 메서드

부분적으로 신뢰할 수 있는 코드에서 실행이 차단 되는 관리 되는 형식 및 멤버의 범주를 지정 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT SetProtectedCategories (  
    [in] EApiCategories  categories  
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `categories`  
 진행 부분적으로 신뢰할 수 있는 코드에서 실행 되는 것을 차단 해야 하는 관리 되는 형식 및 멤버의 범주를 나타내는 [EApiCategories](eapicategories-enumeration.md) 값의 조합입니다.  
  
## <a name="return-value"></a>Return Value  
  
|HRESULT|설명|  
|-------------|-----------------|  
|S_OK|`SetProtectedCategories` 성공적으로 반환 되었습니다.|  
|HOST_E_CLRNOTAVAILABLE|CLR (공용 언어 런타임)이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.|  
|HOST_E_TIMEOUT|호출 시간이 초과 되었습니다.|  
|HOST_E_NOT_OWNER|호출자가 잠금을 소유 하지 않습니다.|  
|HOST_E_ABANDONED|차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.|  
|E_FAIL|알 수 없는 치명적인 오류가 발생 했습니다. 메서드가 E_FAIL 반환 된 후에는 프로세스 내에서 CLR을 더 이상 사용할 수 없습니다. 호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.|  
  
## <a name="remarks"></a>설명  

 각 `EApiCategories` 값은 관리 되는 형식 및 멤버 목록을 나타냅니다. 열거형 및 메서드는 관리 되는 `EApiCategories` `SetProtectedCategories` 클래스와 직접 관련 되어 있으며 <xref:System.Security.Permissions.HostProtectionAttribute> ,이 클래스는에서 설명 하는 범주에 해당 하는 기능을 노출 하는 관리 되는 형식과 멤버를 표시 하는 데 사용 됩니다 `EApiCategories` . 자세한 내용은 <xref:System.Security.Permissions.HostProtectionAttribute> 및 <xref:System.Security.Permissions.HostProtectionResource> 에 직접 해당 하는 열거형을 참조 하세요 `EApiCategories` .  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Mscoree.dll  
  
 **라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Security.Permissions.HostProtectionAttribute>
- <xref:System.Security.Permissions.HostProtectionResource>
- [EApiCategories 열거형](eapicategories-enumeration.md)
- [ICLRControl 인터페이스](iclrcontrol-interface.md)
- [ICLRHostProtectionManager 인터페이스](iclrhostprotectionmanager-interface.md)
