---
description: '자세히 알아보기: IMetaDataEmit:: SetTypeDefProps 메서드'
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
ms.openlocfilehash: 1160d20e7ceb422390f8cd725a75fdb4f42318e7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99706502"
---
# <a name="imetadataemitsettypedefprops-method"></a>IMetaDataEmit::SetTypeDefProps 메서드

[IMetaDataEmit:D](imetadataemit-definetypedef-method.md)에 대 한 이전 호출로 정의 된 형식의 기능을 설정 합니다.  
  
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
 진행 `mdTypeDef` IMetaDataEmit에 대 한 원래 호출에서 가져온 토큰 [::D efin을 정의](imetadataemit-definetypedef-method.md)합니다.  
  
 `dwTypeDefFlags`  
 [in] `TypeDef` 특성. 값의 비트 마스크입니다 `CorTypeAttr` .  
  
 `tkExtends`  
 진행 `mdToken` 기본 클래스의입니다. IMetaDataEmit에 대 한 이전 호출에서 가져옵니다. [:D efineImportType](imetadataemit-defineimporttype-method.md)또는 `null` .  
  
 `rtkImplements[]`  
 진행 이 형식이 구현 하는 인터페이스에 대 한 토큰의 배열입니다. 이러한 `mdTypeRef` 토큰은 [IMetaDataEmit::D efineImportType](imetadataemit-defineimporttype-method.md)을 사용 하 여 가져옵니다. 배열의 마지막 요소는 이어야 합니다 `mdTokenNil` .  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Cor  
  
 **라이브러리:** MSCorEE.dll에서 리소스로 사용 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [IMetaDataEmit 인터페이스](imetadataemit-interface.md)
- [IMetaDataEmit2 인터페이스](imetadataemit2-interface.md)
