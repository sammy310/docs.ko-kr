---
title: IMetaDataEmit::DefineTypeRefByName 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineTypeRefByName
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineTypeRefByName
helpviewer_keywords:
- DefineTypeRefByName method [.NET Framework metadata]
- IMetaDataEmit::DefineTypeRefByName method [.NET Framework metadata]
ms.assetid: c30a4ce3-2d3e-411a-98df-e62ac4a5dd50
topic_type:
- apiref
ms.openlocfilehash: 3dfdd473b01bfe83def52f957c52e0f4d11375ad
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74434389"
---
# <a name="imetadataemitdefinetyperefbyname-method"></a>IMetaDataEmit::DefineTypeRefByName 메서드
현재 범위를 벗어난 지정 된 범위에 정의 된 형식에 대 한 메타 데이터 토큰을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT DefineTypeRefByName (   
    [in]  mdToken     tkResolutionScope,   
    [in]  LPCWSTR     szName,   
    [out] mdTypeRef   *ptr   
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `tkResolutionScope`  
 진행 확인 범위를 지정 하는 토큰입니다. 유효한 토큰 형식은 다음과 같습니다.  
  
- 호출자가 정의 된 동일한 어셈블리에서 형식이 정의 된 경우에는 `mdModuleRef`합니다.  
  
- 호출자가 정의 된 어셈블리 이외의 어셈블리에서 형식이 정의 된 경우에는를 `mdAssemblyRef`합니다.  
  
- 형식이 중첩 형식이 면이 고, 그렇지 않으면 `mdTypeRef`입니다.  
  
- 호출자가 정의 된 동일한 모듈에서 형식이 정의 된 경우에는 `mdModule`합니다.  
  
- 형식이 전역적으로 정의 된 경우 Null입니다.  
  
 `szName`  
 진행 유니코드로 된 대상 형식의 이름입니다.  
  
 `ptr`  
 제한이 형식에 할당 된 `mdTypeRef` 토큰에 대 한 포인터입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Cor  
  
 **라이브러리:** Mscoree.dll에서 리소스로 사용 됩니다.  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [IMetaDataEmit 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [IMetaDataEmit2 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
