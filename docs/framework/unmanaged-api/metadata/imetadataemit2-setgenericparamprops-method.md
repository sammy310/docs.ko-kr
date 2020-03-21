---
title: IMetaDataEmit2::SetGenericParamProps 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataEmit2.SetGenericParamProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit2::SetGenericParamProps
helpviewer_keywords:
- IMetaDataEmit2::SetGenericParamProps method [.NET Framework metadata]
- SetGenericParamProps method [.NET Framework metadata]
ms.assetid: cd93a48d-1fed-4706-bec6-a05dc3b64fbd
topic_type:
- apiref
ms.openlocfilehash: fd7f149e806727d849cdceb3ffbc5dc7392fcf1d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177415"
---
# <a name="imetadataemit2setgenericparamprops-method"></a>IMetaDataEmit2::SetGenericParamProps 메서드
지정된 토큰에서 참조하는 제네릭 매개 변수 정의에 대한 속성 값을 설정합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT SetGenericParamProps (  
    [in] mdGenericParam   gp,
    [in] DWORD            dwParamFlags,
    [in] LPCWSTR          szName,
    [in] DWORD            reserved,
    [in] mdToken          rtkConstraints[]  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `gp`  
 【인】 값을 설정할 제네릭 매개 변수 정의에 대한 토큰입니다.  
  
 `dwParamFlags`  
 【인】 제네릭 매개 변수에 대한 형식을 설명하는 [CorGenericParamAttr](../../../../docs/framework/unmanaged-api/metadata/corgenericparamattr-enumeration.md) 열거형의 값입니다.  
  
 `szName`  
 [in] 선택적 항목으로, 값을 설정할 매개 변수의 이름입니다.  
  
 `reserved`  
 【인】 향후 확장성을 위해 예약되었습니다.  
  
 `rtkConstraints`  
 [in] 선택적 항목으로, 형식 제약 조건의 0-종단 배열입니다. 배열 멤버는 `mdTypeDef`. `mdTypeRef` `mdTypeSpec`  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** 코르h  
  
 **라이브러리:** MsCorEE.dll의 리소스로 사용  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [IMetaDataEmit2 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [IMetaDataEmit 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
