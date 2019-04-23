---
title: ASSEMBLY_INFO 구조체
ms.date: 03/30/2017
api_name:
- ASSEMBLY_INFO
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- ASSEMBLY_INFO
helpviewer_keywords:
- ASSEMBLY_INFO structure [.NET Framework fusion]
ms.assetid: b3cbb47c-457f-4083-8895-49562ca99ab8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bae19ec18c54eccc7aa54d2d3a006f36ba8ab762
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59110879"
---
# <a name="assemblyinfo-structure"></a>ASSEMBLY_INFO 구조체
전역 어셈블리 캐시에 등록 된 어셈블리에 대 한 정보를 포함 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
typedef struct _ASSEMBLY_INFO {  
    ULONG           cbAssemblyInfo;  
    DWORD           dwAssemblyFlags;  
    ULARGE_INTEGER  uliAssemblySizeInKB;  
    LPWSTR          pszCurrentAssemblyPathBuf;  
    ULONG           cchBuf;  
} ASSEMBLY_INFO;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|`cbAssemblyInfo`|구조체의 바이트 크기입니다. 이 필드는 향후 확장성을 위해 예약 되어 있습니다.|  
|`dwAssemblyFlags`|어셈블리에 대 한 설치 세부 정보를 나타내는 플래그입니다. 다음 값이 지원 됩니다.<br /><br /> 어셈블리가 설치 되어 있는지 여부를 나타내는-ASSEMBLYINFO_FLAG_INSTALLED 값입니다. .NET Framework의 현재 버전을 항상 설정 `dwAssemblyFlags` 이 값으로.<br />어셈블리에 상주 하는 페이로드를 나타내는-ASSEMBLYINFO_FLAG_PAYLOADRESIDENT 값입니다. .NET Framework의 현재 버전을 설정 하지 `dwAssemblyFlags` 이 값으로.|  
|`uliAssemblySizeInKB`|(킬로바이트) 어셈블리에 있는 파일의 총 크기입니다.|  
|`pszCurrentAssemblyPathBuf`|매니페스트 파일에 대 한 현재 경로 포함 하는 문자열 버퍼에 대 한 포인터입니다. 경로 null 문자로 끝나야 합니다.|  
|`cchBuf`|Null 종결자를 포함 하 여 와이드 문자 수는 `pszCurrentAssemblyPathBuf` 포함 되어 있습니다.|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** Fusion.h  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고자료

- [Fusion 구조체](../../../../docs/framework/unmanaged-api/fusion/fusion-structures.md)
- [전역 어셈블리 캐시](../../../../docs/framework/app-domains/gac.md)
