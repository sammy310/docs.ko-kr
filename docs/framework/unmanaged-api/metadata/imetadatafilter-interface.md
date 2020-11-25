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
ms.openlocfilehash: 2c22e45ca3d33b0a81ff0ecd90bf7574c45676bd
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95701850"
---
# <a name="imetadatafilter-interface"></a>IMetaDataFilter 인터페이스

이미 수행된 반복 작업을 방지하려고 메타데이터 토큰을 표시 및 필터링하는 메서드를 제공합니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[IsTokenMarked 메서드](imetadatafilter-istokenmarked-method.md)|지정 된 메타 데이터 토큰이 처리 되었는지 여부를 나타내는 값을 가져옵니다.|  
|[MarkToken 메서드](imetadatafilter-marktoken-method.md)|지정 된 메타 데이터 토큰이 처리 되었음을 나타내는 값을 설정 합니다.|  
|[UnmarkAll 메서드](imetadatafilter-unmarkall-method.md)|현재 메타 데이터 범위에 있는 모든 토큰에서 처리 표시를 제거 합니다.|  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Cor  
  
 **라이브러리:** MsCorEE.dll에서 리소스로 사용 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참조

- [메타데이터 인터페이스](metadata-interfaces.md)
