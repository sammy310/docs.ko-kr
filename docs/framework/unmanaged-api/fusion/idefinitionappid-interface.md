---
title: IDefinitionAppId 인터페이스
ms.date: 03/30/2017
api_name:
- IDefinitionAppId
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IDefinitionAppId
helpviewer_keywords:
- IDefinitionAppId interface [.NET Framework fusion]
ms.assetid: e72f2550-bdec-4a20-a2f4-2e14847266c1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5bd705ef549de3a8018efe731ef8735ef7b6b915
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61697240"
---
# <a name="idefinitionappid-interface"></a>IDefinitionAppId 인터페이스
현재 범위에서 응용 프로그램을 정의 하는 코드에 대 한 고유 식별자를 나타냅니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|`IDefinitionAppId::get_Codebase`|이 코드를 나타내는 형식이 지정 된 문자열을 가져옵니다 `IDefinitionAppId` 개체입니다.|  
|`IDefinitionAppId::put_Codebase`|이 코드를 설정 `IDefinitionAppId` 를 지정 된 형식의 문자열 값입니다.|  
|`IDefinitionAppId::EnumAppPath`|한 인터페이스 포인터를 가져옵니다는 [IEnumDefinitionIdentity](../../../../docs/framework/unmanaged-api/fusion/ienumdefinitionidentity-interface.md) 현재 응용 프로그램 경로의 어셈블리가 포함 된 개체입니다.|  
|`IDefinitionAppId::SetAppPath`|지정 된 참조 하는 값을 현재 범위에서 어셈블리에 대 한 응용 프로그램 경로 설정 [IDefinitionIdentity](../../../../docs/framework/unmanaged-api/fusion/idefinitionidentity-interface.md) 개체입니다.|  
|`IDefinitionAppId::get_SubscriptionId`|이 구독에 대 한 토큰 식별자의 문자열 표현으로 포인터를 가져옵니다 `IDefinitionAppId` 개체입니다.|  
|`IDefinitionAppId::put_SubscriptionId`|이 구독에 대 한 토큰 식별자를 설정 하는 `IDefinitionAppId` 개체 지정된 된 문자열 값입니다.|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** Isolation.h  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고자료

- [Fusion 인터페이스](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
