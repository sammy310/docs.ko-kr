---
title: IMetaDataFilter::IsTokenMarked 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataFilter.IsTokenMarked
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataFilter::IsTokenMarked
helpviewer_keywords:
- IMetaDataFilter::IsTokenMarked method [.NET Framework metadata]
- IsTokenMarked method [.NET Framework metadata]
ms.assetid: 7d90dcee-0206-4540-807b-06982fe65f1a
topic_type:
- apiref
ms.openlocfilehash: 47377e892aaf2bdd96a297630c47fe52215b0564
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177388"
---
# <a name="imetadatafilteristokenmarked-method"></a>IMetaDataFilter::IsTokenMarked 메서드
지정된 메타데이터 토큰이 처리된 것으로 표시되었는지 여부를 나타내는 값을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT IsTokenMarked (  
    [in]  mdToken  tk,
    [out] BOOL     *pIsMarked  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `tk`  
 【인】 처리 표시를 검사할 토큰입니다.  
  
 `pIsMarked`  
 【아웃】 처리된 경우값입니다. `true` `tk` 그렇지 `false`않으면 .  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** 코르h  
  
 **라이브러리:** MsCorEE.dll의 리소스로 사용  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [IMetaDataFilter 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadatafilter-interface.md)
