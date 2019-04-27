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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 03b8ecc996e14263510e2d0a658cec020696c263
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61914503"
---
# <a name="assemblycomparisonresult-enumeration"></a>AssemblyComparisonResult 열거형
상응 하는 두 개의 어셈블리 id 기준으로 나타냅니다 합니다 [CompareAssemblyIdentity](../../../../docs/framework/unmanaged-api/fusion/compareassemblyidentity-function.md) 함수입니다.  
  
## <a name="syntax"></a>구문  
  
```  
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
|`ACR_EquivalentFullMatch`|모든 어셈블리 비교 일치 항목에 필드를 나타냅니다.|  
|`ACR_EquivalentFXUnified`|어셈블리 동일 하다 고 간주 어셈블리 버전 번호는.NET Framework 버전 2.0의 공용 언어 런타임 버전 (CLR) 통합 기반을 나타냅니다.|  
|`ACR_EquivalentPartialFXUnified`|.NET Framework 2.0에서 어셈블리 버전 번호의 CLR 통합에 따라 어셈블리가 부분적으로 일치를 나타냅니다.|  
|`ACR_EquivalentPartialMatch`|어셈블리의 부분 일치를 나타냅니다.|  
|`ACR_EquivalentPartialUnified`|어셈블리 버전 번호의 레거시 통합에 따라 부분적으로 일치를 나타냅니다.|  
|`ACR_EquivalentPartialWeakNamed`|단순한 이름의 어셈블리를 부분적으로 일치를 나타냅니다.|  
|`ACR_EquivalentUnified`|어셈블리 동일 하다 고 간주 레거시 버전의.NET Framework 버전 번호의 CLR 통합에 기반을 나타냅니다.|  
|`ACR_EquivalentWeakNamed`|해당 버전 번호는 무시 하는 두 명의 단순한 이름의 어셈블리 간에 일치를 나타냅니다.|  
|`ACR_NonEquivalent`|일치 항목이 없는 두 어셈블리 간에 발생 했음을 나타냅니다.|  
|`ACR_NonEquivalentPartialVersion`|두 어셈블리를 부분적 으로만 일치 하는 해당 버전 번호와 일치 하는지 나타냅니다.|  
|`ACR_NonEquivalentVersion`|두 어셈블리 해당 버전 번호는 일치 하지 않는 일치를 나타냅니다.|  
|`ACR_Unknown`|알 수 없는 같지 않은 이유는 나타냅니다.|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** Fusion.h  
  
 **라이브러리:** MsCorEE.dll에 리소스로 포함  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고자료

- [CompareAssemblyIdentity 함수](../../../../docs/framework/unmanaged-api/fusion/compareassemblyidentity-function.md)
- [Fusion 열거형](../../../../docs/framework/unmanaged-api/fusion/fusion-enumerations.md)
