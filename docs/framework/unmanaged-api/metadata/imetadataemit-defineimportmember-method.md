---
title: IMetaDataEmit::DefineImportMember 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineImportMember
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineImportMember
helpviewer_keywords:
- DefineImportMember method [.NET Framework metadata]
- IMetaDataEmit::DefineImportMember method [.NET Framework metadata]
ms.assetid: c7dd94c6-335b-46ff-9dfe-505056db5673
topic_type:
- apiref
ms.openlocfilehash: a7449ffc8a8ccf2db62ab3cff2f9cfaffd0c72a9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175865"
---
# <a name="imetadataemitdefineimportmember-method"></a>IMetaDataEmit::DefineImportMember 메서드
현재 범위 외부에 정의된 형식 또는 모듈의 지정된 멤버에 대한 참조를 만들고 해당 참조에 대한 토큰을 정의합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT DefineImportMember (
    [in]  IMetaDataAssemblyImport  *pAssemImport,
    [in]  const void               *pbHashValue,
    [in]  ULONG                    cbHashValue,  
    [in]  IMetaDataImport          *pImport,
    [in]  mdToken                  mbMember,
    [in]  IMetaDataAssemblyEmit    *pAssemEmit,
    [in]  mdToken                  tkParent,
    [out] mdMemberRef              *pmr
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `pAssemImport`  
 【인】 대상 멤버를 가져오는 어셈블리를 나타내는 [IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) 인터페이스입니다.  
  
 `pbHashValue`  
 【인】 `pAssemImport`에서 지정한 어셈블리에 대한 해시가 포함된 배열입니다.  
  
 `cbHashValue`  
 [in] `pbHashValue` 배열의 바이트 수입니다.  
  
 `pImport`  
 【인】 대상 멤버를 가져오는 메타데이터 범위를 나타내는 [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) 인터페이스입니다.  
  
 `mbMember`  
 【인】 대상 멤버를 지정하는 메타데이터 토큰입니다. 토큰은 `mdMethodDef` (멤버 메서드에 대한), `mdProperty` (멤버 속성에 `mdFieldDef` 대한) 또는 (멤버 필드의) 토큰일 수 있습니다.  
  
 `pAssemEmit`  
 【인】 대상 멤버를 가져오는 어셈블리를 나타내는 [IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md) 인터페이스입니다.  
  
 `tkParent`  
 【인】 대상 `mdTypeRef` `mdModuleRef` 멤버를 소유하는 형식 또는 모듈에 대한 또는 토큰입니다.  
  
 `pmr`  
 【아웃】 멤버 `mdMemberRef` 참조의 현재 범위에 정의된 토큰입니다.  
  
## <a name="remarks"></a>설명  
 메서드는 `DefineImportMember` 다른 범위에 정의 `mbMember`된 에 의해 지정 된 `pImport`멤버를 검색 하 고 해당 속성을 검색 합니다. 이 정보를 사용하여 현재 범위의 [IMetaDataEmit::DefineMemberRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md) 메서드를 호출하여 멤버 참조를 만듭니다.  
  
 일반적으로 메서드를 `DefineImportMember` 사용하기 전에 현재 범위에서 대상 멤버의 상위 클래스, 인터페이스 또는 모듈에 대한 형식 참조 또는 모듈 참조를 만들어야 합니다. 그런 다음 이 참조에 대한 `tkParent` 메타데이터 토큰이 인수에 전달됩니다. 나중에 컴파일러 또는 링커에 의해 해결될 경우 대상 멤버의 부모에 대한 참조를 만들 필요가 없습니다. 요약하면  
  
- 대상 멤버가 필드 또는 메서드인 경우 [IMetaDataEmit::DefineTypeRefByName](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetyperefbyname-method.md) 또는 [IMetaDataEmit::DefineImportType](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md) 메서드를 사용하여 현재 범위에서 멤버의 상위 클래스 또는 상위 인터페이스에 대한 형식 참조를 만듭니다.  
  
- 대상 멤버가 전역 변수 또는 전역 함수인 경우(즉, 클래스 또는 인터페이스의 구성원이 아님) [IMetaDataEmit::DefineModuleRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemoduleref-method.md) 메서드를 사용하여 멤버의 상위 모듈에 대한 현재 범위에서 모듈 참조를 만듭니다.  
  
- 대상 멤버의 부모가 나중에 컴파일러 또는 링커에 의해 해결되면 `mdTokenNil` `tkParent`에서 전달합니다. 이것이 적용되는 유일한 시나리오는 전역 함수 또는 전역 변수를 현재 모듈에 연결되고 메타데이터가 병합되는 .obj 파일에서 가져오는 경우입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** 코르h  
  
 **라이브러리:** MSCorEE.dll의 리소스로 사용  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [IMetaDataEmit 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [IMetaDataEmit2 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
