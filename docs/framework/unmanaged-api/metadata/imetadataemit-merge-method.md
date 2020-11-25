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
ms.openlocfilehash: e64d644b511f7c3249c48b9642bfd3163142af3c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722013"
---
# <a name="imetadataemitmerge-method"></a>IMetaDataEmit::병합 메서드

병합할 범위 목록에 지정 된 가져온 범위를 추가 합니다.  
  
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
 진행 병합할 가져온 범위를 식별 하는 [IMetaDataImport](imetadataimport-interface.md) 개체에 대 한 포인터입니다.  
  
 `pIMap`  
 진행 토큰 다시 매핑을 지정 하는 [IMapToken](imaptoken-interface.md) 개체에 대 한 포인터입니다.  
  
 `pHandler`  
 진행 오류를 지정 하는 [IUnknown](/cpp/atl/iunknown) 개체에 대 한 포인터입니다.  
  
## <a name="remarks"></a>설명  

 [IMetaDataEmit:: MergeEnd](imetadataemit-mergeend-method.md) 를 호출 하 여 메타 데이터의 병합을 단일 범위로 트리거합니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Cor  
  
 **라이브러리:** MSCorEE.dll에서 리소스로 사용 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참조

- [IMetaDataEmit 인터페이스](imetadataemit-interface.md)
- [IMetaDataEmit2 인터페이스](imetadataemit2-interface.md)
