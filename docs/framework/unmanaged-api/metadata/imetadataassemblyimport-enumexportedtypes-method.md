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
ms.openlocfilehash: f00fe5bce2f808265add228406dfaa2ccc267545
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176008"
---
# <a name="imetadataassemblyimportenumexportedtypes-method"></a>IMetaDataAssemblyImport::EnumExportedTypes 메서드
어셈블리 매니페스트에서 참조되는 내보낸 형식을 현재 메타데이터 범위에서 탐색합니다.  
  
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
 【인, 아웃】 열거형에 대한 포인터입니다. `EnumExportedTypes` 메서드를 처음 호출할 때 null 값이어야 합니다.  
  
 `rExportedTypes`  
 【아웃】 메타데이터 토큰의 `mdExportedType` 열거형입니다.  
  
 `cMax`  
 【인】 배열에 배치할 수 있는 `mdExportedType` 최대 `rExportedTypes` 토큰 수입니다.  
  
 `pcTokens`  
 【아웃】 실제로 에 `mdExportedType` 배치된 토큰 `rExportedTypes`수입니다.  
  
## <a name="return-value"></a>Return Value  
  
|HRESULT|Description|  
|-------------|-----------------|  
|`S_OK`|`EnumExportedTypes`성공적으로 반환됩니다.|  
|`S_FALSE`|등록할 토큰이 없습니다. 이 경우 `pcTokens` 0으로 설정됩니다.|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항을](../../../../docs/framework/get-started/system-requirements.md)참조하십시오.  
  
 **헤더:** 코르h  
  
 **라이브러리:** MsCorEE.dll의 리소스로 사용  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [IMetaDataAssemblyImport 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
