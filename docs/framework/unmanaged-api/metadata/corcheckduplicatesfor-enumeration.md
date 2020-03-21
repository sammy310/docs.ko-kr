---
title: CorCheckDuplicatesFor 열거형
ms.date: 03/30/2017
api_name:
- CorCheckDuplicatesFor
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorCheckDuplicatesFor
helpviewer_keywords:
- CorCheckDuplicatesFor enumeration [.NET Framework metadata]
ms.assetid: d8ec8d3c-70f7-4cc6-9957-68068fd8f49c
topic_type:
- apiref
ms.openlocfilehash: 04dc12ab4d7d178ebf1575a3260f9f4981972782
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176190"
---
# <a name="corcheckduplicatesfor-enumeration"></a>CorCheckDuplicatesFor 열거형
중복을 검사할 메타데이터 토큰을 지정합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
typedef enum CorCheckDuplicatesFor {  
  
    MDDupAll                    = 0xffffffff,  
    MDDupENC                    = MDDupAll,  
    MDNoDupChecks               = 0x00000000,  
    MDDupTypeDef                = 0x00000001,  
    MDDupInterfaceImpl          = 0x00000002,  
    MDDupMethodDef              = 0x00000004,  
    MDDupTypeRef                = 0x00000008,  
    MDDupMemberRef              = 0x00000010,  
    MDDupCustomAttribute        = 0x00000020,  
    MDDupParamDef               = 0x00000040,  
    MDDupPermission             = 0x00000080,  
    MDDupProperty               = 0x00000100,  
    MDDupEvent                  = 0x00000200,  
    MDDupFieldDef               = 0x00000400,  
    MDDupSignature              = 0x00000800,  
    MDDupModuleRef              = 0x00001000,  
    MDDupTypeSpec               = 0x00002000,  
    MDDupImplMap                = 0x00004000,  
    MDDupAssemblyRef            = 0x00008000,  
    MDDupFile                   = 0x00010000,  
    MDDupExportedType           = 0x00020000,  
    MDDupManifestResource       = 0x00040000,  
    MDDupGenericParam           = 0x00080000,  
    MDDupMethodSpec             = 0x00100000,  
    MDDupGenericParamConstraint = 0x00200000,  
  
    MDDupAssembly               = 0x10000000,  
  
    MDDupDefault =
        MDNoDupChecks | MDDupTypeRef | MDDupMemberRef |
        MDDupSignature | MDDupTypeSpec | MDDupMethodSpec  
  
} CorCheckDuplicatesFor;  
```  
  
## <a name="members"></a>구성원  
  
|멤버|Description|  
|------------|-----------------|  
|`MDDupAll`|모든 메타데이터 토큰에 중복이 있는지 확인합니다.|  
|`MDDupENC`|사용되지 않습니다.|  
|`MDNoDupChecks`|메타데이터 토큰에 중복이 있는지 확인하지 마십시오.|  
|`MDDupTypeDef`|토큰의 `mdTypeDef` 중복을 확인합니다.|  
|`MDDupInterfaceImpl`|토큰의 `mdInterfaceImpl` 중복을 확인합니다.|  
|`MDDupMethodDef`|토큰의 `mdMethodDef` 중복을 확인합니다.|  
|`MDDupTypeRef`|토큰의 `mdTypeRef` 중복을 확인합니다.|  
|`MDDupMemberRef`|토큰의 `mdMemberRef` 중복을 확인합니다.|  
|`MDDupCustomAttribute`|토큰의 `mdCustomAttribute` 중복을 확인합니다.|  
|`MDDupParamDef`|토큰의 `mdParamDef` 중복을 확인합니다.|  
|`MDDupPermission`|토큰의 `mdPermission` 중복을 확인합니다.|  
|`MDDupProperty`|토큰의 `mdProperty` 중복을 확인합니다.|  
|`MDDupEvent`|토큰의 `mdEvent` 중복을 확인합니다.|  
|`MDDupFieldDef`|토큰의 `mdFieldDef` 중복을 확인합니다.|  
|`MDDupSignature`|토큰의 `mdSignature` 중복을 확인합니다.|  
|`MDDupModuleRef`|토큰의 `mdModuleRef` 중복을 확인합니다.|  
|`MDDupTypeSpec`|토큰의 `mdTypeSpec` 중복을 확인합니다.|  
|`MDDupImplMap`|토큰의 `mdImplMap` 중복을 확인합니다.|  
|`MDDupAssemblyRef`|토큰의 `mdAssemblyRef` 중복을 확인합니다.|  
|`MDDupFile`|토큰의 `mdFile` 중복을 확인합니다.|  
|`MDDupExportedType`|토큰의 `mdExportedType` 중복을 확인합니다.|  
|`MDDupManifestResource`|토큰의 `mdManifestResource` 중복을 확인합니다.|  
|`MDDupGenericParam`|토큰의 `mdGenericParam` 중복을 확인합니다.|  
|`MDDupMethodSpec`|토큰의 `mdMethodSpec` 중복을 확인합니다.|  
|`MDDupGenericParamConstraint`|토큰의 `mdGenericParamConstraint` 중복을 확인합니다.|  
|`MDDupAssembly`|토큰의 `mdAssembly` 중복을 확인합니다.|  
|`MDDupDefault`|및 `mdMemberRef` `mdTypeRef` `mdMethodSpec` 토큰의 중복을 확인합니다. `mdSignature` `mdTypeSpec`|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** 코르Hdr.h  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [메타데이터 열거형](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
