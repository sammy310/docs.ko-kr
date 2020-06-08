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
ms.openlocfilehash: 2facc63023a20dd6aaac64d7d036324c31658bc8
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501315"
---
# <a name="imetadataemitdefineimportmember-method"></a>IMetaDataEmit::DefineImportMember 메서드
현재 범위 외부에 정의 된 형식 또는 모듈의 지정 된 멤버에 대 한 참조를 만들고 해당 참조에 대 한 토큰을 정의 합니다.  
  
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
 진행 대상 멤버를 가져올 어셈블리를 나타내는 [IMetaDataAssemblyImport](imetadataassemblyimport-interface.md) 인터페이스입니다.  
  
 `pbHashValue`  
 진행 에 지정 된 어셈블리에 대 한 해시를 포함 하는 배열입니다 `pAssemImport` .  
  
 `cbHashValue`  
 [in] `pbHashValue` 배열의 바이트 수입니다.  
  
 `pImport`  
 진행 대상 멤버를 가져올 메타 데이터 범위를 나타내는 [IMetaDataImport](imetadataimport-interface.md) 인터페이스입니다.  
  
 `mbMember`  
 진행 대상 멤버를 지정 하는 메타 데이터 토큰입니다. 토큰은 `mdMethodDef` (멤버 메서드의 경우), `mdProperty` (멤버 속성의 경우) 또는 `mdFieldDef` (멤버 필드의 경우) 토큰 일 수 있습니다.  
  
 `pAssemEmit`  
 진행 대상 멤버를 가져올 대상 어셈블리를 나타내는 [IMetaDataAssemblyEmit](imetadataassemblyemit-interface.md) 인터페이스입니다.  
  
 `tkParent`  
 진행 `mdTypeRef` `mdModuleRef` 대상 멤버를 소유 하는 형식 또는 모듈의 또는 토큰입니다.  
  
 `pmr`  
 제한이 `mdMemberRef`멤버 참조의 현재 범위에서 정의 된 토큰입니다.  
  
## <a name="remarks"></a>설명  
 메서드는로 지정 된 멤버를 조회 하 여 `DefineImportMember` `mbMember` 에 지정 된 다른 범위에 정의 되 `pImport` 고 해당 속성을 검색 합니다. 이 정보를 사용 하 여 현재 범위에서 [IMetaDataEmit::D efinememberref](imetadataemit-definememberref-method.md) 메서드를 호출 하 여 멤버 참조를 만듭니다.  
  
 일반적으로 메서드를 사용 하기 전에 `DefineImportMember` 현재 범위에서 대상 멤버의 부모 클래스, 인터페이스 또는 모듈에 대 한 형식 참조 또는 모듈 참조를 만들어야 합니다. 그런 다음이 참조에 대 한 메타 데이터 토큰이 인수에 전달 됩니다 `tkParent` . 나중에 컴파일러나 링커를 통해 해결 될 경우 대상 멤버의 부모에 대 한 참조를 만들 필요가 없습니다. 요약:  
  
- 대상 멤버가 필드 또는 메서드인 경우 [IMetaDataEmit::D efinetyperefbyname](imetadataemit-definetyperefbyname-method.md) 또는 [IMetaDataEmit::D efineImportType](imetadataemit-defineimporttype-method.md) 메서드를 사용 하 여 현재 범위에서 멤버의 부모 클래스 또는 부모 인터페이스에 대 한 형식 참조를 만듭니다.  
  
- 대상 멤버가 전역 변수나 전역 함수 (즉, 클래스 또는 인터페이스의 멤버가 아님) 인 경우 [IMetaDataEmit::D efinemoduleref](imetadataemit-definemoduleref-method.md) 메서드를 사용 하 여 현재 범위에서 멤버의 부모 모듈에 대 한 모듈 참조를 만듭니다.  
  
- 컴파일러 또는 링커가 대상 멤버의 부모를 나중에 확인 하는 경우를 전달 `mdTokenNil` `tkParent` 합니다. 이를 적용 하는 유일한 시나리오는 현재 모듈에 연결 되 고 메타 데이터가 병합 되는 .obj 파일에서 전역 함수 또는 전역 변수를 가져오는 경우입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Cor  
  
 **라이브러리:** Mscoree.dll에서 리소스로 사용 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [IMetaDataEmit 인터페이스](imetadataemit-interface.md)
- [IMetaDataEmit2 인터페이스](imetadataemit2-interface.md)
