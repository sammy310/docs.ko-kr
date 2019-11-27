---
title: IMetaDataFilter 인터페이스
ms.date: 03/30/2017
api_name:
- IMetaDataFilter
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataFilter
helpviewer_keywords:
- IMetaDataFilter interface [.NET Framework metadata]
ms.assetid: ec0856ef-8c56-40ba-bf60-86e0ce8b337f
topic_type:
- apiref
ms.openlocfilehash: e8b15f478eb3b94b7cdcab3b69d54e7cc99be13b
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74440170"
---
# <a name="imetadatafilter-interface"></a>IMetaDataFilter 인터페이스
이미 수행된 반복 작업을 방지하려고 메타데이터 토큰을 표시 및 필터링하는 메서드를 제공합니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[IsTokenMarked 메서드](../../../../docs/framework/unmanaged-api/metadata/imetadatafilter-istokenmarked-method.md)|지정 된 메타 데이터 토큰이 처리 되었는지 여부를 나타내는 값을 가져옵니다.|  
|[MarkToken 메서드](../../../../docs/framework/unmanaged-api/metadata/imetadatafilter-marktoken-method.md)|지정 된 메타 데이터 토큰이 처리 되었음을 나타내는 값을 설정 합니다.|  
|[UnmarkAll 메서드](../../../../docs/framework/unmanaged-api/metadata/imetadatafilter-unmarkall-method.md)|현재 메타 데이터 범위에 있는 모든 토큰에서 처리 표시를 제거 합니다.|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Cor  
  
 **라이브러리:** Mscoree.dll에서 리소스로 사용 됩니다.  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [메타데이터 인터페이스](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
