---
title: IMetaDataEmit::DefineProperty 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineProperty
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineProperty
helpviewer_keywords:
- IMetaDataEmit::DefineProperty method [.NET Framework metadata]
- DefineProperty method [.NET Framework metadata]
ms.assetid: 5c4c1dc2-d40d-4173-bbe6-7058fb21c98f
topic_type:
- apiref
ms.openlocfilehash: eb3ecbf39376e7126b5ec93a26badcbf5076d1db
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175787"
---
# <a name="imetadataemitdefineproperty-method"></a>IMetaDataEmit::DefineProperty 메서드
지정된 및 `set` 메서드 접근자와 함께 지정된 `get` 형식에 대한 속성 정의를 만들고 해당 속성 정의에 대한 토큰을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT DefineProperty (
    [in]  mdTypeDef          td,
    [in]  LPCWSTR            szProperty,
    [in]  DWORD              dwPropFlags,
    [in]  PCCOR_SIGNATURE    pvSig,
    [in]  ULONG              cbSig,
    [in]  DWORD              dwCPlusTypeFlag,
    [in]  void const         *pValue,
    [in]  ULONG              cchValue,
    [in]  mdMethodDef        mdSetter,
    [in]  mdMethodDef        mdGetter,
    [in]  mdMethodDef        rmdOtherMethods[],
    [out] mdProperty         *pmdProp
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `td`  
 【인】 속성이 정의되는 클래스 또는 인터페이스에 대한 토큰입니다.  
  
 `szProperty`  
 【인】 속성의 이름입니다.  
  
 `dwPropFlags`  
 【인】 속성 플래그입니다.  
  
 `pvSig`  
 【인】 속성 서명입니다.  
  
 `cbSig`  
 【인】 의 바이트 `pvSig`수입니다.  
  
 `dwCPlusTypeFlag`  
 【인】 속성의 기본값의 형식입니다.  
  
 `pValue`  
 【인】 속성의 기본값입니다.  
  
 `cchValue`  
 【인】 에서 (유니코드) 문자의 `pValue`수입니다.  
  
 `mdSetter`  
 【인】 속성 값을 설정하는 메서드입니다.  
  
 `mdGetter`  
 【인】 속성 값을 얻는 메서드입니다.  
  
 `rmdOtherMethods[]`  
 【인】 속성과 연결된 다른 메서드의 배열입니다. `mdTokenNil`을 통해 배열을 종료합니다.  
  
 `pmdProp`  
 【아웃】 할당된 토큰입니다. `mdProperty`  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** 코르h  
  
 **라이브러리:** MSCorEE.dll의 리소스로 사용  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [IMetaDataEmit 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [IMetaDataEmit2 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
