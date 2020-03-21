---
title: IMetaDataImport::EnumMembersWithName 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumMembersWithName
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumMembersWithName
helpviewer_keywords:
- IMetaDataImport::EnumMembersWithName method [.NET Framework metadata]
- EnumMembersWithName method [.NET Framework metadata]
ms.assetid: 7c9e9120-3104-42f0-86ce-19a025f20dcc
topic_type:
- apiref
ms.openlocfilehash: 7410f91a853f3a677a105dc2e12a86d723c9fad6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177314"
---
# <a name="imetadataimportenummemberswithname-method"></a>IMetaDataImport::EnumMembersWithName 메서드
지정한 이름을 가진 지정한 형식의 멤버를 나타내는 MemberDef 토큰을 열거합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT EnumMembersWithName (  
   [in, out] HCORENUM    *phEnum,
   [in]      mdTypeDef   cl,
   [in]      LPCWSTR     szName,
   [out]     mdToken     rMembers[],
   [in]      ULONG       cMax,
   [out]     ULONG       *pcTokens  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `phEnum`  
 【인, 아웃】 열거형에 대한 포인터입니다.  
  
 `cl`  
 【인】 멤버를 사용하여 형식을 나타내는 TypeDef 토큰을 개명합니다.  
  
 `szName`  
 【인】 열거자의 범위를 제한하는 멤버 이름입니다.  
  
 `rMembers`  
 【아웃】 MemberDef 토큰을 저장하는 데 사용되는 배열입니다.  
  
 `cMax`  
 [in] `rMembers` 배열의 최대 크기입니다.  
  
 `pcTokens`  
 【아웃】 에서 반환된 멤버Def 토큰의 `rMembers`실제 수입니다.  
  
## <a name="remarks"></a>설명  
 이 메서드는 필드 및 메서드를 등록하지만 속성이나 이벤트는 등록하지 않습니다. [IMetaDataImport::EnumMembers와](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enummembers-method.md) `EnumMembersWithName` 달리 지정된 이름이 없는 모든 필드 및 멤버 토큰은 삭제됩니다.  
  
## <a name="return-value"></a>Return Value  
  
|HRESULT|Description|  
|-------------|-----------------|  
|`S_OK`|`EnumTypeDefs`성공적으로 반환됩니다.|  
|`S_FALSE`|등록할 MemberDef 토큰이 없습니다. 이 경우 `pcTokens` 0입니다.|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** 코르h  
  
 **라이브러리:** MsCorEE.dll의 리소스로 포함  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [IMetaDataImport 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
