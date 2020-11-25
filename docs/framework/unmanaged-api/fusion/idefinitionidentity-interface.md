---
title: IDefinitionIdentity 인터페이스
ms.date: 03/30/2017
api_name:
- IDefinitionIdentity
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IDefinitionIdentity
helpviewer_keywords:
- IDefinitionIdentity interface [.NET Framework fusion]
ms.assetid: ce5ba888-5fbe-4efd-91cf-f0ff94d8428b
topic_type:
- apiref
ms.openlocfilehash: 4f08fbbf9c8be16dff092327713e731c5aa14661
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732879"
---
# <a name="idefinitionidentity-interface"></a>IDefinitionIdentity 인터페이스

현재 범위에서 응용 프로그램을 정의 하는 코드의 고유 서명을 나타냅니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|`IDefinitionIdentity::Clone`|지정 된 특성이 변경 되는 경우를 제외 하 고이와 동일한 새 개체에 대 한 인터페이스 포인터를 가져옵니다 `IDefinitionIdentity` `IDefinitionIdentity` .|  
|`IDefinitionIdentity::EnumAttributes`|이와 연결 된 특성을 포함 하는 [IEnumIDENTITY_ATTRIBUTE](ienumidentity-attribute-interface.md) 개체에 대 한 인터페이스 포인터를 가져옵니다 `IDefinitionIdentity` .|  
|`IDefinitionIdentity::GetAttribute`|지정 된 네임 스페이스에서 지정 된 이름을 가진 특성의 값을 가져옵니다.|  
|`IDefinitionIdentity::SetAttribute`|지정 된 네임 스페이스에서 지정 된 이름을 가진 특성을 지정 된 값으로 설정 합니다.|  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** 격리. h  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참조

- [Fusion 인터페이스](fusion-interfaces.md)
