---
title: OSINFO 구조체
ms.date: 03/30/2017
api_name:
- OSINFO
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- OSINFO
helpviewer_keywords:
- OSINFO structure [.NET Framework metadata]
ms.assetid: fac7b480-7adb-4450-a5e9-690fed81ffae
topic_type:
- apiref
ms.openlocfilehash: 49e29cc0367d5162dffcd641b163fd7b9a56ffd0
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95672892"
---
# <a name="osinfo-structure"></a>OSINFO 구조체

어셈블리 또는 모듈의 운영 체제에 대 한 세부 정보를 포함 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
typedef struct {  
    DWORD   dwOSPlatformId;  
    DWORD   dwOSMajorVersion;
    DWORD   dwOSMinorVersion;
} OSINFO;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|`dwOSPlatformId`|Microsoft Windows 플랫폼 함수에 의해 정의 된 식별자 값 중 하나입니다 `GetVersionEx` . 지원되는 값은 다음과 같습니다.<br /><br /> -VER_PLATFORM_WIN32s 또는 경우 Microsoft Windows 3.1을 지정 합니다.<br />-VER_PLATFORM_WIN32_WINDOWS 또는 0x0001에서 Windows 95, Windows 98 또는 운영 체제를 지정 합니다.<br />-VER_PLATFORM_WIN32_NT 또는 0x0002, Windows NT 또는 운영 체제를 지정 합니다.|  
|`dwOSMajorVersion`|운영 체제 주 버전 또는 모든 버전을 나타내는 NULL 값입니다.|  
|`dwOSMinorVersion`|운영 체제 부 버전 또는 모든 버전을 나타내는 NULL 값입니다.|  
  
## <a name="remarks"></a>설명  

 `OSINFO` 는 `OSVERSIONINFOEX` Microsoft Windows 플랫폼 함수 호출에 사용 되는 구조를 기반으로 `GetVersionEx` 합니다. 이 구조는 ASSEMBLYMETADATA 구조에서 해당 운영 체제 지원을 나타내는 데 사용 됩니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Cor  
  
 **라이브러리:** MsCorEE.dll에서 리소스로 사용 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참조

- [메타데이터 구조체](metadata-structures.md)
- [IMetaDataAssemblyEmit 인터페이스](imetadataassemblyemit-interface.md)
