---
title: CorAssemblyFlags 열거형
ms.date: 03/30/2017
api_name:
- CorAssemblyFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorAssemblyFlags
helpviewer_keywords:
- CorAssemblyFlags enumeration [.NET Framework metadata]
ms.assetid: bb8db3b6-d81d-49fc-b74c-dbc908a9eab9
topic_type:
- apiref
ms.openlocfilehash: 615c4ac95ab777e8081e630cafb6671e64dea78a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95718997"
---
# <a name="corassemblyflags-enumeration"></a>CorAssemblyFlags 열거형

어셈블리 컴파일에 적용되는 메타데이터를 설명하는 값을 포함합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
typedef enum CorAssemblyFlags {  
  
    afPublicKey             =   0x0001,  
    afPA_None               =   0x0000,  
    afPA_MSIL               =   0x0010,  
    afPA_x86                =   0x0020,  
    afPA_IA64               =   0x0030,  
    afPA_AMD64              =   0x0040,  
    afPA_ARM                =   0x0050,  
    afPA_NoPlatform         =   0x0070,  
    afPA_Specified          =   0x0080,  
    afPA_Mask               =   0x0070,  
    afPA_FullMask           =   0x00F0,  
    afPA_Shift              =   0x0004,  
  
    afEnableJITcompileTracking  =   0x8000,  
    afDisableJITcompileOptimizer=   0x4000,  
  
    afRetargetable          =   0x0100,  
    afContentType_Default        =   0x0000,  
    afContentType_WindowsRuntime =   0x0200,  
    afContentType_Mask           =   0x0E00,  
  
} CorAssemblyFlags;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|`afPublicKey`|어셈블리 참조에 해시 되지 않은 전체 공개 키가 포함 되어 있음을 나타냅니다.|  
|`afPA_None`|프로세서 아키텍처가 지정 되지 않았음을 나타냅니다.|  
|`afPA_MSIL`|프로세서 아키텍처가 중립 상태임을 나타냅니다 (PE32).|  
|`afPA_x86`|프로세서 아키텍처가 x86 (PE32) 임을 나타냅니다.|  
|`afPA_IA64`|프로세서 아키텍처가 Itanium (PE32 +) 임을 나타냅니다.|  
|`afPA_AMD64`|프로세서 아키텍처가 AMD X64 (PE32 +) 임을 나타냅니다.|  
|`afPA_ARM`|프로세서 아키텍처가 ARM (PE32) 임을 나타냅니다.|  
|`afPA_NoPlatform`|어셈블리가 참조 어셈블리 임을 나타냅니다. 즉, 모든 아키텍처에 적용 되지만 모든 아키텍처에서 실행할 수는 없습니다. 따라서 플래그는와 동일 합니다 `afPA_Mask` .|  
|`afPA_Specified`|프로세서 아키텍처 플래그를 레코드로 전파 해야 함을 나타냅니다 `AssemblyRef` .|  
|`afPA_Mask`|프로세서 아키텍처를 설명 하는 마스크입니다.|  
|`afPA_FullMask`|프로세서 아키텍처 설명을 포함 하도록 지정 합니다.|  
|`afPA_Shift`|인덱스에 대 한 프로세서 아키텍처 플래그의 이동 횟수를 나타냅니다.|  
|`afEnableJITcompileTracking`|의에서 해당 하는 값을 나타냅니다 <xref:System.Diagnostics.DebuggableAttribute.DebuggingModes> <xref:System.Diagnostics.DebuggableAttribute> .|  
|`afDisableJITcompileOptimizer`|의에서 해당 하는 값을 나타냅니다 <xref:System.Diagnostics.DebuggableAttribute.DebuggingModes> <xref:System.Diagnostics.DebuggableAttribute> .|  
|`afRetargetable`|런타임에 다른 게시자의 어셈블리에 어셈블리의 대상을 지정할 수 있음을 나타냅니다.|  
|`afContentType_Mask`|내용 유형을 설명 하는 마스크입니다.|  
|`afContentType_Default`|기본 콘텐츠 형식을 나타냅니다.|  
|`afContentType_WindowsRuntime`|Windows 런타임 내용 유형을 나타냅니다.|  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorHdr .h  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참조

- [메타데이터 열거형](metadata-enumerations.md)
