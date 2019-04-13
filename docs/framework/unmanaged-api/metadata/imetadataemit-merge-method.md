---
title: IMetaDataEmit::병합 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.Merge
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::Merge
helpviewer_keywords:
- IMetaDataEmit::Merge method [.NET Framework metadata]
- Merge method [.NET Framework metadata]
ms.assetid: 7596220c-f699-4b6c-8ae7-c83220610650
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 179cfc5c0725934e21d7b89a2f8d4c934b049f78
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59106057"
---
# <a name="imetadataemitmerge-method"></a>IMetaDataEmit::병합 메서드
병합할 범위의 목록에 지정된 된 가져온된 범위를 추가 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT Merge (   
    [in]  IMetaDataImport  *pImport,   
    [in]  IMapToken        *pHostMapToken,   
    [in]  IUnknown         *pHandler   
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `pImport`  
 [in] 에 대 한 포인터를 [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) 병합할 가져온된 범위를 식별 하는 개체입니다.  
  
 `pIMap`  
 [in] 에 대 한 포인터를 [IMapToken](../../../../docs/framework/unmanaged-api/metadata/imaptoken-interface.md) 토큰 다시 매핑을 지정 하는 개체입니다.  
  
 `pHandleer`  
 [in] 에 대 한 포인터를 [IUnknown](/cpp/atl/iunknown) 오류를 지정 하는 개체입니다.  
  
## <a name="remarks"></a>설명  
 호출 [imetadataemit:: Mergeend](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-mergeend-method.md) 단일 범위로 메타 데이터는 병합을 트리거할 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** Cor.h  
  
 **라이브러리:** MSCorEE.dll에서 리소스로 사용  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고자료

- [IMetaDataEmit 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [IMetaDataEmit2 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
