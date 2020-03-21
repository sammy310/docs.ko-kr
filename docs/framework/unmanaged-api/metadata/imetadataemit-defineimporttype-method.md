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
ms.openlocfilehash: 6825a5198976cc7ab2c04ebd6e782418dcf4a8f7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177689"
---
# <a name="imetadataemitdefineimporttype-method"></a>IMetaDataEmit::DefineImportType 메서드
현재 범위 외부에 정의된 지정된 형식에 대한 참조를 만들고 해당 참조에 대한 토큰을 정의합니다.  
  
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
 【인】 대상 형식을 가져오는 어셈블리를 나타내는 [IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) 인터페이스입니다.  
  
 `pbHashValue`  
 【인】 `pAssemImport`에서 지정한 어셈블리에 대한 해시가 포함된 배열입니다.  
  
 `cbHashValue`  
 [in] `pbHashValue` 배열의 바이트 수입니다.  
  
 `pImport`  
 【인】 대상 형식을 가져오는 메타데이터 범위를 나타내는 [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) 인터페이스입니다.  
  
 `tdImport`  
 【인】 대상 `mdTypeDef` 유형을 지정하는 토큰입니다.  
  
 `pAssemEmit`  
 【인】 대상 형식을 가져오는 어셈블리를 나타내는 [IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md) 인터페이스입니다.  
  
 `ptr`  
 【아웃】 형식 `mdTypeRef` 참조의 현재 범위에 정의된 토큰입니다.  
  
## <a name="remarks"></a>설명  
 [IMetaDataEmit::DefineImportMember](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimportmember-method.md) 메서드를 호출하기 전에 메서드를 `DefineImportType` 사용하여 멤버의 상위 클래스 또는 상위 인터페이스에 대한 현재 범위에서 형식 참조를 만들 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** 코르h  
  
 **라이브러리:** MSCorEE.dll의 리소스로 사용  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [IMetaDataEmit 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [IMetaDataEmit2 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
