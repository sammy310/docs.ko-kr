---
description: '자세히 알아보기: IDefinitionAppId 인터페이스'
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
ms.openlocfilehash: 3c68044e7e747521e190fad404e89d6d0a994611
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99760669"
---
# <a name="idefinitionappid-interface"></a>IDefinitionAppId 인터페이스

현재 범위에서 응용 프로그램을 정의 하는 코드의 고유 식별자를 나타냅니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|`IDefinitionAppId::get_Codebase`|이 개체의 코드를 나타내는 형식이 지정 된 문자열을 가져옵니다 `IDefinitionAppId` .|  
|`IDefinitionAppId::put_Codebase`|이 개체의 코드를 `IDefinitionAppId` 지정 된 형식이 지정 된 문자열 값으로 설정 합니다.|  
|`IDefinitionAppId::EnumAppPath`|현재 응용 프로그램 경로의 어셈블리를 포함 하는 [IEnumDefinitionIdentity](ienumdefinitionidentity-interface.md) 개체에 대 한 인터페이스 포인터를 가져옵니다.|  
|`IDefinitionAppId::SetAppPath`|현재 범위에 있는 어셈블리의 응용 프로그램 경로를 지정 된 [Idefinitionidentity](idefinitionidentity-interface.md) 개체에서 참조 하는 값으로 설정 합니다.|  
|`IDefinitionAppId::get_SubscriptionId`|이 개체에 대 한 구독의 토큰 식별자에 대 한 문자열 표현에 대 한 포인터를 가져옵니다 `IDefinitionAppId` .|  
|`IDefinitionAppId::put_SubscriptionId`|이 개체에 대 한 구독의 토큰 식별자를 `IDefinitionAppId` 지정 된 문자열 값으로 설정 합니다.|  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** 격리. h  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [Fusion 인터페이스](fusion-interfaces.md)
