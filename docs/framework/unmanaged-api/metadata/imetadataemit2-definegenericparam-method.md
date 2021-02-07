---
description: IMetaDataEmit2::D efineGenericParam 메서드에 대해 자세히 알아보세요.
title: IMetaDataEmit2::DefineGenericParam 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataEmit2.DefineGenericParam
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit2::DefineGenericParam
helpviewer_keywords:
- IMetaDataEmit2::DefineGenericParam method [.NET Framework metadata]
- DefineGenericParam method [.NET Framework metadata]
ms.assetid: 47b2a3b6-907d-43dc-858d-1ae7dca1316a
topic_type:
- apiref
ms.openlocfilehash: 813661adca162f47a864b19c9754b49072bb4c7b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99745790"
---
# <a name="imetadataemit2definegenericparam-method"></a>IMetaDataEmit2::DefineGenericParam 메서드

제네릭 형식 매개 변수에 대 한 정의를 만들고 해당 제네릭 형식 매개 변수에 대 한 토큰을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT DefineGenericParam (
    [in]  mdToken         tk,
    [in]  ULONG           ulParamSeq,
    [in]  DWORD           dwParamFlags,
    [in]  LPCWSTR         szname,
    [in]  DWORD           reserved,
    [in]  mdToken         rtkConstraints[],
    [out] mdGenericParam  *pgp  
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `tk`  
 진행 `mdTypeDef` `mdMethodDef` 제네릭 매개 변수를 정의할 메서드나 생성자를 나타내는 또는 토큰입니다.  
  
 `ulParamSeq`  
 진행 제네릭 매개 변수의 인덱스입니다.  
  
 `dwParamFlags`  
 진행 제네릭 매개 변수의 형식을 설명 하는 [Corgenericparamattr](corgenericparamattr-enumeration.md) 열거형의 값입니다.  
  
 `szname`  
 진행 매개 변수의 이름입니다.  
  
 `reserved`  
 진행 이 매개 변수는 나중에 확장할 수 있도록 예약 되어 있습니다.  
  
 `rtkConstraints`  
 진행 0으로 끝나는 형식의 제약 조건 배열입니다. 배열 멤버는 `mdTypeDef` , `mdTypeRef` 또는 `mdTypeSpec` 메타 데이터 토큰 이어야 합니다.  
  
 `pgp`  
 제한이 제네릭 매개 변수를 나타내는 토큰입니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Cor  
  
 **라이브러리:** MsCorEE.dll에서 리소스로 사용 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [IMetaDataEmit2 인터페이스](imetadataemit2-interface.md)
- [IMetaDataEmit 인터페이스](imetadataemit-interface.md)
