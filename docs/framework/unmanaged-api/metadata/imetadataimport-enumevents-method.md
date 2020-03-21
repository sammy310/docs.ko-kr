---
title: IMetaDataImport::EnumEvents 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumEvents
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumEvents
helpviewer_keywords:
- IMetaDataImport::EnumEvents method [.NET Framework metadata]
- EnumEvents method [.NET Framework metadata]
ms.assetid: e1efedcb-3dd7-42ae-a399-21c24728aec5
topic_type:
- apiref
ms.openlocfilehash: bd50d63b1f7080f510c29f90979b7b36242af1c0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177365"
---
# <a name="imetadataimportenumevents-method"></a>IMetaDataImport::EnumEvents 메서드
지정한 TypeDef 토큰에 대한 이벤트 정의 토큰을 열거합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT EnumEvents (
   [in, out] HCORENUM    *phEnum,
   [in]      mdTypeDef   td,
   [out]     mdEvent     rEvents[],
   [in]      ULONG       cMax,  
   [out]    ULONG        *pcEvents  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `phEnum`  
 【인, 아웃】 열거형에 대한 포인터입니다.  
  
 `td`  
 【인】 이벤트 정의를 지글거칠 TypeDef 토큰입니다.  
  
 `rEvents`  
 【아웃】 반환된 이벤트의 배열입니다.  
  
 `cMax`  
 [in] `rEvents` 배열의 최대 크기입니다.  
  
 `pcEvents`  
 【아웃】 에서 반환되는 이벤트의 `rEvents`실제 수입니다.  
  
## <a name="return-value"></a>Return Value  
  
|HRESULT|Description|  
|-------------|-----------------|  
|`S_OK`|`EnumEvents`성공적으로 반환됩니다.|  
|`S_FALSE`|등록할 이벤트가 없습니다. 이 경우 `pcEvents` 0입니다.|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** 코르h  
  
 **라이브러리:** MsCorEE.dll의 리소스로 포함  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [IMetaDataImport 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
