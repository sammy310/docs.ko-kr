---
title: IMetaDataEmit::SetTypeDefProps 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetTypeDefProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetTypeDefProps
helpviewer_keywords:
- SetTypeDefProps method [.NET Framework metadata]
- IMetaDataEmit::SetTypeDefProps method [.NET Framework metadata]
ms.assetid: 480d596a-759f-4d29-ac1a-3dbff8f3544d
topic_type:
- apiref
ms.openlocfilehash: e59e7695246b2c83171e77352e16464258516f8d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177459"
---
# <a name="imetadataemitsettypedefprops-method"></a>IMetaDataEmit::SetTypeDefProps 메서드
[IMetaDataEmit::DefineTypeDef에](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md)대한 사전 호출에 의해 정의된 형식의 기능을 설정합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT SetTypeDefProps (  
    [in]  mdTypeDef   td,
    [in]  DWORD       dwTypeDefFlags,
    [in]  mdToken     tkExtends,
    [in]  mdToken     rtkImplements[]
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `td`  
 【인】 `mdTypeDef` [IMetaDataEmit::DefineTypeDef에](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md)대한 원래 호출에서 얻은 토큰입니다.  
  
 `dwTypeDefFlags`  
 【인】 `TypeDef` 속성입니다. 이것은 값의 `CorTypeAttr` 비트 마스크입니다.  
  
 `tkExtends`  
 【인】 기본 `mdToken` 클래스의 입니다. [IMetaDataEmit::DefineImportType](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md)에 대한 이전 호출에서 `null`얻은 또는 .  
  
 `rtkImplements[]`  
 【인】 이 형식이 구현하는 인터페이스에 대한 토큰 배열입니다. 이러한 `mdTypeRef` 토큰은 [IMetaDataEmit::DefineImportType](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md). 배열의 마지막 요소는 .가 `mdTokenNil`있어야 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** 코르h  
  
 **라이브러리:** MSCorEE.dll의 리소스로 사용  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [IMetaDataEmit 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [IMetaDataEmit2 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
