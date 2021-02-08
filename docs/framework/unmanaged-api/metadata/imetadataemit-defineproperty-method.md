---
description: IMetaDataEmit::D efineProperty 메서드에 대해 자세히 알아보세요.
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
ms.openlocfilehash: c0c0b6009f8674a5edebf1c982e277f4ca5b185b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99784034"
---
# <a name="imetadataemitdefineproperty-method"></a>IMetaDataEmit::DefineProperty 메서드

지정 된 및 메서드 접근자를 사용 하 여 지정 된 형식에 대 한 속성 정의를 만들고 `get` `set` 해당 속성 정의에 대 한 토큰을 가져옵니다.  
  
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
 진행 속성이 정의 되는 클래스 또는 인터페이스에 대 한 토큰입니다.  
  
 `szProperty`  
 진행 속성의 이름입니다.  
  
 `dwPropFlags`  
 진행 속성 플래그입니다.  
  
 `pvSig`  
 진행 속성 시그니처입니다.  
  
 `cbSig`  
 진행 의 바이트 수 `pvSig` 입니다.  
  
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
 진행 속성과 연결 된 다른 메서드의 배열입니다. 을 사용 하 여 배열을 종료 `mdTokenNil` 합니다.  
  
 `pmdProp`  
 제한이 `mdProperty` 할당 된 토큰입니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Cor  
  
 **라이브러리:** MSCorEE.dll에서 리소스로 사용 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [IMetaDataEmit 인터페이스](imetadataemit-interface.md)
- [IMetaDataEmit2 인터페이스](imetadataemit2-interface.md)
