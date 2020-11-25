---
title: IMetaDataAssemblyImport::EnumExportedTypes 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.EnumExportedTypes
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::EnumExportedTypes
helpviewer_keywords:
- EnumExportedTypes method [.NET Framework metadata]
- IMetaDataAssemblyImport::EnumExportedTypes method [.NET Framework metadata]
ms.assetid: e5912ed8-e4ce-438b-8ea3-d9e4c288d109
topic_type:
- apiref
ms.openlocfilehash: a8b2377c48331ff9f0e69876c51fb78c7190f694
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95708896"
---
# <a name="imetadataassemblyimportenumexportedtypes-method"></a>IMetaDataAssemblyImport::EnumExportedTypes 메서드

현재 메타 데이터 범위에서 어셈블리 매니페스트에 참조 된 내보낸 형식을 열거 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT EnumExportedTypes (  
    [in, out] HCORENUM     *phEnum,
    [out] mdExportedType   rExportedTypes[],
    [in]  ULONG            cMax,
    [out] ULONG            *pcTokens  
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `phEnum`  
 [in, out] 열거자에 대 한 포인터입니다. 이 값은 메서드가 처음 호출 될 때 null 값 이어야 합니다 `EnumExportedTypes` .  
  
 `rExportedTypes`  
 제한이 `mdExportedType` 메타 데이터 토큰의 열거형입니다.  
  
 `cMax`  
 진행 `mdExportedType` 배열에 배치할 수 있는 최대 토큰 수입니다 `rExportedTypes` .  
  
 `pcTokens`  
 제한이 `mdExportedType` 에 실제로 배치 된 토큰의 수 `rExportedTypes` 입니다.  
  
## <a name="return-value"></a>반환 값  
  
|HRESULT|설명|  
|-------------|-----------------|  
|`S_OK`|`EnumExportedTypes` 성공적으로 반환 되었습니다.|  
|`S_FALSE`|열거할 토큰이 없습니다. 이 경우 `pcTokens` 는 0으로 설정 됩니다.|  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조 하세요.  
  
 **헤더:** Cor  
  
 **라이브러리:** MsCorEE.dll에서 리소스로 사용 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참조

- [IMetaDataAssemblyImport 인터페이스](imetadataassemblyimport-interface.md)
