---
title: IMetaDataImport2::EnumMethodSpecs 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataImport2.EnumMethodSpecs
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport2::EnumMethodSpecs
helpviewer_keywords:
- IMetaDataImport2::EnumMethodSpecs method [.NET Framework metadata]
- EnumMethodSpecs method [.NET Framework metadata]
ms.assetid: b3fc1e6c-bcb6-4915-baf8-7dc0a31b8724
topic_type:
- apiref
ms.openlocfilehash: 2df53ba53c64e042abc54a1d2ac043d301acdde9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177181"
---
# <a name="imetadataimport2enummethodspecs-method"></a>IMetaDataImport2::EnumMethodSpecs 메서드
지정된 MethodDef 또는 MemberRef 토큰과 연결된 MethodSpec 토큰 배열에 대한 열거기를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT EnumMethodSpecs (  
    [in, out] HCORENUM      *phEnum,
    [in]      mdToken       tk,  
    [out]     mdMethodSpec  rMethodSpecs[],  
    [in]      ULONG         cMax,  
    [out]     ULONG         *pcMethodSpecs  
);
```  
  
## <a name="parameters"></a>매개 변수  
 `phEnum`  
 【인, 아웃】 에 대한 열거형에 대한 `rMethodSpecs`포인터입니다.  
  
 `tk`  
 【인】 MethodSpec 토큰을 등록할 메서드를 나타내는 MemberRef 또는 MethodDef 토큰입니다. 값이 `tk` 0(0)이면 범위의 모든 MethodSpec 토큰이 큐어됩니다.  
  
 `rMethodSpecs`  
 【아웃】 열거할 MethodSpec 토큰의 배열입니다.  
  
 `cMax`  
 【인】 에 배치할 요청된 최대 `rMethodSpecs`토큰 수입니다.  
  
 `pcMethodSpecs`  
 【아웃】 에 `rMethodSpecs`배치된 토큰의 반환 된 수입니다.  
  
## <a name="return-value"></a>Return Value  
  
|HRESULT|Description|  
|-------------|-----------------|  
|`S_OK`|`EnumMethodSpecs`성공적으로 반환됩니다.|  
|`S_FALSE`|`phEnum`멤버 요소가 없습니다. 이 경우 `pcMethodSpecs` 0(0)으로 설정됩니다.|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** 코르h  
  
 **라이브러리:** MsCorEE.dll의 리소스로 사용  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [IMetaDataImport2 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
- [IMetaDataImport 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
