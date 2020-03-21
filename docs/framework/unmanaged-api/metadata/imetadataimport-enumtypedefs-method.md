---
title: IMetaDataImport::EnumTypeDefs 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumTypeDefs
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumTypeDefs
helpviewer_keywords:
- EnumTypeDefs method [.NET Framework metadata]
- IMetaDataImport::EnumTypeDefs method [.NET Framework metadata]
ms.assetid: 4e508711-da92-4381-aaf8-6803075cdaa2
topic_type:
- apiref
ms.openlocfilehash: 2d6e86a7f5a93b900e79907f8ee0762869d7f737
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177292"
---
# <a name="imetadataimportenumtypedefs-method"></a>IMetaDataImport::EnumTypeDefs 메서드
현재 범위 내의 모든 형식을 나타내는 TypeDef 토큰을 열거합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT EnumTypeDefs (  
   [out] HCORENUM   *phEnum,
   [in]  mdTypeDef  rTypeDefs[],  
   [in]  ULONG      cMax,
   [out] ULONG      *pcTypeDefs  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `phEnum`  
 【아웃】 새 열거형에 대한 포인터입니다. 이 메서드의 첫 번째 호출에 대 한 NULL 이어야합니다.  
  
 `rTypeDefs`  
 【인】 TypeDef 토큰을 저장하는 데 사용되는 배열입니다.  
  
 `cMax`  
 [in] `rTypeDefs` 배열의 최대 크기입니다.  
  
 `pcTypeDefs`  
 【아웃】 에서 반환되는 TypeDef 토큰 `rTypeDefs`의 수입니다.  
  
## <a name="return-value"></a>Return Value  
  
|HRESULT|Description|  
|-------------|-----------------|  
|`S_OK`|`EnumTypeDefs`성공적으로 반환됩니다.|  
|`S_FALSE`|등록할 토큰이 없습니다. 이 경우 `pcTypeDefs` 0입니다.|  
  
## <a name="remarks"></a>설명  
 TypeDef 토큰은 클래스 또는 인터페이스와 같은 형식과 확장성 메커니즘을 통해 추가된 모든 형식을 나타냅니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** 코르h  
  
 **라이브러리:** MsCorEE.dll의 리소스로 포함  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [IMetaDataImport 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
