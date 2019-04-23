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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4ff23330f307c10eac134048de39a6e19a67c75b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59192669"
---
# <a name="idefinitionidentity-interface"></a>IDefinitionIdentity 인터페이스
현재 범위에서 응용 프로그램을 정의 하는 코드의 고유한 시그니처를 나타냅니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|`IDefinitionIdentity::Clone`|새 인터페이스 포인터를 가져옵니다 `IDefinitionIdentity` 이 동일한 개체 `IDefinitionIdentity`, 지정 된 특성 변경을 제외 하 고 있습니다.|  
|`IDefinitionIdentity::EnumAttributes`|한 인터페이스 포인터를 가져옵니다는 [IEnumIDENTITY_ATTRIBUTE](../../../../docs/framework/unmanaged-api/fusion/ienumidentity-attribute-interface.md) 개체와 연결 된 특성이 포함 된 `IDefinitionIdentity`합니다.|  
|`IDefinitionIdentity::GetAttribute`|지정된 된 네임 스페이스에서 지정한 이름 가진 특성의 값을 가져옵니다.|  
|`IDefinitionIdentity::SetAttribute`|지정된 된 값으로 지정된 된 네임 스페이스에서 지정 된 이름이 있는 특성을 설정 합니다.|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** Isolation.h  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고자료

- [Fusion 인터페이스](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
