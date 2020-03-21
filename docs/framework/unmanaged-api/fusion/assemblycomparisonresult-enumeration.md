---
title: AssemblyComparisonResult 열거형
ms.date: 03/30/2017
api_name:
- AssemblyComparisonResult
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- AssemblyComparisonResult
helpviewer_keywords:
- AssemblyComparisonResult enumeration [.NET Framework fusion]
ms.assetid: bd042f89-10b1-40ca-946e-46da082f5263
topic_type:
- apiref
ms.openlocfilehash: e3cdb648397ca4f4aa2326e4f2349a5a14c3edcc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178299"
---
# <a name="assemblycomparisonresult-enumeration"></a>AssemblyComparisonResult 열거형
[비교어셈블리 ID](compareassemblyidentity-function.md) 함수에 의해 결정된 대로 두 어셈블리 ID의 동등성을 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
typedef enum _tagAssemblyComparisonResult {  
    ACR_Unknown,
    ACR_EquivalentFullMatch,  
    ACR_EquivalentWeakNamed,  
    ACR_EquivalentFXUnified,  
    ACR_EquivalentUnified,
    ACR_NonEquivalentVersion,  
    ACR_NonEquivalent,
    ACR_EquivalentPartialMatch,  
    ACR_EquivalentPartialWeakNamed,
    ACR_EquivalentPartialUnified,  
    ACR_EquivalentPartialFXUnified,  
    ACR_NonEquivalentPartialVersion
} AssemblyComparisonResult;  
```  
  
## <a name="members"></a>구성원  
  
|멤버 이름|Description|  
|-----------------|-----------------|  
|`ACR_EquivalentFullMatch`|비교의 모든 어셈블리 필드가 일치음을 나타냅니다.|  
|`ACR_EquivalentFXUnified`|어셈블리는 .NET Framework 버전 2.0에서 어셈블리 버전 번호의 공통 언어 런타임 버전(CLR) 통합을 기반으로 동등한 것으로 간주됩니다.|  
|`ACR_EquivalentPartialFXUnified`|.NET Framework 2.0에서 어셈블리 버전 번호의 CLR 통합을 기반으로 어셈블리의 부분 일치를 나타냅니다.|  
|`ACR_EquivalentPartialMatch`|어셈블리의 부분 일치를 나타냅니다.|  
|`ACR_EquivalentPartialUnified`|버전 번호의 레거시 통합을 기반으로 어셈블리의 부분 일치를 나타냅니다.|  
|`ACR_EquivalentPartialWeakNamed`|명명된 어셈블리의 부분 일치를 나타냅니다.|  
|`ACR_EquivalentUnified`|어셈블리는 .NET Framework의 레거시 버전에서 버전 번호의 CLR 통합에 따라 동등한 것으로 간주됩니다.|  
|`ACR_EquivalentWeakNamed`|버전 번호가 무시된 두 개의 단순히 명명된 어셈블리 간의 일치를 나타냅니다.|  
|`ACR_NonEquivalent`|두 어셈블리 간에 일치하는 집합이 발생하지 않은 것을 나타냅니다.|  
|`ACR_NonEquivalentPartialVersion`|두 어셈블리가 부분적으로만 일치하는 버전 번호를 제외하고 일치한다는 것을 나타냅니다.|  
|`ACR_NonEquivalentVersion`|일치하지 않는 버전 번호를 제외하고 두 어셈블리가 일치한다는 것을 나타냅니다.|  
|`ACR_Unknown`|비동등성에 대한 이유가 알려져 있지 않음을 나타냅니다.|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** 퓨전.h  
  
 **라이브러리:** MsCorEE.dll의 리소스로 포함  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [CompareAssemblyIdentity 함수](compareassemblyidentity-function.md)
- [Fusion 열거형](fusion-enumerations.md)
