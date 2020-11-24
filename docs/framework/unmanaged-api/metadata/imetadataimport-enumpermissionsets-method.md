---
title: IMetaDataImport::EnumPermissionSets 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumPermissionSets
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumPermissionSets
helpviewer_keywords:
- EnumPermissionSets method [.NET Framework metadata]
- IMetaDataImport::EnumPermissionSets method [.NET Framework metadata]
ms.assetid: 347d7e5c-c90f-45ad-bd1e-2c7912b0b19c
topic_type:
- apiref
ms.openlocfilehash: eef2c733f96d74e3353a940cc90f1a631cf48a36
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95690527"
---
# <a name="imetadataimportenumpermissionsets-method"></a>IMetaDataImport::EnumPermissionSets 메서드

지정한 메타데이터 범위의 개체에 대한 권한을 열거합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT EnumPermissionSets  
   [in, out] HCORENUM      *phEnum,
   [in]      mdToken       tk,
   [in]      DWORD         dwActions,  
   [out]     mdPermission  rPermission[],  
   [in]      ULONG         cMax,  
   [out]     ULONG         *pcTokens  
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `phEnum`  
 [in, out] 열거자에 대 한 포인터입니다. 이 메서드의 첫 번째 호출에서는 NULL 이어야 합니다.  
  
 `tk`  
 진행 검색 범위를 제한 하는 메타 데이터 토큰 또는 가능한 가장 넓은 범위를 검색 하는 NULL입니다.  
  
 `dwActions`  
 진행 <xref:System.Security.Permissions.SecurityAction> 에 포함할 값을 나타내는 플래그 `rPermission` 또는 모든 동작을 반환 하는 0입니다.  
  
 `rPermission`  
 제한이 사용 권한 토큰을 저장 하는 데 사용 되는 배열입니다.  
  
 `cMax`  
 [in] `rPermission` 배열의 최대 크기입니다.  
  
 `pcTokens`  
 제한이 에서 반환 된 권한 토큰의 수 `rPermission` 입니다.  
  
## <a name="return-value"></a>반환 값  
  
|HRESULT|설명|  
|-------------|-----------------|  
|`S_OK`|`EnumPermissionSets` 성공적으로 반환 되었습니다.|  
|`S_FALSE`|열거할 토큰이 없습니다. 이 경우는 `pcTokens` 0입니다.|  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Cor  
  
 **라이브러리:** MsCorEE.dll의 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참조

- [IMetaDataImport 인터페이스](imetadataimport-interface.md)
- [IMetaDataImport2 인터페이스](imetadataimport2-interface.md)
