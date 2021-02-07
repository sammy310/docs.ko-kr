---
description: '자세히 알아보기: IMetaDataDispenser 인터페이스'
title: IMetaDataDispenser 인터페이스
ms.date: 03/30/2017
api_name:
- IMetaDataDispenser
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataDispenser
helpviewer_keywords:
- IMetaDataDispenser interface [.NET Framework metadata]
ms.assetid: 989840b3-9822-4ce5-a6c5-b375d3340a7a
topic_type:
- apiref
ms.openlocfilehash: 5ba37fc05a4e1897b100967d32b268f91a0e4402
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99721010"
---
# <a name="imetadatadispenser-interface"></a>IMetaDataDispenser 인터페이스

새 메타 데이터 범위를 만들거나 기존 메타 데이터 범위를 여는 메서드를 제공 합니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[DefineScope 메서드](imetadatadispenser-definescope-method.md)|새 메타 데이터를 만들 수 있는 메모리에 새 영역을 만듭니다.|  
|[OpenScope 메서드](imetadatadispenser-openscope-method.md)|기존 디스크에 있는 기존 파일을 열고 해당 메타 데이터를 메모리에 매핑합니다.|  
|[OpenScopeOnMemory 메서드](imetadatadispenser-openscopeonmemory-method.md)|기존 메타 데이터를 포함 하는 메모리 영역을 엽니다. 즉,이 메서드는 기존 데이터가 메타 데이터로 처리 되는 지정 된 메모리 영역을 엽니다.|  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조 하세요.  
  
 **헤더:** Cor  
  
 **라이브러리:** MsCorEE.dll에서 리소스로 사용 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [IMetaDataDispenserEx 인터페이스](imetadatadispenserex-interface.md)
- [메타데이터 인터페이스](metadata-interfaces.md)
