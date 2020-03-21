---
title: IMetaDataEmit::DefineField 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineField
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineField
helpviewer_keywords:
- IMetaDataEmit::DefineField method [.NET Framework metadata]
- DefineField method, IMetaDataEmit interface [.NET Framework metadata
ms.assetid: 6b5be4fc-2e86-499c-8b09-833160bca767
topic_type:
- apiref
ms.openlocfilehash: 8ca5ab70f60de4d783800fb18612a8f04cb9cee1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177710"
---
# <a name="imetadataemitdefinefield-method"></a>IMetaDataEmit::DefineField 메서드
지정된 메타데이터 시그니처가 있는 필드에 대한 정의를 만들고 해당 필드 정의에 대한 토큰을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT DefineField (
    [in]  mdTypeDef   td,
    [in]  LPCWSTR     szName,
    [in]  DWORD       dwFieldFlags,
    [in]  PCCOR_SIGNATURE pvSigBlob,
    [in]  ULONG       cbSigBlob,
    [in]  DWORD       dwCPlusTypeFlag,
    [in]  void const  *pValue,
    [in]  ULONG       cchValue,
    [out] mdFieldDef  *pmd
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `td`  
 【인】 둘러싸는 클래스 또는 인터페이스에 대한 `mdTypeDef` 토큰입니다.  
  
 `szName`  
 【인】 유니코드의 필드 이름입니다.  
  
 `dwFieldFlags`  
 【인】 필드 특성입니다. 이것은 값의 `CorFieldAttr` 비트 마스크입니다.  
  
 `pvSigBlob`  
 【인】 필드 시그니처를 BLOB로 합니다.  
  
 `cbSigBlob`  
 【인】 의 바이트 `pvSigBlob`수입니다.  
  
 `dwCPlusTypeFlag`  
 【인】 `ELEMENT_TYPE_` 에 대 한 상수 값입니다. *\** 이것은 값입니다. `CorElementType` 필드에 대한 상수 값을 정의하지 `ELEMENT_TYPE_END`않으면 을 사용합니다.  
  
 `pValue`  
 【인】 필드의 상수 값입니다.  
  
 `cchValue`  
 【인】 의 (유니코드) 문자의 `pValue`크기입니다.  
  
 `pmd`  
 【아웃】 할당된 토큰입니다. `mdFieldDef`  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** 코르h  
  
 **라이브러리:** MSCorEE.dll의 리소스로 사용  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [IMetaDataEmit 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [IMetaDataEmit2 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
