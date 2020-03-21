---
title: IMetaDataImport2::EnumGenericParams 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataImport2.EnumGenericParams
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport2::EnumGenericParams
helpviewer_keywords:
- EnumGenericParams method [.NET Framework metadata]
- IMetaDataImport2::EnumGenericParams method [.NET Framework metadata]
ms.assetid: b50488a5-3cf0-483c-82dc-2892a3ec61ac
topic_type:
- apiref
ms.openlocfilehash: 55709e79cd8bdb36fe1e32ee8a699fccb1b1bbc8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175306"
---
# <a name="imetadataimport2enumgenericparams-method"></a>IMetaDataImport2::EnumGenericParams 메서드
지정된 TypeDef 또는 MethodDef 토큰과 연결된 일반 매개 변수 토큰 배열에 대한 열거기를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
HRESULT EnumGenericParams (  
   [in, out] HCORENUM     *phEnum,
   [in]  mdToken          tk,  
   [out] mdGenericParam   rGenericParams[],
   [in]  ULONG            cMax,
   [out] ULONG            *pcGenericParams  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `phEnum`  
 【인, 아웃】 열거형에 대한 포인터입니다.  
  
 `tk`  
 【인】 제네릭 매개 변수를 개명할 TypeDef 또는 MethodDef 토큰입니다.  
  
 `rGenericParams`  
 【아웃】 열거할 제네릭 매개 변수의 배열입니다.  
  
 `cMax`  
 【인】 에 배치할 요청된 최대 `rGenericParams`토큰 수입니다.  
  
 `pcGenericParams`  
 【아웃】 에 `rGenericParams`배치된 토큰의 반환 된 수입니다.  
  
## <a name="return-value"></a>Return Value  
  
|HRESULT|Description|  
|-------------|-----------------|  
|`S_OK`|`EnumGenericParams`성공적으로 반환됩니다.|  
|`S_FALSE`|`phEnum`멤버 요소가 없습니다. 이 경우 `pcGenericParams` 0(0)으로 설정됩니다.|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** 코르h  
  
 **라이브러리:** MsCorEE.dll의 리소스로 사용  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [IMetaDataImport2 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
- [IMetaDataImport 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
