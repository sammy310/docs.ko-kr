---
title: IMetaDataImport::EnumMemberRefs 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumMemberRefs
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumMemberRefs
helpviewer_keywords:
- EnumMemberRefs method [.NET Framework metadata]
- IMetaDataImport::EnumMemberRefs method [.NET Framework metadata]
ms.assetid: e97c97a6-6e4f-41f5-9af1-9b3cf3bdbd6b
topic_type:
- apiref
ms.openlocfilehash: b8a65b0748fec0e474d8b3b5dc03473fbd716108
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177328"
---
# <a name="imetadataimportenummemberrefs-method"></a>IMetaDataImport::EnumMemberRefs 메서드
지정한 형식의 멤버를 나타내는 MemberRef 토큰을 열거합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT EnumMemberRefs (  
   [in, out] HCORENUM    *phEnum,
   [in]   mdToken        tkParent,
   [out]  mdMemberRef    rMemberRefs[],
   [in]   ULONG          cMax,
   [out]  ULONG          *pcTokens  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `phEnum`  
 【인, 아웃】 열거형에 대한 포인터입니다.  
  
 `tkParent`  
 【인】 멤버를 개명할 형식에 대한 TypeDef, TypeRef, MethodDef 또는 ModuleRef 토큰입니다.  
  
 `rMemberRefs`  
 【아웃】 MemberRef 토큰을 저장하는 데 사용되는 배열입니다.  
  
 `cMax`  
 [in] `rMemberRefs` 배열의 최대 크기입니다.  
  
 `pcTokens`  
 【아웃】 에서 반환된 MemberRef 토큰의 `rMemberRefs`실제 수입니다.  
  
## <a name="return-value"></a>Return Value  
  
|HRESULT|Description|  
|-------------|-----------------|  
|`S_OK`|`EnumMemberRefs`성공적으로 반환됩니다.|  
|`S_FALSE`|등록할 MemberRef 토큰이 없습니다. 이 경우 `pcTokens` 0입니다.|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** 코르h  
  
 **라이브러리:** MsCorEE.dll의 리소스로 포함  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [IMetaDataImport 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
