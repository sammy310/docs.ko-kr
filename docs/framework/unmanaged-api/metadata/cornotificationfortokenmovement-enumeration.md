---
description: '자세한 정보: CorNotificationForTokenMovement 열거형'
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
ms.openlocfilehash: 1975598b756499c9c0b017bf7eba9a134af5185f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99784316"
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
  
## <a name="members"></a>구성원  
  
|멤버|설명|  
|------------|-----------------|  
|`MDNotifyDefault`|`mdTypeRef`, `mdMethodDef` , `mdMemberRef` 또는 `mdFieldDef` 토큰이 이동할 때 알립니다.|  
|`MDNotifyAll`|토큰이 이동 하면 알립니다.|  
|`MDNotifyNone`|토큰이 이동할 때 알리지 않습니다.|  
|`MDNotifyMethodDef`|토큰을 이동할 때 알립니다 `mdMethodDef` .|  
|`MDNotifyMemberRef`|토큰을 이동할 때 알립니다 `mdMemberRef` .|  
|`MDNotifyFieldDef`|토큰을 이동할 때 알립니다 `mdFieldDef` .|  
|`MDNotifyTypeRef`|토큰을 이동할 때 알립니다 `mdTypeRef` .|  
|`MDNotifyTypeDef`|토큰을 이동할 때 알립니다 `mdTypeDef` .|  
|`MDNotifyParamDef`|토큰을 이동할 때 알립니다 `mdParamDef` .|  
|`MDNotifyInterfaceImpl`|토큰을 이동할 때 알립니다 `mdInterfaceImpl` .|  
|`MDNotifyProperty`|토큰을 이동할 때 알립니다 `mdProperty` .|  
|`MDNotifyEvent`|토큰을 이동할 때 알립니다 `mdEvent` .|  
|`MDNotifySignature`|토큰을 이동할 때 알립니다 `mdSignature` .|  
|`MDNotifyTypeSpec`|토큰을 이동할 때 알립니다 `mdTypeSpec` .|  
|`MDNotifyCustomAttribute`|토큰을 이동할 때 알립니다 `mdCustomAttribute` .|  
|`MDNotifySecurityValue`|토큰을 이동할 때 알립니다 `mdSecurityValue` .|  
|`MDNotifyPermission`|토큰을 이동할 때 알립니다 `mdPermission` .|  
|`MDNotifyModuleRef`|토큰을 이동할 때 알립니다 `mdModuleRef` .|  
|`MDNotifyNameSpace`|토큰을 이동할 때 알립니다 `mdNameSpace` .|  
|`MDNotifyAssemblyRef`|토큰을 이동할 때 알립니다 `mdAssemblyRef` .|  
|`MDNotifyFile`|토큰을 이동할 때 알립니다 `mdFile` .|  
|`MDNotifyExportedType`|토큰을 이동할 때 알립니다 `mdExportedType` .|  
|`MDNotifyResource`|토큰을 이동할 때 알립니다 `mdManifestResource` .|  
  
## <a name="remarks"></a>설명  

 토큰은 메타 데이터 병합 중에 다시 매핑 (즉, 이동) 될 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorHdr .h  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [메타데이터 열거형](metadata-enumerations.md)
