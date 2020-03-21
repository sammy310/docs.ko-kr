---
title: IMetaDataImport::EnumMethods 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumMethods
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumMethods
helpviewer_keywords:
- IMetaDataImport::EnumMethods method [.NET Framework metadata]
- EnumMethods method [.NET Framework metadata]
ms.assetid: 8cc3b0c3-d97d-4f71-9e7d-ef2a92b4959a
topic_type:
- apiref
ms.openlocfilehash: 218b65b5899692774c434ae136a3976ecb97ea2f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177303"
---
# <a name="imetadataimportenummethods-method"></a>IMetaDataImport::EnumMethods 메서드
지정한 형식의 메서드를 나타내는 MethodDef 토큰을 열거합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT EnumMethods (  
   [in, out] HCORENUM   *phEnum,
   [in]  mdTypeDef      cl,
   [out] mdMethodDef    rMethods[],
   [in]  ULONG          cMax,
   [out] ULONG          *pcTokens  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `phEnum`  
 【인, 아웃】 열거형에 대한 포인터입니다. 이 메서드의 첫 번째 호출에 대 한 NULL 이어야합니다.  
  
 `cl`  
 【인】 개율할 메서드를 사용하여 형식을 나타내는 TypeDef 토큰입니다.  
  
 `rMethods`  
 【아웃】 MethodDef 토큰을 저장할 배열입니다.  
  
 `cMax`  
 【인】 MethodDef `rMethods` 배열의 최대 크기입니다.  
  
 `pcTokens`  
 【아웃】 에서 반환되는 MethodDef 토큰 `rMethods`수입니다.  
  
## <a name="return-value"></a>Return Value  
  
|HRESULT|Description|  
|-------------|-----------------|  
|`S_OK`|`EnumMethods`성공적으로 반환됩니다.|  
|`S_FALSE`|메서드Def 를 등록할 수 있는 토큰이 없습니다. 이 경우 `pcTokens` 0입니다.|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** 코르h  
  
 **라이브러리:** MsCorEE.dll의 리소스로 포함  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [IMetaDataImport 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
