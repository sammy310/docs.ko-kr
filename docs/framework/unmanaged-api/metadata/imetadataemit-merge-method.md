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
ms.openlocfilehash: 759358822ed865c89f6f55084d1e7f6143506e93
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175709"
---
# <a name="imetadataemitmerge-method"></a>IMetaDataEmit::병합 메서드
병합할 범위 목록에 지정된 가져온 범위를 추가합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT Merge (
    [in]  IMetaDataImport  *pImport,
    [in]  IMapToken        *pHostMapToken,
    [in]  IUnknown         *pHandler
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `pImport`  
 【인】 병합할 가져온 범위를 식별하는 [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) 개체에 대한 포인터입니다.  
  
 `pIMap`  
 【인】 토큰 다시 매핑을 지정하는 [IMapToken](../../../../docs/framework/unmanaged-api/metadata/imaptoken-interface.md) 개체에 대한 포인터입니다.  
  
 `pHandler`  
 【인】 오류를 지정하는 [IUnknown](/cpp/atl/iunknown) 개체에 대한 포인터입니다.  
  
## <a name="remarks"></a>설명  
 [IMetaDataEmit::MergeEnd호출하여](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-mergeend-method.md) 메타데이터를 단일 범위로 병합합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** 코르h  
  
 **라이브러리:** MSCorEE.dll의 리소스로 사용  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [IMetaDataEmit 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [IMetaDataEmit2 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
