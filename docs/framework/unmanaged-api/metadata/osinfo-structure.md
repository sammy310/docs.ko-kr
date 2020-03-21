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
ms.openlocfilehash: 048fe687e4d979576896f5310bddc855b40bb695
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175228"
---
# <a name="osinfo-structure"></a>OSINFO 구조체
어셈블리 또는 모듈의 운영 체제에 대한 세부 정보를 포함합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
typedef struct {  
    DWORD   dwOSPlatformId;  
    DWORD   dwOSMajorVersion;
    DWORD   dwOSMinorVersion;
} OSINFO;  
```  
  
## <a name="members"></a>구성원  
  
|멤버|Description|  
|------------|-----------------|  
|`dwOSPlatformId`|Microsoft Windows 플랫폼 함수에 `GetVersionEx`의해 정의된 식별자 값 중 하나 . 다음 값이 지원 됩니다.<br /><br /> - VER_PLATFORM_WIN32s, 또는 0x0000, 마이크로 소프트 윈도우 3.1을 지정합니다.<br />- VER_PLATFORM_WIN32_WINDOWS, 또는 0x0001, 윈도우 95, 윈도우 98, 또는 운영 체제를 지정합니다.<br />- VER_PLATFORM_WIN32_NT, 또는 0x0002, 윈도우 NT 또는 운영 체제에서 후손 지정합니다.|  
|`dwOSMajorVersion`|운영 체제 주 버전 또는 NULL 값을 사용하여 모든 버전을 나타냅니다.|  
|`dwOSMinorVersion`|운영 체제 부 버전 또는 NULL 값으로 모든 버전을 나타냅니다.|  
  
## <a name="remarks"></a>설명  
 `OSINFO`Microsoft Windows `OSVERSIONINFOEX` 플랫폼 함수에 `GetVersionEx`대한 호출에 사용되는 구조를 기반으로 합니다. 이 구조는 ASSEMBLYMETADATA 구조에서 운영 체제 지원을 나타내는 데 사용됩니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** 코르h  
  
 **라이브러리:** MsCorEE.dll의 리소스로 사용  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [메타데이터 구조체](../../../../docs/framework/unmanaged-api/metadata/metadata-structures.md)
- [IMetaDataAssemblyEmit 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
