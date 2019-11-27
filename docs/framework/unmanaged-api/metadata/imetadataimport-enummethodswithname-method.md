---
title: IMetaDataImport::EnumMethodsWithName 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumMethodsWithName
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumMethodsWithName
helpviewer_keywords:
- IMetaDataImport::EnumMethodsWithName method [.NET Framework metadata]
- EnumMethodsWithName method [.NET Framework metadata]
ms.assetid: a8624913-2e23-46ad-a0c1-bb8eccbbf20f
topic_type:
- apiref
ms.openlocfilehash: b0817288040550b5f4c3c4ec063f6a7fdb004137
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74450066"
---
# <a name="imetadataimportenummethodswithname-method"></a>IMetaDataImport::EnumMethodsWithName 메서드
지정한 TypeDef 토큰이 참조하는 형식으로 정의되고 지정한 이름을 가진 메서드를 열거합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT EnumMethodsWithName (  
   [in, out] HCORENUM    *phEnum,  
   [in]  mdTypeDef       cl,  
   [in]  LPCWSTR         szName,  
   [out] mdMethodDef     rMethods[],  
   [in]  ULONG           cMax,  
   [out] ULONG           *pcTokens  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `phEnum`  
 [in, out] 열거자에 대 한 포인터입니다. 이 메서드의 첫 번째 호출에서는 NULL 이어야 합니다.  
  
 `cl`  
 진행 열거할 메서드를 포함 하는 형식을 나타내는 TypeDef 토큰입니다.  
  
 `szName`  
 진행 열거형의 범위를 제한 하는 이름입니다.  
  
 `rMethods`  
 제한이 MethodDef 토큰을 저장 하는 데 사용 되는 배열입니다.  
  
 `cMax`  
 [in] `rMethods` 배열의 최대 크기입니다.  
  
 `pcTokens`  
 제한이 `rMethods`에서 반환 된 MethodDef 토큰 수입니다.  
  
## <a name="remarks"></a>주의  
 이 메서드는 필드 및 메서드를 열거 하지만 속성이 나 이벤트는 열거 하지 않습니다. [IMetaDataImport:: EnumMethods](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enummethods-method.md)달리 `EnumMethodsWithName`는 지정 된 이름이 없는 메서드 토큰을 모두 삭제 합니다.  
  
## <a name="return-value"></a>반환 값  
  
|HRESULT|설명|  
|-------------|-----------------|  
|`S_OK`|`EnumMethodsWithName` 성공적으로 반환 되었습니다.|  
|`S_FALSE`|열거할 토큰이 없습니다. 이 경우 `pcTokens`은 0입니다.|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Cor  
  
 **라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [IMetaDataImport 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
