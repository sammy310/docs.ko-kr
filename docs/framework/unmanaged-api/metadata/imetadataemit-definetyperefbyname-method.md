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
ms.openlocfilehash: b83c868f1a804d4e6f32adffc190ae086aa5e0a0
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719335"
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
  
- `mdModuleRef`호출자가 정의 된 동일한 어셈블리에서 형식이 정의 된 경우입니다.  
  
- `mdAssemblyRef`호출자가 정의 되어 있지 않은 어셈블리에서 형식이 정의 된 경우입니다.  
  
- `mdTypeRef`형식이 중첩 형식이 면입니다.  
  
- `mdModule`호출자가 정의 된 동일한 모듈에서 형식이 정의 된 경우입니다.  
  
- 형식이 전역적으로 정의 된 경우 Null입니다.  
  
 `szName`  
 진행 유니코드로 된 대상 형식의 이름입니다.  
  
 `ptr`  
 제한이 형식에 할당 된 토큰에 대 한 포인터 `mdTypeRef` 입니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Cor  
  
 **라이브러리:** MSCorEE.dll에서 리소스로 사용 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참조

- [IMetaDataEmit 인터페이스](imetadataemit-interface.md)
- [IMetaDataEmit2 인터페이스](imetadataemit2-interface.md)
