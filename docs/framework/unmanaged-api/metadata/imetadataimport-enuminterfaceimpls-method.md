---
title: IMetaDataImport::EnumInterfaceImpls 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumInterfaceImpls
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumInterfaceImpls
helpviewer_keywords:
- IMetaDataImport::EnumInterfaceImpls method [.NET Framework metadata]
- EnumInterfaceImpls method [.NET Framework metadata]
ms.assetid: ba6e178f-128b-4e47-a13c-b4be73eb106c
topic_type:
- apiref
ms.openlocfilehash: b535fdd5027a26cc4dd0eafec9883f0186773dd1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175501"
---
# <a name="imetadataimportenuminterfaceimpls-method"></a>IMetaDataImport::EnumInterfaceImpls 메서드
지정된 `TypeDef`에 의해 구현된 모든 인터페이스를 탐색합니다.
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT EnumInterfaceImpls (  
   [in, out]  HCORENUM       *phEnum,
   [in]   mdTypeDef          td,  
   [out]  mdInterfaceImpl    rImpls[],
   [in]   ULONG              cMax,  
   [out]  ULONG*             pcImpls  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `phEnum`  
 【인, 아웃】 열거형에 대한 포인터입니다.  
  
 `td`  
 【인】 인터페이스 구현을 나타내는 MethodDef 토큰을 등록해야 하는 TypeDef의 토큰입니다.  
  
 `rImpls`  
 【아웃】 MethodDef 토큰을 저장하는 데 사용되는 배열입니다.  
  
 `cMax`  
 【인】 배열의 최대 `rImpls` 길이입니다.  
  
 `pcImpls`  
 【아웃】 에서 반환되는 실제 토큰 `rImpls`수입니다.  
  
## <a name="return-value"></a>Return Value  
  
|HRESULT|Description|  
|-------------|-----------------|  
|`S_OK`|`EnumInterfaceImpls`성공적으로 반환됩니다.|  
|`S_FALSE`|메서드Def 를 등록할 수 있는 토큰이 없습니다. 이 경우 `pcImpls` 0으로 설정됩니다.|  

## <a name="remarks"></a>설명

열거형은 지정된 `TypeDef`에 `mdInterfaceImpl` 의해 구현된 각 인터페이스에 대한 토큰 컬렉션을 반환합니다. 인터페이스 토큰은 인터페이스가 지정된 순서대로 반환됩니다(through `DefineTypeDef` or). `SetTypeDefProps` 반환된 `mdInterfaceImpl` 토큰의 속성은 [GetInterfaceImplProps](imetadataimport-getinterfaceimplprops-method.md)를 사용하여 쿼리할 수 있습니다.
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** 코르h  
  
 **라이브러리:** MsCorEE.dll의 리소스로 포함  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [IMetaDataImport 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
