---
description: '자세히 알아보기: IMetaDataConverter 인터페이스'
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
ms.openlocfilehash: 6ed84083bad924e760c576afe485bd7ccad012cf
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99789257"
---
# <a name="imetadataconverter-interface"></a>IMetaDataConverter 인터페이스

형식 라이브러리를 메타데이터 서명에 매핑하고 서로 변환하는 메서드를 제공합니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[GetMetaDataFromTypeInfo 메서드](imetadataconverter-getmetadatafromtypeinfo-method.md)|지정 된 인스턴스가 참조 하는 형식 라이브러리에 대 한 메타 데이터 서명을 나타내는 [IMetaDataImport](imetadataimport-interface.md) 인스턴스에 대 한 포인터를 가져옵니다 `ITypeInfo` .|  
|[GetMetaDataFromTypeLib 메서드](imetadataconverter-getmetadatafromtypelib-method.md)|`IMetaDataImport`지정 된 인스턴스가 나타내는 형식 라이브러리에 대 한 메타 데이터 서명을 나타내는 인스턴스에 대 한 포인터를 가져옵니다 `ITypeLib` .|  
|[GetTypeLibFromMetaData 메서드](imetadataconverter-gettypelibfrommetadata-method.md)|`ITypeLib`지정 된 모듈 및 라이브러리 이름이 있는 형식 라이브러리를 나타내는 인스턴스에 대 한 포인터를 가져옵니다.|  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조 하세요.  
  
 **헤더:** Cor  
  
 **라이브러리:** MsCorEE.dll에서 리소스로 사용 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [메타데이터 인터페이스](metadata-interfaces.md)
- [IMetaDataImport 인터페이스](imetadataimport-interface.md)
