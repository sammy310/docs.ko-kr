---
description: '자세히 알아보기: IMetaDataEmit:: SetPropertyProps 메서드'
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
ms.openlocfilehash: ad5efa86b4f774bcaa2251cb992c2dd52ac28bdd
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99771836"
---
# <a name="imetadataemitsetpropertyprops-method"></a>IMetaDataEmit::SetPropertyProps 메서드

[DefineProperty 메서드에](imetadataemit-defineproperty-method.md)대 한 이전 호출로 정의 된 속성에 대 한 메타 데이터에 저장 된 기능을 설정 합니다.  
  
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
 진행 변경할 속성의 토큰입니다.  
  
 `dwPropFlags`  
 진행 속성 플래그입니다.  
  
 `dwCPlusTypeFlag`  
 진행 속성의 기본값 형식입니다.  
  
 `pValue`  
 진행 속성의 기본값입니다.  
  
 `cchValue`  
 진행 의 (유니코드) 문자 수입니다 `pValue` .  
  
 `mdSetter`  
 진행 속성 값을 설정 하는 메서드입니다.  
  
 `mdGetter`  
 진행 속성 값을 가져오는 메서드입니다.  
  
 `rmdOtherMethods[]`  
 진행 속성과 연결 된 다른 메서드의 배열입니다. 토큰을 사용 하 여이 배열을 종료 `mdTokenNil` 합니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Cor  
  
 **라이브러리:** MSCorEE.dll에서 리소스로 사용 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [IMetaDataEmit 인터페이스](imetadataemit-interface.md)
- [IMetaDataEmit2 인터페이스](imetadataemit2-interface.md)
