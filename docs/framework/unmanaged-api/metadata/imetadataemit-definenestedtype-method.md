---
title: IMetaDataEmit::DefineNestedType 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineNestedType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineNestedType
helpviewer_keywords:
- IMetaDataEmit::DefineNestedType method [.NET Framework metadata]
- DefineNestedType method [.NET Framework metadata]
ms.assetid: 1e994de6-4628-459c-b967-b34be1e9fe4f
topic_type:
- apiref
ms.openlocfilehash: 3b8fd9876563bace52a6088747d1ca4ed26ea872
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175813"
---
# <a name="imetadataemitdefinenestedtype-method"></a>IMetaDataEmit::DefineNestedType 메서드
형식 정의의 메타데이터 서명을 만들고 `mdTypeDef` 해당 형식에 대한 토큰을 반환하며 정의된 형식이 `tdEncloser` 매개 변수에서 참조하는 형식의 멤버임을 지정합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT DefineNestedType (
    [in]  LPCWSTR     szTypeDef,  
    [in]  DWORD       dwTypeDefFlags,
    [in]  mdToken     tkExtends,
    [in]  mdToken     rtkImplements[],
    [in]  mdTypeDef   tdEncloser,
    [out] mdTypeDef   *ptd  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `szTypeDef`  
 【인】 유니코드의 형식 이름입니다.  
  
 `dwTypeDefFlags`  
 【인】 `TypeDef` 속성입니다. 이것은 값의 `CorTypeAttr` 비트 마스크입니다.  
  
 `tkExtends`  
 【인】 기본 클래스의 토큰입니다. 이것은 또는 `mdTypeDef` 토큰입니다. `mdTypeRef`  
  
 `rtkImplements`[]  
 【인】 이 클래스 또는 인터페이스가 구현하는 인터페이스를 지정하는 토큰 배열입니다.  
  
 `tdEncloser`  
 【인】 둘러싸는 형식의 토큰입니다. 배열의 마지막 요소는 . `mdTokenNil`  
  
 `ptd`  
 【아웃】 할당된 토큰입니다. `mdTypeDef`  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** 코르h  
  
 **라이브러리:** MSCorEE.dll의 리소스로 사용  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [IMetaDataEmit 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [IMetaDataEmit2 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
