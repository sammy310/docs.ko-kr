---
title: IMetaDataImport::EnumMembers 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumMembers
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumMembers
helpviewer_keywords:
- IMetaDataImport::EnumMembers method [.NET Framework metadata]
- EnumMembers method [.NET Framework metadata]
ms.assetid: 3fb8e178-342b-4c89-9bcf-f7f834e6cb77
topic_type:
- apiref
ms.openlocfilehash: 20c7a90f27defa18a5ef311d1f3a549b81fc5c40
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175488"
---
# <a name="imetadataimportenummembers-method"></a>IMetaDataImport::EnumMembers 메서드
지정한 형식의 멤버를 나타내는 MemberDef 토큰을 열거합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT EnumMembers (
   [in, out]  HCORENUM    *phEnum,
   [in]  mdTypeDef   cl,
   [out] mdToken     rMembers[],
   [in]  ULONG       cMax,
   [out] ULONG       *pcTokens  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `phEnum`  
 【인, 아웃】 열거형에 대한 포인터입니다.  
  
 `cl`  
 【인】 멤버를 등록할 형식을 나타내는 TypeDef 토큰입니다.  
  
 `rMembers`  
 【아웃】 MemberDef 토큰을 보유하는 데 사용되는 배열입니다.  
  
 `cMax`  
 [in] `rMembers` 배열의 최대 크기입니다.  
  
 `pcTokens`  
 【아웃】 에서 반환된 멤버Def 토큰의 `rMembers`실제 수입니다.  
  
## <a name="return-value"></a>Return Value  
  
|HRESULT|Description|  
|-------------|-----------------|  
|`S_OK`|`EnumMembers`성공적으로 반환됩니다.|  
|`S_FALSE`|등록할 MemberDef 토큰이 없습니다. 이 경우 `pcTokens` 0입니다.|  
  
## <a name="remarks"></a>설명  
 클래스에 대한 멤버 컬렉션을 등록할 때 `EnumMembers` 클래스에 직접 정의된 멤버(필드 및 메서드는 있지만 속성이나 이벤트는 **아님)만** 반환합니다. 클래스가 상속된 멤버에 대한 구현을 제공하는 경우에도 클래스가 상속하는 멤버는 반환되지 않습니다. 상속된 멤버를 등록하려면 호출자는 상속 체인을 명시적으로 걸어야 합니다. 상속 체인에 대한 규칙은 원래 메타데이터를 내보낸 언어 또는 컴파일러에 따라 달라질 수 있습니다.

 속성 및 이벤트는 에 의해 `EnumMembers`지어지지 않습니다. 열거형으로 열거하려면 [EnumProperties](imetadataimport-enumproperties-method.md) 또는 [EnumEvents를](imetadataimport-enumevents-method.md)사용합니다.
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** 코르h  
  
 **라이브러리:** MsCorEE.dll의 리소스로 포함  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [IMetaDataImport 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
