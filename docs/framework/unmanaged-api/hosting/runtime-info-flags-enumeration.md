---
description: '다음에 대 한 자세한 정보: 열거형 RUNTIME_INFO_FLAGS'
title: RUNTIME_INFO_FLAGS 열거형
ms.date: 03/30/2017
api_name:
- RUNTIME_INFO_FLAGS
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- RUNTIME_INFO_FLAGS
helpviewer_keywords:
- RUNTIME_INFO_FLAGS enumeration [.NET Framework hosting]
ms.assetid: adba37be-f775-4cdb-8919-5746ce694f33
topic_type:
- apiref
ms.openlocfilehash: 54ff62cdee6e940ae9ea8a2ce8ceff99f923d3f4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99679448"
---
# <a name="runtime_info_flags-enumeration"></a>RUNTIME_INFO_FLAGS 열거형

반환 해야 하는 CLR (공용 언어 런타임)에 대 한 정보를 나타내는 값을 포함 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
typedef enum {  
  
    RUNTIME_INFO_UPGRADE_VERSION             = 0x01,  
    RUNTIME_INFO_REQUEST_IA64                = 0x02,  
    RUNTIME_INFO_REQUEST_AMD64               = 0x04,  
    RUNTIME_INFO_REQUEST_X86                 = 0x08,  
    RUNTIME_INFO_DONT_RETURN_DIRECTORY       = 0x10,  
    RUNTIME_INFO_DONT_RETURN_VERSION         = 0x20,  
    RUNTIME_INFO_DONT_SHOW_ERROR_DIALOG      = 0x40,  
    RUNTIME_INFO_IGNORE_ERROR_MODE           = 0x1000  
  
} RUNTIME_INFO_FLAGS;  
```  
  
## <a name="members"></a>구성원  
  
|멤버|설명|  
|------------|-----------------|  
|`RUNTIME_INFO_DONT_RETURN_DIRECTORY`|디렉터리 정보를 포함 하지 않아야 함을 나타냅니다.|  
|`RUNTIME_INFO_DONT_RETURN_VERSION`|버전 정보를 포함 하지 않아야 함을 나타냅니다.|  
|`RUNTIME_INFO_DONT_SHOW_ERROR_DIALOG`|오류가 발생 한 경우 오류 대화 상자를 표시 하지 않음을 나타냅니다.|  
|`RUNTIME_INFO_IGNORE_ERROR_MODE`|SEM_FAILCRITICALERRORS 플래그를 사용 하 여 [SetErrorMode](/windows/win32/api/errhandlingapi/nf-errhandlingapi-seterrormode) 함수를 호출 하는 효과를 재정의 해야 함을 나타냅니다. 즉, 실패 시 설치 대화 상자가 표시 되지 않고 표시 되어야 합니다.|  
|`RUNTIME_INFO_REQUEST_AMD64`|AMD-64 호환 버전의 런타임 정보에 대 한 요청을 나타냅니다.|  
|`RUNTIME_INFO_REQUEST_IA64`|64 호환 버전의 런타임에 대 한 정보에 대 한 요청을 나타냅니다.|  
|`RUNTIME_INFO_REQUEST_X86`|X86 호환 버전의 런타임에 대 한 정보 요청을 나타냅니다.|  
|`RUNTIME_INFO_UPGRADE_VERSION`|버전 업그레이드 정보를 포함 해야 함을 나타냅니다.|  
  
## <a name="remarks"></a>설명  

 다음 플랫폼 아키텍처 플래그는 한 번에 하나만 지정할 수 있으며 결합할 수 없습니다.  
  
- RUNTIME_INFO_REQUEST_IA64  
  
- RUNTIME_INFO_REQUEST_AMD64  
  
- RUNTIME_INFO_REQUEST_X86  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Mscoree.dll  
  
 **라이브러리:** MSCorEE.dll  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [호스팅 열거형](hosting-enumerations.md)
