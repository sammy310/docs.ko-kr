---
title: IMetaDataEmit::DefineImportType 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineImportType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineImportType
helpviewer_keywords:
- DefineImportType method [.NET Framework metadata]
- IMetaDataEmit::DefineImportType method [.NET Framework metadata]
ms.assetid: 37fd27af-8062-4904-ace4-51bb78ec600a
topic_type:
- apiref
ms.openlocfilehash: 94ce4443be210fdfeb1bab197c3e603255e1cc4c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723248"
---
# <a name="imetadataemitdefineimporttype-method"></a>IMetaDataEmit::DefineImportType 메서드

현재 범위 외부에 정의 된 지정 된 형식에 대 한 참조를 만들고 해당 참조에 대 한 토큰을 정의 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT DefineImportType (
    [in]  IMetaDataAssemblyImport  *pAssemImport,
    [in]  const void               *pbHashValue,
    [in]  ULONG                    cbHashValue,
    [in]  IMetaDataImport          *pImport,
    [in]  mdTypeDef                tdImport,
    [in]  IMetaDataAssemblyEmit    *pAssemEmit,
    [out] mdTypeRef                *ptr  
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `pAssemImport`  
 진행 대상 유형을 가져올 어셈블리를 나타내는 [IMetaDataAssemblyImport](imetadataassemblyimport-interface.md) 인터페이스입니다.  
  
 `pbHashValue`  
 진행 에 지정 된 어셈블리에 대 한 해시를 포함 하는 배열입니다 `pAssemImport` .  
  
 `cbHashValue`  
 [in] `pbHashValue` 배열의 바이트 수입니다.  
  
 `pImport`  
 진행 대상 유형을 가져올 메타 데이터 범위를 나타내는 [IMetaDataImport](imetadataimport-interface.md) 인터페이스입니다.  
  
 `tdImport`  
 진행 `mdTypeDef` 대상 형식을 지정 하는 토큰입니다.  
  
 `pAssemEmit`  
 진행 대상 형식을 가져오는 대상 어셈블리를 나타내는 [IMetaDataAssemblyEmit](imetadataassemblyemit-interface.md) 인터페이스입니다.  
  
 `ptr`  
 제한이 `mdTypeRef` 형식 참조에 대 한 현재 범위에서 정의 된 토큰입니다.  
  
## <a name="remarks"></a>설명  

 [IMetaDataEmit::D efineImportMember](imetadataemit-defineimportmember-method.md) 메서드를 호출 하기 전에 메서드를 사용 하 여 `DefineImportType` 현재 범위에서 멤버의 부모 클래스 또는 부모 인터페이스에 대 한 형식 참조를 만들 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Cor  
  
 **라이브러리:** MSCorEE.dll에서 리소스로 사용 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참조

- [IMetaDataEmit 인터페이스](imetadataemit-interface.md)
- [IMetaDataEmit2 인터페이스](imetadataemit2-interface.md)
