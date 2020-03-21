---
title: IMetaDataEmit::SetPropertyProps 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetPropertyProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetPropertyProps
helpviewer_keywords:
- SetPropertyProps method [.NET Framework metadata]
- IMetaDataEmit::SetPropertyProps method [.NET Framework metadata]
ms.assetid: e2501fc8-b2bc-4dcc-9205-e3acd5a53ffe
topic_type:
- apiref
ms.openlocfilehash: dc6375f3e2cff1a744a8ff2e6a6adab27bbf8af3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177472"
---
# <a name="imetadataemitsetpropertyprops-method"></a>IMetaDataEmit::SetPropertyProps 메서드
[정의 속성 메서드에](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineproperty-method.md)대 한 이전 호출에 의해 정의 된 속성에 대 한 메타 데이터에 저장 된 기능을 설정 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT SetPropertyProps (
    [in]  mdProperty      pr,
    [in]  DWORD           dwPropFlags,
    [in]  DWORD           dwCPlusTypeFlag,
    [in]  void const      *pValue,
    [in]  ULONG           cchValue,
    [in]  mdMethodDef     mdSetter,
    [in]  mdMethodDef     mdGetter,
    [in]  mdMethodDef     rmdOtherMethods[]
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `pr`  
 【인】 속성을 변경할 토큰  
  
 `dwPropFlags`  
 【인】 속성 플래그입니다.  
  
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
 【인】 속성과 연결된 다른 메서드의 배열입니다. 토큰으로 이 `mdTokenNil` 배열을 종료합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** 코르h  
  
 **라이브러리:** MSCorEE.dll의 리소스로 사용  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [IMetaDataEmit 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [IMetaDataEmit2 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
