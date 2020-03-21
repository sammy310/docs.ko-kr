---
title: IMetaDataAssemblyEmit::DefineExportedType 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.DefineExportedType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::DefineExportedType
helpviewer_keywords:
- IMetaDataAssemblyEmit::DefineExportedType method [.NET Framework metadata]
- DefineExportedType method [.NET Framework metadata]
ms.assetid: fad01d7a-3178-4c8c-9f0a-4641e3701c9b
topic_type:
- apiref
ms.openlocfilehash: 388f227377ddf73fe1297e1c777bb1c0607c13d2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177876"
---
# <a name="imetadataassemblyemitdefineexportedtype-method"></a>IMetaDataAssemblyEmit::DefineExportedType 메서드
지정된 내보낸 형식에 대한 메타데이터를 포함하는 `ExportedType` 구조를 만들고 연결된 메타데이터 토큰을 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT DefineExportedType (  
    [in]  LPCWSTR             szName,  
    [in]  mdToken             tkImplementation,
    [in]  mdTypeDef           tkTypeDef,  
    [in]  DWORD               dwExportedTypeFlags,  
    [out] mdExportedType      *pmdct  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `szName`  
 【인】 내보낼 형식의 이름입니다. 공통 언어 런타임의 버전 1.1의 경우 내보낸 형식의 이름은 형식에 `TypeDef` 지정된 이름과 정확히 일치해야 합니다.  
  
 `tkImplementation`  
 【인】 내보낸 형식이 구현되는 위치를 지정하는 토큰입니다. 유효한 값과 관련 된 의미는 다음과 같습니다.  
  
- `mdFile`형식은 이 어셈블리 내의 다른 파일에서 구현됩니다.  
  
- `mdAssemblyRef`형식은 다른 어셈블리에서 구현됩니다.  
  
- `mdExportedTYpe`형식은 다른 형식 내에 중첩됩니다.  
  
- `mdFileNil`형식은 매니페스트와 동일한 파일에 있으며 중첩된 형식이 아닙니다.  
  
 `tkTypeDef`  
 【인】 내보낼 형식을 지정하는 메타데이터에 대한 토큰입니다. 이 값은 형식을 `TypeDef` 구현하는 파일의 테이블에 입력되며 해당 파일이 이 어셈블리에 있는 경우에만 관련이 있습니다.  
  
 `dwExportedTypeFlags`  
 【인】 내보낸 형식에 대 한 속성 설정을 정의 하는 [CorTypeAttr](../../../../docs/framework/unmanaged-api/metadata/cortypeattr-enumeration.md) 열거형 값의 비트 조합입니다.  
  
 `pmdct`  
 【아웃】 내보낸 형식을 나타내는 반환된 메타데이터 토큰에 대한 포인터입니다.  
  
## <a name="remarks"></a>설명  
 `ExportedType` 메타데이터 구조는 이 어셈블리에 의해 노출되고 매니페스트를 포함하는 모듈이 아닌 모듈에서 구현되는 각 형식에 대해 정의되어야 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항을](../../../../docs/framework/get-started/system-requirements.md)참조하십시오.  
  
 **헤더:** 코르h  
  
 **라이브러리:** MsCorEE.dll의 리소스로 사용  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [IMetaDataAssemblyEmit 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
