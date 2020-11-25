---
title: COR_NATIVE_LINK 구조체
ms.date: 03/30/2017
api_name:
- COR_NATIVE_LINK
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- COR_NATIVE_LINK
helpviewer_keywords:
- COR_NATIVE_LINK structure [.NET Framework metadata]
ms.assetid: 6ef78d3c-1c69-4141-b687-dcb065b7a74d
topic_type:
- apiref
ms.openlocfilehash: 15f573ebc07bcf08a1ab8f5a5bbb88e940c5c8dc
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724171"
---
# <a name="cor_native_link-structure"></a>COR_NATIVE_LINK 구조체

네이티브 코드를 연결하는 데 사용되는 정보를 포함합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
typedef struct
{  
    BYTE        m_linkType;  
    BYTE        m_flags;  
    mdMemberRef m_entryPoint;  
} COR_NATIVE_LINK;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|`m_linkType`|네이티브 코드에 연결 될 형식입니다. 이 값은 [CorNativeLinkType](cornativelinktype-enumeration.md) 값 중 하나입니다.|  
|`m_flags`|네이티브 코드를 연결할 때 링커에서 사용 하는 플래그입니다. 이 값은 [CorNativeLinkFlags](cornativelinkflags-enumeration.md) 값 중 하나입니다.|  
|`m_entryPoint`|진입점을 나타내는 MemberRef 메타 데이터 토큰입니다. 형식은 `lib:entrypoint`입니다.|  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Cor  
  
 **라이브러리:** MsCorEE.dll에서 리소스로 사용 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참조

- [메타데이터 구조체](metadata-structures.md)
- [CorNativeLinkType 열거형](cornativelinktype-enumeration.md)
- [CorNativeLinkFlags 열거형](cornativelinkflags-enumeration.md)
