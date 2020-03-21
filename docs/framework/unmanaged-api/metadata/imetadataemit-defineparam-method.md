---
title: IMetaDataEmit::DefineParam 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineParam
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineParam
helpviewer_keywords:
- IMetaDataEmit::DefineParam method [.NET Framework metadata]
- DefineParam method [.NET Framework metadata]
ms.assetid: d86a3d14-4796-4909-9591-dfafe3de5ce4
topic_type:
- apiref
ms.openlocfilehash: 2807458549db02598ba05f2aa80fa6ea6fbc5a13
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177701"
---
# <a name="imetadataemitdefineparam-method"></a>IMetaDataEmit::DefineParam 메서드
지정된 토큰에서 참조하는 메서드에 대해 지정된 시그니처를 사용하여 매개 변수 정의를 만들고 해당 매개 변수 정의에 대한 토큰을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT DefineParam (  
    [in]  mdMethodDef md,
    [in]  ULONG       ulParamSeq,
    [in]  LPCWSTR     szName,
    [in]  DWORD       dwParamFlags,
    [in]  DWORD       dwCPlusTypeFlag,
    [in]  void const  *pValue,  
    [in]  ULONG       cchValue,
    [out] mdParamDef  *ppd
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `md`  
 【인】 매개 변수가 정의되는 메서드의 토큰입니다.  
  
 `ulParamSeq`  
 【인】 매개 변수 시퀀스 번호입니다.  
  
 `szName`  
 【인】 유니코드의 매개 변수 이름입니다.  
  
 `dwParamFlags`  
 【인】 매개 변수에 대한 플래그입니다. 이것은 값의 `CorParamAttr` 비트 마스크입니다.  
  
 `dwCPlusTypeFlag`  
 【인】 `ELEMENT_TYPE_` 상수 값에 대한 값입니다. *\**  
  
 `pValue`  
 【인】 매개 변수의 상수 값입니다.  
  
 `cchValue`  
 【인】 유니코드 문자의 크기입니다. `pValue`  
  
 `ppd`  
 【아웃】 할당된 토큰입니다. `mdParamDef`  
  
## <a name="remarks"></a>설명  
 시퀀스 `ulParamSeq` 값은 매개변수에 대해 1로 시작합니다. 반환 값에는 시퀀스 번호가 0입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** 코르h  
  
 **라이브러리:** MSCorEE.dll의 리소스로 사용  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [IMetaDataEmit 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [IMetaDataEmit2 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
