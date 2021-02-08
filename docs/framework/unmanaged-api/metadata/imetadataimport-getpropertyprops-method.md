---
description: '자세히 알아보기: IMetaDataImport:: GetPropertyProps 메서드'
title: IMetaDataImport::GetPropertyProps 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetPropertyProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetPropertyProps
helpviewer_keywords:
- GetPropertyProps method [.NET Framework metadata]
- IMetaDataImport::GetPropertyProps method [.NET Framework metadata]
ms.assetid: dc0ff3e6-7e7d-4f6c-948d-52b28f5cb78c
topic_type:
- apiref
ms.openlocfilehash: 25fae4488117a35d94479ce501154679b6b536ad
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99789179"
---
# <a name="imetadataimportgetpropertyprops-method"></a>IMetaDataImport::GetPropertyProps 메서드

지정 된 토큰이 나타내는 속성의 메타 데이터를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetPropertyProps (  
   [in]  mdProperty        prop,  
   [out] mdTypeDef         *pClass,
   [out] LPCWSTR           szProperty,
   [in]  ULONG             cchProperty,
   [out] ULONG             *pchProperty,
   [out] DWORD             *pdwPropFlags,
   [out] PCCOR_SIGNATURE   *ppvSig,
   [out] ULONG             *pbSig,
   [out] DWORD             *pdwCPlusTypeFlag,
   [out] UVCP_CONSTANT     *ppDefaultValue,  
   [out] ULONG             *pcchDefaultValue,  
   [out] mdMethodDef       *pmdSetter,
   [out] mdMethodDef       *pmdGetter,
   [out] mdMethodDef       rmdOtherMethod[],  
   [in]  ULONG             cMax,
   [out] ULONG             *pcOtherMethod
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `prop`  
 진행 메타 데이터를 반환할 속성을 나타내는 토큰입니다.  
  
 `pClass`  
 제한이 속성을 구현 하는 형식을 나타내는 TypeDef 토큰에 대 한 포인터입니다.  
  
 `szProperty`  
 제한이 속성 이름을 보유할 버퍼입니다.  
  
 `cchProperty`  
 진행 의 와이드 문자 크기입니다 `szProperty` .  
  
 `pchProperty`  
 제한이 에서 반환 되는 와이드 문자 수입니다 `szProperty` .  
  
 `pdwPropFlags`  
 제한이 속성에 적용 된 특성 플래그에 대 한 포인터입니다. 이 값은 [Corpropertyattr](corpropertyattr-enumeration.md) 열거형의 비트 마스크입니다.  
  
 `ppvSig`  
 제한이 속성의 메타 데이터 서명에 대 한 포인터입니다.  
  
 `pbSig`  
 제한이 에서 반환 된 바이트 수입니다 `ppvSig` .  
  
 `pdwCPlusTypeFlag`  
 제한이 속성의 기본값 인 상수의 형식을 지정 하는 플래그입니다. 이 값은 CorElementType 열거형에서 가져온 값입니다.  
  
 `ppDefaultValue`  
 제한이 이 속성의 기본값을 저장 하는 바이트에 대 한 포인터입니다.  
  
 `pcchDefaultValue`  
 제한이 가 ELEMENT_TYPE_STRING 경우의 와이드 문자 크기 `ppDefaultValue` `pdwCPlusTypeFlag` 이 고, 그렇지 않으면이 값은 관련이 없습니다. 이 경우의 길이는에 `ppDefaultValue` 의해 지정 된 형식에서 유추 됩니다 `pdwCPlusTypeFlag` .  
  
 `pmdSetter`  
 제한이 속성의 set 접근자 메서드를 나타내는 MethodDef 토큰에 대 한 포인터입니다.  
  
 `pmdGetter`  
 제한이 속성의 get 접근자 메서드를 나타내는 MethodDef 토큰에 대 한 포인터입니다.  
  
 `rmdOtherMethod`  
 제한이 속성과 연결 된 다른 메서드를 나타내는 MethodDef 토큰의 배열입니다.  
  
 `cMax`  
 [in] `rmdOtherMethod` 배열의 최대 크기입니다. 모든 메서드를 저장할 수 있을 만큼 충분히 크지 않은 배열을 제공 하지 않으면 경고 없이 건너뜁니다.  
  
 `pcOtherMethod`  
 제한이 에서 반환 된 MethodDef 토큰의 수입니다 `rmdOtherMethod` .  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Cor  
  
 **라이브러리:** MsCorEE.dll의 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [IMetaDataImport 인터페이스](imetadataimport-interface.md)
- [IMetaDataImport2 인터페이스](imetadataimport2-interface.md)
