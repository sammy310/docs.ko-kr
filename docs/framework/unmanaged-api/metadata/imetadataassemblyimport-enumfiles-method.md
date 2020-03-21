---
title: IMetaDataAssemblyImport::EnumFiles 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.EnumFiles
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::EnumFiles
helpviewer_keywords:
- IMetaDataAssemblyImport::EnumFiles method [.NET Framework metadata]
- EnumFiles method [.NET Framework metadata]
ms.assetid: f0d721e2-b946-426d-8e20-9124bd04e4cb
topic_type:
- apiref
ms.openlocfilehash: 70f76318f51047cb81262f744a6fbed5fe401692
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177810"
---
# <a name="imetadataassemblyimportenumfiles-method"></a>IMetaDataAssemblyImport::EnumFiles 메서드
현재 어셈블리 매니페스트에서 참조하는 파일을 열거합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT EnumFiles (  
    [in, out] HCORENUM    *phEnum,
    [out] mdFile          rFiles[],
    [in]  ULONG           cMax,
    [out] ULONG           *pcTokens  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `phEnum`  
 【인, 아웃】 열거형에 대한 포인터입니다. 이 메서드의 첫 번째 호출에 대 한 null 값이어야 합니다.  
  
 `rFiles`  
 【아웃】 메타데이터 토큰을 `mdFile` 저장하는 데 사용되는 배열입니다.  
  
 `cMax`  
 【인】 에 `rFiles`배치할 `mdFile` 수 있는 최대 토큰 수입니다.  
  
 `pcTokens`  
 【아웃】 실제로 에 `mdFile` 배치된 토큰 `rFiles`수입니다.  
  
## <a name="return-value"></a>Return Value  
  
|HRESULT|Description|  
|-------------|-----------------|  
|`S_OK`|`EnumFiles`성공적으로 반환됩니다.|  
|`S_FALSE`|등록할 토큰이 없습니다. 이 경우 `pcTokens` 0으로 설정됩니다.|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** 코르h  
  
 **라이브러리:** MsCorEE.dll의 리소스로 사용  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [IMetaDataAssemblyImport 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
