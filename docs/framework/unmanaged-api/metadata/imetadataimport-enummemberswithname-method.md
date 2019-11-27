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
ms.openlocfilehash: ed193aab8beb0de1321aa1d52ec9f963b08b316c
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74441667"
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
 [in, out] 열거자에 대 한 포인터입니다.  
  
 `cl`  
 진행 열거할 멤버가 포함 된 형식을 나타내는 TypeDef 토큰입니다.  
  
 `szName`  
 진행 열거자의 범위를 제한 하는 멤버 이름입니다.  
  
 `rMembers`  
 제한이 MemberDef 토큰을 저장 하는 데 사용 되는 배열입니다.  
  
 `cMax`  
 [in] `rMembers` 배열의 최대 크기입니다.  
  
 `pcTokens`  
 제한이 `rMembers`에서 반환 된 실제 MemberDef 토큰 수입니다.  
  
## <a name="remarks"></a>주의  
 이 메서드는 필드 및 메서드를 열거 하지만 속성이 나 이벤트는 열거 하지 않습니다. [IMetaDataImport:: EnumMembers](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enummembers-method.md)와 달리 `EnumMembersWithName`는 지정 된 이름이 없는 모든 필드 및 멤버 토큰을 삭제 합니다.  
  
## <a name="return-value"></a>반환 값  
  
|HRESULT|설명|  
|-------------|-----------------|  
|`S_OK`|`EnumTypeDefs` 성공적으로 반환 되었습니다.|  
|`S_FALSE`|열거할 MemberDef 토큰이 없습니다. 이 경우 `pcTokens`은 0입니다.|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Cor  
  
 **라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [IMetaDataImport 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
