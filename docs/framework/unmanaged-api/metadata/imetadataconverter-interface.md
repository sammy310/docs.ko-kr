---
title: IMetaDataConverter 인터페이스
ms.date: 03/30/2017
api_name:
- IMetaDataConverter
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataConverter
helpviewer_keywords:
- IMetaDataConverter interface [.NET Framework metadata]
ms.assetid: 9caea662-0167-4267-b14a-2fa42c3be4ea
topic_type:
- apiref
ms.openlocfilehash: b771b368c069a4577d266b47bfb4a5ee1935e48e
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74436264"
---
# <a name="imetadataconverter-interface"></a>IMetaDataConverter 인터페이스
형식 라이브러리를 메타데이터 서명에 매핑하고 서로 변환하는 메서드를 제공합니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[GetMetaDataFromTypeInfo 메서드](../../../../docs/framework/unmanaged-api/metadata/imetadataconverter-getmetadatafromtypeinfo-method.md)|지정 된 `ITypeInfo` 인스턴스가 참조 하는 형식 라이브러리에 대 한 메타 데이터 서명을 나타내는 [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) 인스턴스에 대 한 포인터를 가져옵니다.|  
|[GetMetaDataFromTypeLib 메서드](../../../../docs/framework/unmanaged-api/metadata/imetadataconverter-getmetadatafromtypelib-method.md)|지정 된 `ITypeLib` 인스턴스가 나타내는 형식 라이브러리에 대 한 메타 데이터 서명을 나타내는 `IMetaDataImport` 인스턴스에 대 한 포인터를 가져옵니다.|  
|[GetTypeLibFromMetaData 메서드](../../../../docs/framework/unmanaged-api/metadata/imetadataconverter-gettypelibfrommetadata-method.md)|지정 된 모듈 및 라이브러리 이름이 있는 형식 라이브러리를 나타내는 `ITypeLib` 인스턴스에 대 한 포인터를 가져옵니다.|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조 하세요.  
  
 **헤더:** Cor  
  
 **라이브러리:** Mscoree.dll에서 리소스로 사용 됩니다.  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고자료

- [메타데이터 인터페이스](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
- [IMetaDataImport 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
