---
title: CorMethodAttr 열거형
ms.date: 03/30/2017
api_name:
- CorMethodAttr
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorMethodAttr
helpviewer_keywords:
- CorMethodAttr enumeration [.NET Framework metadata]
ms.assetid: 4e0c3521-e54d-43c1-9857-cc76b49b8ffc
topic_type:
- apiref
ms.openlocfilehash: 6c3e721c24da217eaf2e8857377359e1c51b7b59
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95677026"
---
# <a name="cormethodattr-enumeration"></a>CorMethodAttr 열거형

메서드의 기능을 설명 하는 값을 포함 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
typedef enum CorMethodAttr {  
  
    mdMemberAccessMask          =   0x0007,  
    mdPrivateScope              =   0x0000,  
    mdPrivate                   =   0x0001,  
    mdFamANDAssem               =   0x0002,  
    mdAssem                     =   0x0003,  
    mdFamily                    =   0x0004,  
    mdFamORAssem                =   0x0005,  
    mdPublic                    =   0x0006,  
  
    mdStatic                    =   0x0010,  
    mdFinal                     =   0x0020,  
    mdVirtual                   =   0x0040,  
    mdHideBySig                 =   0x0080,  
  
    mdVtableLayoutMask          =   0x0100,  
    mdReuseSlot                 =   0x0000,  
    mdNewSlot                   =   0x0100,  
  
    mdCheckAccessOnOverride     =   0x0200,  
    mdAbstract                  =   0x0400,  
    mdSpecialName               =   0x0800,  
  
    mdPinvokeImpl               =   0x2000,  
    mdUnmanagedExport           =   0x0008,  
  
    mdReservedMask              =   0xd000,  
    mdRTSpecialName             =   0x1000,  
    mdHasSecurity               =   0x4000,  
    mdRequireSecObject          =   0x8000,  
  
} CorMethodAttr;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|`mdMemberAccessMask`|멤버 액세스를 지정 합니다.|  
|`mdPrivateScope`|멤버를 참조할 수 없도록 지정 합니다.|  
|`mdPrivate`|부모 형식만 멤버에 액세스할 수 있도록 지정 합니다.|  
|`mdFamANDAssem`|이 어셈블리의 하위 형식에서 멤버에 액세스할 수 있도록 지정 합니다.|  
|`mdAssem`|멤버가 어셈블리의 모든 사용자에 의해 accessibly 지정 합니다.|  
|`mdFamily`|형식 및 하위 형식 에서만 멤버에 액세스할 수 있도록 지정 합니다.|  
|`mdFamORAssem`|파생 클래스와 해당 어셈블리의 다른 형식에서 멤버에 액세스할 수 있도록 지정 합니다.|  
|`mdPublic`|범위에 대 한 액세스 권한이 있는 모든 형식에서 멤버에 액세스할 수 있도록 지정 합니다.|  
|`mdStatic`|멤버가 인스턴스의 멤버가 아니라 형식의 일부로 정의 되도록 지정 합니다.|  
|`mdFinal`|메서드를 재정의할 수 없도록 지정 합니다.|  
|`mdVirtual`|메서드를 재정의할 수 있도록 지정 합니다.|  
|`mdHideBySig`|메서드가 이름 뿐만 아니라 이름 및 시그니처로 숨기도록 지정 합니다.|  
|`mdVtableLayoutMask`|가상 테이블 레이아웃을 지정 합니다.|  
|`mdReuseSlot`|가상 테이블에서이 메서드에 사용 되는 슬롯을 다시 사용 하도록 지정 합니다. 이것이 기본값입니다.|  
|`mdNewSlot`|메서드가 항상 가상 테이블에 새 슬롯을 가져옵니다.|  
|`mdCheckAccessOnOverride`|표시 되는 형식과 동일한 형식으로 메서드를 재정의할 수 있도록 지정 합니다.|  
|`mdAbstract`|메서드가 구현 되지 않도록 지정 합니다.|  
|`mdSpecialName`|메서드를 특수 하 게 지정 하 고 해당 이름에서 방법을 설명 합니다.|  
|`mdPinvokeImpl`|PInvoke를 사용 하 여 메서드 구현을 전달 하도록 지정 합니다.|  
|`mdUnmanagedExport`|메서드를 비관리 코드로 내보낸 관리 되는 메서드로 지정 합니다.|  
|`mdReservedMask`|공용 언어 런타임에서 내부용으로 사용 하도록 예약 되어 있습니다.|  
|`mdRTSpecialName`|공용 언어 런타임에서 메서드 이름의 인코딩을 확인 하도록 지정 합니다.|  
|`mdHasSecurity`|메서드에 연결 된 보안이 있음을 지정 합니다.|  
|`mdRequireSecObject`|메서드가 보안 코드를 포함 하는 다른 메서드를 호출 하도록 지정 합니다.|  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorHdr .h  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참조

- [메타데이터 열거형](metadata-enumerations.md)
