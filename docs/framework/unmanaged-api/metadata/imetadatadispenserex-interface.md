---
title: IMetaDataDispenserEx 인터페이스
ms.date: 03/30/2017
api_name:
- IMetaDataDispenserEx
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataDispenserEx
helpviewer_keywords:
- IMetaDataDispenserEx interface [.NET Framework metadata]
ms.assetid: 78b3629e-77a2-4406-89c3-56b5cc2c4594
topic_type:
- apiref
ms.openlocfilehash: 96f0c0c254ce255581ac2937c805096918ab29e8
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008055"
---
# <a name="imetadatadispenserex-interface"></a>IMetaDataDispenserEx 인터페이스
[IMetaDataDispenser 인터페이스](imetadatadispenser-interface.md) 인터페이스를 확장 하 여 메타 데이터 api가 현재 메타 데이터 범위에서 작동 하는 방식을 제어할 수 있는 기능을 제공 합니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|Description|  
|------------|-----------------|  
|[FindAssembly 메서드](imetadatadispenserex-findassembly-method.md)|이 메서드가 구현되지 않았습니다. 이 메서드를 호출 하면 E_NOTIMPL 반환 됩니다.|  
|[FindAssemblyModule 메서드](imetadatadispenserex-findassemblymodule-method.md)|이 메서드가 구현되지 않았습니다. 이 메서드를 호출 하면 E_NOTIMPL 반환 됩니다.|  
|[GetCORSystemDirectory 메서드](imetadatadispenserex-getcorsystemdirectory-method.md)|현재 CLR (공용 언어 런타임)을 보유 하 고 있는 디렉터리를 가져옵니다. 이 메서드는 in-process 디버거가 사용할 때만 지원 됩니다. 다른 구성 요소에서 호출 되는 경우 E_NOTIMPL 반환 됩니다.|  
|[GetOption 메서드](imetadatadispenserex-getoption-method.md)|현재 메타 데이터 범위에 지정 된 옵션의 값을 가져옵니다. 옵션은 현재 메타 데이터 범위에 대 한 호출을 처리 하는 방법을 제어 합니다.|  
|[OpenScopeOnITypeInfo 메서드](imetadatadispenserex-openscopeonitypeinfo-method.md)|이 메서드가 구현되지 않았습니다. 이 메서드를 호출 하면 E_NOTIMPL 반환 됩니다.|  
|[SetOption 메서드](imetadatadispenserex-setoption-method.md)|지정 된 옵션을 현재 메타 데이터 범위의 지정 된 값으로 설정 합니다. 옵션은 현재 메타 데이터 범위에 대 한 호출을 처리 하는 방법을 제어 합니다.|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조 하세요.  
  
 **헤더:** Cor  
  
 **라이브러리:** Mscoree.dll에서 리소스로 사용 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [메타데이터 인터페이스](metadata-interfaces.md)
- [IMetaDataDispenser 인터페이스](imetadatadispenser-interface.md)
- [IMetaDataEmit 인터페이스](imetadataemit-interface.md)
- [IMetaDataImport 인터페이스](imetadataimport-interface.md)
