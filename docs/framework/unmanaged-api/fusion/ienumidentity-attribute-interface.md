---
title: IEnumIDENTITY_ATTRIBUTE 인터페이스
ms.date: 03/30/2017
api_name:
- IEnumIDENTITY_ATTRIBUTE
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IEnumIDENTITY_ATTRIBUTE
helpviewer_keywords:
- IEnumIDENTITY_ATTRIBUTE interface [.NET Framework fusion]
ms.assetid: c2ec2748-e9ae-4e1b-80db-6fcec5cb81a1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d725228f2a7359d415673fdcb90d0cabae1a40be
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59175528"
---
# <a name="ienumidentityattribute-interface"></a>IEnumIDENTITY_ATTRIBUTE 인터페이스
현재 범위에 있는 코드 개체의 특성에 대 한 열거자를 역할도합니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|`IEnumIDENTITY_ATTRIBUTE::Clone`|새 인터페이스 포인터를 가져옵니다 `IEnumIDENTITY_ATTRIBUTE` 이 동일한 멤버를 포함 하는 `IEnumIDENTITY_ATTRIBUTE`합니다.|  
|`IEnumIDENTITY_ATTRIBUTE::CurrentIntoBuffer`|이 요소에 포함 된 데이터를 쓰는 `IEnumIDENTITY_ATTRIBUTE` 지정된 된 데이터 버퍼를 합니다.|  
|`IEnumIDENTITY_ATTRIBUTE::Next`|특성을 현재 위치부터 지정한 수를 가져옵니다.|  
|`IEnumIDENTITY_ATTRIBUTE::Reset`|이 부분에 명령 포인터를 이동 `IEnumIDENTITY_ATTRIBUTE`합니다.|  
|`IEnumIDENTITY_ATTRIBUTE::Skip`|요소를 현재 위치부터 지정한 수 만큼 앞으로 명령 포인터를 이동 합니다.|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** Isolation.h  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고자료

- [Fusion 인터페이스](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
