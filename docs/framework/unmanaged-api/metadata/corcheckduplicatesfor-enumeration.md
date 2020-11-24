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
ms.openlocfilehash: 4acdfd6df410f229a002fa191ef24766748a1262
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95672359"
---
# <a name="corcheckduplicatesfor-enumeration"></a>CorCheckDuplicatesFor 열거형

중복을 확인할 메타 데이터 토큰을 지정 합니다.  
  
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
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|`MDDupAll`|모든 메타 데이터 토큰에 중복 항목이 있는지 확인 합니다.|  
|`MDDupENC`|사용되지 않습니다.|  
|`MDNoDupChecks`|메타 데이터 토큰에서 중복 항목을 확인 하지 않습니다.|  
|`MDDupTypeDef`|토큰의 중복을 확인 `mdTypeDef` 합니다.|  
|`MDDupInterfaceImpl`|토큰의 중복을 확인 `mdInterfaceImpl` 합니다.|  
|`MDDupMethodDef`|토큰의 중복을 확인 `mdMethodDef` 합니다.|  
|`MDDupTypeRef`|토큰의 중복을 확인 `mdTypeRef` 합니다.|  
|`MDDupMemberRef`|토큰의 중복을 확인 `mdMemberRef` 합니다.|  
|`MDDupCustomAttribute`|토큰의 중복을 확인 `mdCustomAttribute` 합니다.|  
|`MDDupParamDef`|토큰의 중복을 확인 `mdParamDef` 합니다.|  
|`MDDupPermission`|토큰의 중복을 확인 `mdPermission` 합니다.|  
|`MDDupProperty`|토큰의 중복을 확인 `mdProperty` 합니다.|  
|`MDDupEvent`|토큰의 중복을 확인 `mdEvent` 합니다.|  
|`MDDupFieldDef`|토큰의 중복을 확인 `mdFieldDef` 합니다.|  
|`MDDupSignature`|토큰의 중복을 확인 `mdSignature` 합니다.|  
|`MDDupModuleRef`|토큰의 중복을 확인 `mdModuleRef` 합니다.|  
|`MDDupTypeSpec`|토큰의 중복을 확인 `mdTypeSpec` 합니다.|  
|`MDDupImplMap`|토큰의 중복을 확인 `mdImplMap` 합니다.|  
|`MDDupAssemblyRef`|토큰의 중복을 확인 `mdAssemblyRef` 합니다.|  
|`MDDupFile`|토큰의 중복을 확인 `mdFile` 합니다.|  
|`MDDupExportedType`|토큰의 중복을 확인 `mdExportedType` 합니다.|  
|`MDDupManifestResource`|토큰의 중복을 확인 `mdManifestResource` 합니다.|  
|`MDDupGenericParam`|토큰의 중복을 확인 `mdGenericParam` 합니다.|  
|`MDDupMethodSpec`|토큰의 중복을 확인 `mdMethodSpec` 합니다.|  
|`MDDupGenericParamConstraint`|토큰의 중복을 확인 `mdGenericParamConstraint` 합니다.|  
|`MDDupAssembly`|토큰의 중복을 확인 `mdAssembly` 합니다.|  
|`MDDupDefault`|`mdMemberRef`,, `mdTypeRef` `mdSignature` , 및 토큰이 중복 되는지 확인 `mdTypeSpec` `mdMethodSpec` 합니다.|  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorHdr .h  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참조

- [메타데이터 열거형](metadata-enumerations.md)
