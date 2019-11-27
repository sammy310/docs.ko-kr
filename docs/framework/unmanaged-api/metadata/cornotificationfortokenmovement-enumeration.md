---
title: CorNotificationForTokenMovement 열거형
ms.date: 03/30/2017
api_name:
- CorNotificationForTokenMovement
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorNotificationForTokenMovement
helpviewer_keywords:
- CorNotificationForTokenMovement enumeration [.NET Framework metadata]
ms.assetid: 1edd1670-976a-4fc8-bef7-7c41e60ad989
topic_type:
- apiref
ms.openlocfilehash: 411fad0accb59431f776c5bd66e8bd3027ddd907
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74450152"
---
# <a name="cornotificationfortokenmovement-enumeration"></a>CorNotificationForTokenMovement 열거형
토큰 다시 매핑을 수행 하는 경우 메타 데이터 API 클라이언트에 전송 되는 알림을 지정 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
typedef enum CorNotificationForTokenMovement {  
  
    MDNotifyDefault             = 0x0000000f,  
    MDNotifyAll                 = 0xffffffff,  
    MDNotifyNone                = 0x00000000,  
    MDNotifyMethodDef           = 0x00000001,  
    MDNotifyMemberRef           = 0x00000002,  
    MDNotifyFieldDef            = 0x00000004,  
    MDNotifyTypeRef             = 0x00000008,  
  
    MDNotifyTypeDef             = 0x00000010,  
    MDNotifyParamDef            = 0x00000020,  
    MDNotifyInterfaceImpl       = 0x00000040,  
    MDNotifyProperty            = 0x00000080,  
    MDNotifyEvent               = 0x00000100,  
    MDNotifySignature           = 0x00000200,  
    MDNotifyTypeSpec            = 0x00000400,  
    MDNotifyCustomAttribute     = 0x00000800,  
    MDNotifySecurityValue       = 0x00001000,  
    MDNotifyPermission          = 0x00002000,  
    MDNotifyModuleRef           = 0x00004000,  
  
    MDNotifyNameSpace           = 0x00008000,  
  
    MDNotifyAssemblyRef         = 0x01000000,  
    MDNotifyFile                = 0x02000000,  
    MDNotifyExportedType        = 0x04000000,  
    MDNotifyResource            = 0x08000000  
  
} CorNotificationForTokenMovement;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|`MDNotifyDefault`|`mdTypeRef`, `mdMethodDef`, `mdMemberRef`또는 `mdFieldDef` 토큰이 이동할 때 알립니다.|  
|`MDNotifyAll`|토큰이 이동 하면 알립니다.|  
|`MDNotifyNone`|토큰이 이동할 때 알리지 않습니다.|  
|`MDNotifyMethodDef`|`mdMethodDef` 토큰이 이동할 때 알립니다.|  
|`MDNotifyMemberRef`|`mdMemberRef` 토큰이 이동할 때 알립니다.|  
|`MDNotifyFieldDef`|`mdFieldDef` 토큰이 이동할 때 알립니다.|  
|`MDNotifyTypeRef`|`mdTypeRef` 토큰이 이동할 때 알립니다.|  
|`MDNotifyTypeDef`|`mdTypeDef` 토큰이 이동할 때 알립니다.|  
|`MDNotifyParamDef`|`mdParamDef` 토큰이 이동할 때 알립니다.|  
|`MDNotifyInterfaceImpl`|`mdInterfaceImpl` 토큰이 이동할 때 알립니다.|  
|`MDNotifyProperty`|`mdProperty` 토큰이 이동할 때 알립니다.|  
|`MDNotifyEvent`|`mdEvent` 토큰이 이동할 때 알립니다.|  
|`MDNotifySignature`|`mdSignature` 토큰이 이동할 때 알립니다.|  
|`MDNotifyTypeSpec`|`mdTypeSpec` 토큰이 이동할 때 알립니다.|  
|`MDNotifyCustomAttribute`|`mdCustomAttribute` 토큰이 이동할 때 알립니다.|  
|`MDNotifySecurityValue`|`mdSecurityValue` 토큰이 이동할 때 알립니다.|  
|`MDNotifyPermission`|`mdPermission` 토큰이 이동할 때 알립니다.|  
|`MDNotifyModuleRef`|`mdModuleRef` 토큰이 이동할 때 알립니다.|  
|`MDNotifyNameSpace`|`mdNameSpace` 토큰이 이동할 때 알립니다.|  
|`MDNotifyAssemblyRef`|`mdAssemblyRef` 토큰이 이동할 때 알립니다.|  
|`MDNotifyFile`|`mdFile` 토큰이 이동할 때 알립니다.|  
|`MDNotifyExportedType`|`mdExportedType` 토큰이 이동할 때 알립니다.|  
|`MDNotifyResource`|`mdManifestResource` 토큰이 이동할 때 알립니다.|  
  
## <a name="remarks"></a>주의  
 토큰은 메타 데이터 병합 중에 다시 매핑 (즉, 이동) 될 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorHdr .h  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [메타데이터 열거형](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
