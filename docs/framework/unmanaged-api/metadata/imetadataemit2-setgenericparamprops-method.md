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
ms.openlocfilehash: 7a93bbe0d7a9d9e6ff7505bbc215efa79176ad1f
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74440443"
---
# <a name="imetadataemit2setgenericparamprops-method"></a>IMetaDataEmit2::SetGenericParamProps 메서드
지정 된 토큰이 참조 하는 제네릭 매개 변수 정의에 대 한 속성 값을 설정 합니다.  
  
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
 진행 값을 설정할 제네릭 매개 변수 정의에 대 한 토큰입니다.  
  
 `dwParamFlags`  
 진행 제네릭 매개 변수의 형식을 설명 하는 [Corgenericparamattr](../../../../docs/framework/unmanaged-api/metadata/corgenericparamattr-enumeration.md) 열거형의 값입니다.  
  
 `szName`  
 [in] 선택적 항목으로, 값을 설정할 매개 변수의 이름입니다.  
  
 `reserved`  
 진행 향후 확장성을 위해 예약 되었습니다.  
  
 `rtkConstraints`  
 [in] 선택적 항목으로, 0으로 끝나는 형식의 제약 조건 배열입니다. 배열 멤버는 `mdTypeDef`, `mdTypeRef`또는 `mdTypeSpec` 메타 데이터 토큰 이어야 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Cor  
  
 **라이브러리:** Mscoree.dll에서 리소스로 사용 됩니다.  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고자료

- [IMetaDataEmit2 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [IMetaDataEmit 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
