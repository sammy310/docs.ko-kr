---
description: '다음에 대 한 자세한 정보: AssemblyFlags 열거'
title: AssemblyFlags 열거형
ms.date: 03/30/2017
api_name:
- AssemblyFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- AssemblyFlags
helpviewer_keywords:
- AssemblyFlags enumeration [.NET Framework metadata]
ms.assetid: 40f9bd9e-16ec-447e-81b0-168c875e9866
topic_type:
- apiref
ms.openlocfilehash: 17cc0dec305c21d21693fe8f4f8d82c039f73278
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99679006"
---
# <a name="assemblyflags-enumeration"></a>AssemblyFlags 열거형

어셈블리의 런타임 기능을 설명 하는 값을 포함 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
typedef enum {  
    afImplicitExportedTypes = 0x0001,  
    afImplicitResources = 0x0002,  
    afNonSideBySideAppDomain = 0x0010,  
    afNonSideBySideProcess = 0x0020,  
    afNonSideBySideMachine = 0x0030  
} AssemblyFlags;  
```  
  
## <a name="members"></a>구성원  
  
|멤버|설명|  
|------------|-----------------|  
|`afImplicitExportedTypes`|내보낸 형식 정의가 어셈블리를 구성 하는 파일 내에서 암시적 임을 지정 합니다. .NET Framework 버전 1.0 및 1.1에서는이 값이 항상 설정 된 것으로 가정 합니다.|  
|`afImplicitResources`|어셈블리를 구성 하는 파일 내에서 리소스 정의가 암시적 임을 지정 합니다. .NET Framework 1.0 및 1.1에서는이 값이 항상 설정 된 것으로 가정 합니다.|  
|`afNonSideBySideAppDomain`|동일한 응용 프로그램 도메인에서 실행 중인 경우 어셈블리를 다른 버전과 함께 실행할 수 없도록 지정 합니다.|  
|`afNonSideBySideProcess`|동일한 프로세스에서 실행 되는 어셈블리를 다른 버전과 함께 실행할 수 없도록 지정 합니다.|  
|`afNonSideBySideMachine`|동일한 컴퓨터에서 실행 중인 어셈블리를 다른 버전과 함께 실행할 수 없도록 지정 합니다.|  
  
## <a name="remarks"></a>설명  

 0x0010 및 0x0070 (포함) 사이의 값은 참조 된 어셈블리의 병렬 호환성 기능을 설명 하는 데 사용 됩니다. 이러한 값이 설정 되어 있지 않으면 어셈블리는 side-by-side 호환으로 간주 됩니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Mscoree.dll  
  
 **라이브러리:** MsCorEE.dll의 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [메타데이터 열거형](metadata-enumerations.md)
- [IMetaDataAssemblyEmit 인터페이스](imetadataassemblyemit-interface.md)
