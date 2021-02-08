---
description: '다음에 대 한 자세한 정보: 열거형 CLSID_RESOLUTION_FLAGS'
title: CLSID_RESOLUTION_FLAGS 열거형
ms.date: 03/30/2017
api_name:
- CLSID_RESOLUTION_FLAGS
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CLSID_RESOLUTION_FLAGS
helpviewer_keywords:
- CLSID_RESOLUTION_FLAGS enumeration [.NET Framework hosting]
ms.assetid: cd8b9879-962a-4811-aa46-2e2b6bae0d84
topic_type:
- apiref
ms.openlocfilehash: 54d334147e13217f8ce20dae1b139cdc6d11a3b8
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99799878"
---
# <a name="clsid_resolution_flags-enumeration"></a>CLSID_RESOLUTION_FLAGS 열거형

CLR (공용 언어 런타임)에서를 확인 하는 방법을 나타내는 값을 포함 합니다 `CLSID` .  
  
## <a name="syntax"></a>구문  
  
```cpp  
typedef enum {  
    CLSID_RESOLUTION_DEFAULT      = 0x0,  
    CLSID_RESOLUTION_REGISTERED   = 0x1  
} CLSID_RESOLUTION_FLAGS;  
```  
  
## <a name="members"></a>구성원  
  
|멤버|설명|  
|------------|-----------------|  
|`CLSID_RESOLUTION_DEFAULT`|기본 동작을 나타냅니다.|  
|`CLSID_RESOLUTION_REGISTERED`|런타임이 레지스트리를 검색 하 고 shim 정책을 적용 함을 나타냅니다.|  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Mscoree.dll  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [호스팅 열거형](hosting-enumerations.md)
