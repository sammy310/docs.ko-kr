---
title: CorDeclSecurity 열거형
ms.date: 03/30/2017
api_name:
- CorDeclSecurity
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorDeclSecurity
helpviewer_keywords:
- CorDeclSecurity enumeration [.NET Framework metadata]
ms.assetid: 864f1267-d267-4696-8df7-1f83f8444d6f
topic_type:
- apiref
ms.openlocfilehash: 98183ed02f8821b7c40852de2d040775d30f2518
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74443737"
---
# <a name="cordeclsecurity-enumeration"></a>CorDeclSecurity 열거형
선언적 보안을 사용하여 수행할 수 있는 보안 작업을 지정합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
typedef enum CorDeclSecurity {  
  
    dclActionMask               =   0x001f,  
    dclActionNil                =   0x0000,  
    dclRequest                  =   0x0001,  
    dclDemand                   =   0x0002,  
    dclAssert                   =   0x0003,  
    dclDeny                     =   0x0004,  
    dclPermitOnly               =   0x0005,  
    dclLinktimeCheck            =   0x0006,  
    dclInheritanceCheck         =   0x0007,  
    dclRequestMinimum           =   0x0008,  
    dclRequestOptional          =   0x0009,  
    dclRequestRefuse            =   0x000a,  
    dclPrejitGrant              =   0x000b,  
    dclPrejitDenied             =   0x000c,  
    dclNonCasDemand             =   0x000d,  
    dclNonCasLinkDemand         =   0x000e,  
    dclNonCasInheritance        =   0x000f,  
    dclLinkDemandChoice         =   0x0010,  
    dclInheritanceDemandChoice  =   0x0011,  
    dclDemandChoice             =   0x0012,  
    dclMaximumValue             =   0x0012  
  
} CorDeclSecurity;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|`dclActionMask`|예약됨.|  
|`dclActionNil`|예약됨.|  
|`dclRequest`|예약됨.|  
|`dclDemand`|호출 스택의 상위에 있는 모든 호출자에게 현재 사용 권한 개체가 지정한 사용 권한이 부여되었어야 합니다.|  
|`dclAssert`|The calling code can access the resource identified by the current permission object, even if callers higher in the stack have not been granted permission to access the resource|  
|`dclDeny`|The ability to access the resource specified by the current permission object is denied to callers, even if they have been granted permission to access it.|  
|`dclPermitOnly`|코드에 다른 리소스에 액세스할 수 있는 권한이 부여되더라도 이 권한 개체가 지정한 리소스에만 액세스할 수 있습니다.|  
|`dclLinktimeCheck`|The immediate caller is required to have been granted the specified permission for a given period of time.|  
|`dclInheritanceCheck`|The derived class inheriting another class or overriding a method is required to have been granted the specified permission.|  
|`dclRequestMinimum`|The caller can request for the minimum permissions required for code to run. 이 작업은 어셈블리 범위 내에서만 사용할 수 있습니다.|  
|`dclRequestOptional`|The caller can request for additional permissions that are optional (not required to run). 이 요청은 특별히 요청되지 않은 다른 모든 사용 권한을 암시적으로 거부합니다. 이 작업은 어셈블리 범위 내에서만 사용할 수 있습니다.|  
|`dclRequestRefuse`|The caller's request for permissions that might be misused will not be granted. 이 작업은 어셈블리 범위 내에서만 사용할 수 있습니다.|  
|`dclPrejitGrant`|예약됨.|  
|`dclPrejitDenied`|예약됨.|  
|`dclNonCasDemand`|예약됨.|  
|`dclNonCasLinkDemand`|직접 실행 호출자에게 지정된 사용 권한이 부여되었어야 합니다.|  
|`dclNonCasInheritance`|예약됨.|  
|`dclLinkDemandChoice`|예약됨.|  
|`dclInheritanceDemandChoice`|예약됨.|  
|`dclDemandChoice`|예약됨.|  
|`dclMaximumValue`|예약됨.|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **Header:** CorHdr.h  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참조

- [메타데이터 열거형](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
