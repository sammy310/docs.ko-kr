---
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
ms.openlocfilehash: 5fc71bf240b89afadbf8f2ba10906322921bdda2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175332"
---
# <a name="imetadataimportgetpropertyprops-method"></a>IMetaDataImport::GetPropertyProps 메서드
지정된 토큰으로 표시되는 속성의 메타데이터를 가져옵니다.  
  
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
 【인】 메타데이터를 반환하는 속성을 나타내는 토큰입니다.  
  
 `pClass`  
 【아웃】 속성을 구현하는 형식을 나타내는 TypeDef 토큰에 대한 포인터입니다.  
  
 `szProperty`  
 【아웃】 속성 이름을 보유하는 버퍼입니다.  
  
 `cchProperty`  
 【인】 의 와이드 문자의 `szProperty`크기입니다.  
  
 `pchProperty`  
 【아웃】 에서 반환되는 와이드 `szProperty`문자 수입니다.  
  
 `pdwPropFlags`  
 【아웃】 속성에 적용 된 모든 특성 플래그에 대 한 포인터입니다. 이 값은 [CorPropertyAttr](../../../../docs/framework/unmanaged-api/metadata/corpropertyattr-enumeration.md) 열거형의 비트 마스크입니다.  
  
 `ppvSig`  
 【아웃】 속성의 메타데이터 서명에 대한 포인터입니다.  
  
 `pbSig`  
 【아웃】 에서 반환되는 바이트 `ppvSig`수입니다.  
  
 `pdwCPlusTypeFlag`  
 【아웃】 속성의 기본값인 상수의 형식을 지정하는 플래그입니다. 이 값은 CorElementType 열거형에서 발원합니다.  
  
 `ppDefaultValue`  
 【아웃】 이 속성의 기본값을 저장하는 바이트에 대한 포인터입니다.  
  
 `pcchDefaultValue`  
 【아웃】 의 넓은 문자의 `ppDefaultValue`크기는 `pdwCPlusTypeFlag` ELEMENT_TYPE_STRING. 그렇지 않으면 이 값은 관련이 없습니다. 이 경우 `ppDefaultValue` 길이는 에 의해 `pdwCPlusTypeFlag`지정된 형식에서 유추됩니다.  
  
 `pmdSetter`  
 【아웃】 속성에 대 한 집합 접근자 메서드를 나타내는 MethodDef 토큰에 대 한 포인터입니다.  
  
 `pmdGetter`  
 【아웃】 속성에 대 한 get 접근자 메서드를 나타내는 MethodDef 토큰에 대 한 포인터입니다.  
  
 `rmdOtherMethod`  
 【아웃】 속성과 연결된 다른 메서드를 나타내는 MethodDef 토큰의 배열입니다.  
  
 `cMax`  
 [in] `rmdOtherMethod` 배열의 최대 크기입니다. 모든 메서드를 보유할 수 있을 만큼 큰 배열을 제공하지 않으면 경고 없이 건너뜁니다.  
  
 `pcOtherMethod`  
 【아웃】 에서 반환되는 MethodDef 토큰 `rmdOtherMethod`수입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** 코르h  
  
 **라이브러리:** MsCorEE.dll의 리소스로 포함  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [IMetaDataImport 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
