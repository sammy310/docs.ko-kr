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
ms.openlocfilehash: 5114f74e80da925c7a153b9e481c54067152eaec
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73108206"
---
# <a name="idefinitionappid-interface"></a>IDefinitionAppId 인터페이스
현재 범위에서 응용 프로그램을 정의 하는 코드의 고유 식별자를 나타냅니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|`IDefinitionAppId::get_Codebase`|이 `IDefinitionAppId` 개체의 코드를 나타내는 형식이 지정 된 문자열을 가져옵니다.|  
|`IDefinitionAppId::put_Codebase`|이 `IDefinitionAppId` 개체의 코드를 지정 된 형식이 지정 된 문자열 값으로 설정 합니다.|  
|`IDefinitionAppId::EnumAppPath`|현재 응용 프로그램 경로의 어셈블리를 포함 하는 [IEnumDefinitionIdentity](ienumdefinitionidentity-interface.md) 개체에 대 한 인터페이스 포인터를 가져옵니다.|  
|`IDefinitionAppId::SetAppPath`|현재 범위에 있는 어셈블리의 응용 프로그램 경로를 지정 된 [Idefinitionidentity](idefinitionidentity-interface.md) 개체에서 참조 하는 값으로 설정 합니다.|  
|`IDefinitionAppId::get_SubscriptionId`|이 `IDefinitionAppId` 개체에 대 한 구독의 토큰 식별자에 대 한 문자열 표현에 대 한 포인터를 가져옵니다.|  
|`IDefinitionAppId::put_SubscriptionId`|이 `IDefinitionAppId` 개체에 대 한 구독의 토큰 식별자를 지정 된 문자열 값으로 설정 합니다.|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** 격리. h  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참조

- [Fusion 인터페이스](fusion-interfaces.md)
