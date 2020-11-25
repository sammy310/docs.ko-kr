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
ms.openlocfilehash: cde25a9507006c89ef6490c13ae82033f04c2931
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731035"
---
# <a name="assemblycomparisonresult-enumeration"></a>AssemblyComparisonResult 열거형

[CompareAssemblyIdentity](compareassemblyidentity-function.md) 함수에 의해 결정 된 두 어셈블리 id의 동일성을 나타냅니다.  
  
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
  
## <a name="members"></a>멤버  
  
|멤버 이름|설명|  
|-----------------|-----------------|  
|`ACR_EquivalentFullMatch`|비교의 모든 어셈블리 필드가 일치 함을 나타냅니다.|  
|`ACR_EquivalentFXUnified`|.NET Framework 버전 2.0에서 어셈블리 버전 번호의 CLR (공용 언어 런타임 버전) 통합에 따라 어셈블리가 동일한 것으로 간주 됨을 나타냅니다.|  
|`ACR_EquivalentPartialFXUnified`|.NET Framework 2.0에서 어셈블리 버전 번호의 CLR 통합을 기반으로 하는 어셈블리의 부분 일치를 나타냅니다.|  
|`ACR_EquivalentPartialMatch`|어셈블리의 부분 일치를 나타냅니다.|  
|`ACR_EquivalentPartialUnified`|버전 번호의 레거시 통합을 기반으로 하는 어셈블리의 부분 일치를 나타냅니다.|  
|`ACR_EquivalentPartialWeakNamed`|단순한 이름의 어셈블리에 대 한 부분 일치를 나타냅니다.|  
|`ACR_EquivalentUnified`|는 .NET Framework의 레거시 버전에서 버전 번호의 CLR 통합에 따라 어셈블리가 동일한 것으로 간주 됨을 나타냅니다.|  
|`ACR_EquivalentWeakNamed`|버전 번호가 무시 된 두 개의 단순한 명명 된 어셈블리 사이에 일치 하는 항목을 나타냅니다.|  
|`ACR_NonEquivalent`|두 어셈블리 사이에 일치 하는 항목이 없음을 나타냅니다.|  
|`ACR_NonEquivalentPartialVersion`|는 부분적 으로만 일치 하는 버전 번호를 제외 하 고 두 어셈블리가 일치 함을 나타냅니다.|  
|`ACR_NonEquivalentVersion`|일치 하지 않는 버전 번호를 제외 하 고 두 어셈블리가 일치 함을 나타냅니다.|  
|`ACR_Unknown`|같지 않음의 원인을 알 수 없음을 나타냅니다.|  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Fusion. h  
  
 **라이브러리:** MsCorEE.dll의 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참조

- [CompareAssemblyIdentity 함수](compareassemblyidentity-function.md)
- [Fusion 열거형](fusion-enumerations.md)
