---
title: IMetaDataImport::EnumCustomAttributes 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumCustomAttributes
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumCustomAttributes
helpviewer_keywords:
- EnumCustomAttributes method [.NET Framework metadata]
- IMetaDataImport::EnumCustomAttributes method [.NET Framework metadata]
ms.assetid: 798513a0-68b1-4d04-bc5b-782a4445ea68
topic_type:
- apiref
ms.openlocfilehash: 61b5678a546bdbadbcc6d8ee86447cb17ce72b99
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175527"
---
# <a name="imetadataimportenumcustomattributes-method"></a>IMetaDataImport::EnumCustomAttributes 메서드
지정된 형식 또는 멤버와 연결된 사용자 지정 특성 정의 토큰을 연수합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT EnumCustomAttributes (
   [in, out] HCORENUM      *phEnum,  
   [in]  mdToken            tk,
   [in]  mdToken            tkType,
   [out] mdCustomAttribute  rCustomAttributes[],
   [in]  ULONG              cMax,  
   [out, optional] ULONG   *pcCustomAttributes  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `phEnum`  
 【인, 아웃】 반환된 열거형에 대한 포인터입니다.  
  
 `tk`  
 【인】 열거형 범위에 대한 토큰 또는 모든 사용자 지정 특성에 대한 0입니다.  
  
 `tkType`  
 【인】 등록할 특성 형식의 생성자 또는 `null` 모든 형식에 대한 토큰입니다.  
  
 `rCustomAttributes`  
 【아웃】 사용자 지정 특성 토큰의 배열입니다.  
  
 `cMax`  
 [in] `rCustomAttributes` 배열의 최대 크기입니다.  
  
 `pcCustomAttributes`  
 [아웃, 선택 사항] 에서 반환되는 실제 토큰 `rCustomAttributes`값 수입니다.  
  
## <a name="return-value"></a>Return Value  
  
|HRESULT|Description|  
|-------------|-----------------|  
|`S_OK`|`EnumCustomAttributes`성공적으로 반환됩니다.|  
|`S_FALSE`|등록할 사용자 지정 특성이 없습니다. 이 경우 `pcCustomAttributes` 0입니다.|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** 코르h  
  
 **라이브러리:** MsCorEE.dll의 리소스로 포함  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [IMetaDataImport 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
