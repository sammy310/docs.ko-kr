---
title: IMetaDataImport::EnumTypeRefs 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumTypeRefs
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumTypeRefs
helpviewer_keywords:
- EnumTypeRefs method [.NET Framework metadata]
- IMetaDataImport::EnumTypeRefs method [.NET Framework metadata]
ms.assetid: b4896b8f-8e97-469c-8089-e72a025661b5
topic_type:
- apiref
ms.openlocfilehash: e5d4ddd43b27d733a63c2e0dc5e92ffd2ba94a7f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175436"
---
# <a name="imetadataimportenumtyperefs-method"></a>IMetaDataImport::EnumTypeRefs 메서드
현재 메타데이터 범위에서 정의된 TypeRef 토큰을 열거합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT EnumTypeRefs (  
   [in, out] HCORENUM    *phEnum,
   [out] mdTypeRef       rTypeRefs[],  
   [in]  ULONG           cMax,
   [out] ULONG           *pcTypeRefs  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `phEnum`  
 【인, 아웃】 열거형에 대한 포인터입니다. 이 메서드의 첫 번째 호출에 대 한 NULL 이어야합니다.  
  
 `rTypeRefs`  
 【아웃】 TypeRef 토큰을 저장하는 데 사용되는 배열입니다.  
  
 `cMax`  
 [in] `rTypeRefs` 배열의 최대 크기입니다.  
  
 `pcTypeRefs`  
 【아웃】 에서 반환되는 TypeRef 토큰 수에 `rTypeRefs`대한 포인터입니다.  
  
## <a name="return-value"></a>Return Value  
  
|HRESULT|Description|  
|-------------|-----------------|  
|`S_OK`|`EnumTypeRefs`성공적으로 반환됩니다.|  
|`S_FALSE`|등록할 토큰이 없습니다. 이 경우 `pcTypeRefs` 0입니다.|  
  
## <a name="remarks"></a>설명  
 TypeRef 토큰은 형식에 대한 참조를 나타냅니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** 코르h  
  
 **라이브러리:** MsCorEE.dll의 리소스로 포함  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [IMetaDataImport 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
