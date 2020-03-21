---
title: IMetaDataImport::EnumMethodImpls 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumMethodImpls
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumMethodImpls
helpviewer_keywords:
- EnumMethodImpls method [.NET Framework metadata]
- IMetaDataImport::EnumMethodImpls method [.NET Framework metadata]
ms.assetid: 4e0f865d-88b5-44bd-be35-492622e5e08e
topic_type:
- apiref
ms.openlocfilehash: e766cec8fd84713e12c43cd1095650ed5b757bcb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175475"
---
# <a name="imetadataimportenummethodimpls-method"></a>IMetaDataImport::EnumMethodImpls 메서드
지정한 형식의 메서드를 나타내는 MethodBody 및 MethodDeclaration 토큰을 열거합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT EnumMethodImpls (  
   [in, out] HCORENUM    *phEnum,
   [in]      mdTypeDef   td,
   [out]     mdToken     rMethodBody[],
   [out]     mdToken     rMethodDecl[],
   [in]      ULONG       cMax,
   [in]      ULONG       *pcTokens  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `phEnum`  
 【인, 아웃】 열거형에 대한 포인터입니다. 이 메서드의 첫 번째 호출에 대 한 NULL 이어야합니다.  
  
 `td`  
 【인】 메서드를 개명하는 형식을 위한 TypeDef 토큰입니다.  
  
 `rMethodBody`  
 【아웃】 MethodBody 토큰을 저장할 배열입니다.  
  
 `rMethodDecl`  
 【아웃】 MethodDeclaration 토큰을 저장할 배열입니다.  
  
 `cMax`  
 【인】 `rMethodBody` 및 `rMethodDecl` 배열의 최대 크기입니다.  
  
 `pcTokens`  
 【인】 반환된 메서드의 실제 `rMethodBody` `rMethodDecl`수및 .  
  
## <a name="return-value"></a>Return Value  
  
|HRESULT|Description|  
|-------------|-----------------|  
|`S_OK`|`EnumMethodImpls`성공적으로 반환됩니다.|  
|`S_FALSE`|등록할 메서드 토큰이 없습니다. 이 경우 `pcTokens` 0입니다.|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** 코르h  
  
 **라이브러리:** MsCorEE.dll의 리소스로 포함  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [IMetaDataImport 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
