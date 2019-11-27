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
ms.openlocfilehash: 40f24a4ea628ce92a27ab1bfe97fc87a57dfa4f0
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74432552"
---
# <a name="imetadataemitdefinefield-method"></a>IMetaDataEmit::DefineField 메서드
지정 된 메타 데이터 시그니처를 사용 하 여 필드에 대 한 정의를 만들고 해당 필드 정의에 대 한 토큰을 가져옵니다.  
  
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
 진행 바깥쪽 클래스 또는 인터페이스에 대 한 `mdTypeDef` 토큰입니다.  
  
 `szName`  
 진행 유니코드의 필드 이름입니다.  
  
 `dwFieldFlags`  
 진행 필드 특성입니다. `CorFieldAttr` 값의 비트 마스크입니다.  
  
 `pvSigBlob`  
 진행 BLOB으로 필드 시그니처입니다.  
  
 `cbSigBlob`  
 진행 `pvSigBlob`바이트 수입니다.  
  
 `dwCPlusTypeFlag`  
 진행 상수 값에 대 한 `ELEMENT_TYPE_` *\** 입니다. `CorElementType` 값입니다. 필드에 대 한 상수 값을 정의 하지 않는 경우 `ELEMENT_TYPE_END`를 사용 합니다.  
  
 `pValue`  
 진행 필드의 상수 값입니다.  
  
 `cchValue`  
 진행 `pValue`의 (유니코드) 문자 크기입니다.  
  
 `pmd`  
 제한이 할당 된 `mdFieldDef` 토큰입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Cor  
  
 **라이브러리:** Mscoree.dll에서 리소스로 사용 됩니다.  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고자료

- [IMetaDataEmit 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [IMetaDataEmit2 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
