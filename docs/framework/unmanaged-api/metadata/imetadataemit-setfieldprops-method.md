---
title: IMetaDataEmit::SetFieldProps 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetFieldProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetFieldProps
helpviewer_keywords:
- IMetaDataEmit::SetFieldProps method [.NET Framework metadata]
- SetFieldProps method [.NET Framework metadata]
ms.assetid: 47132dda-fa92-4bd1-ae4b-24cd9a60665a
topic_type:
- apiref
ms.openlocfilehash: b921118f7c43edef3c07cbb34cbbd9119d36ce51
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177558"
---
# <a name="imetadataemitsetfieldprops-method"></a>IMetaDataEmit::SetFieldProps 메서드
지정된 필드 토큰에서 참조하는 필드의 기본값을 설정하거나 업데이트합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT SetFieldProps (  
    [in]  mdFieldDef  fd,
    [in]  DWORD       dwFieldFlags,
    [in]  DWORD       dwCPlusTypeFlag,
    [in]  void const  *pValue,
    [in]  ULONG       cchValue
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `fd`  
 【인】 대상 필드에 대한 토큰입니다.  
  
 `dwFieldFlags`  
 【인】 필드 특성입니다. 이것은 값의 `CorFieldAttr` 비트 마스크입니다.  
  
 `dwCPlusTypeFlag`  
 【인】 `ELEMENT_TYPE_` 에 대 한 상수 값입니다. *\** 이것은 값입니다. `CorElementType` 상수가 정의되지 않은 경우 이 `ELEMENT_TYPE_END`값을 로 설정합니다.  
  
 `pValue`  
 【인】 필드의 상수 값입니다.  
  
 `cchValue`  
 【인】 유니코드 문자의 크기입니다. `pValue`  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** 코르h  
  
 **라이브러리:** MSCorEE.dll의 리소스로 사용  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [IMetaDataEmit 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [IMetaDataEmit2 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
