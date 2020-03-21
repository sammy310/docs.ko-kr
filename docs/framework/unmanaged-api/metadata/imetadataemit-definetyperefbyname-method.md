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
ms.openlocfilehash: 23a6931b31ea2d7e4e8d1cb3dc8adf3a51216315
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175748"
---
# <a name="imetadataemitdefinetyperefbyname-method"></a>IMetaDataEmit::DefineTypeRefByName 메서드
현재 범위를 벗어난 지정된 범위에 정의된 형식에 대한 메타데이터 토큰을 가져옵니다.  
  
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
 【인】 해결 범위를 지정하는 토큰입니다. 다음 토큰 유형은 유효합니다.  
  
- `mdModuleRef`을 선택하면 호출이 정의된 동일한 어셈블리에서 형식이 정의된 경우  
  
- `mdAssemblyRef`에서는 호출자가 정의된 어셈블리가 아닌 어셈블리에 형식이 정의된 경우  
  
- `mdTypeRef`을 선택하면 형식이 중첩된 형식인 경우  
  
- `mdModule`을 선택하면 호출자는 정의된 동일한 모듈에서 형식이 정의됩니다.  
  
- Null, 형식이 전역적으로 정의된 경우.  
  
 `szName`  
 【인】 유니코드의 대상 형식의 이름입니다.  
  
 `ptr`  
 【아웃】 형식에 할당된 `mdTypeRef` 토큰에 대한 포인터입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** 코르h  
  
 **라이브러리:** MSCorEE.dll의 리소스로 사용  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [IMetaDataEmit 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [IMetaDataEmit2 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
