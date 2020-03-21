---
title: COR_PRF_REJIT_FLAGS 열거형
ms.date: 08/06/2019
api_name:
- COR_PRF_REJIT_FLAGS Enumeration
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_REJIT_FLAGS
helpviewer_keywords:
- COR_PRF_REJIT_FLAGS enumeration [.NET Framework profiling]
topic_type:
- apiref
author: davmason
ms.author: davmason
ms.openlocfilehash: 8fc5f1a488826d8adc6aecb8ef122609bebbe813
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177092"
---
# <a name="cor_prf_rejit_flags-enumeration"></a>COR_PRF_REJIT_FLAGS 열거형
[ICorProfilerInfo10:::RequestReJITWithInliners](icorprofilerinfo10-requestrejitwithinliners-method.md) API가 어떻게 작동해야 하는지 나타내는 값을 포함합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
typedef enum  
{
    COR_PRF_REJIT_BLOCK_INLINING = 0x1,
    COR_PRF_REJIT_INLINING_CALLBACKS    = 0x2
} COR_PRF_REJIT_FLAGS;  
```  
  
## <a name="members"></a>구성원  
  
|멤버|Description|  
|------------|-----------------|  
|`COR_PRF_REJIT_BLOCK_INLINING`| ReJITted 메서드는 다른 메서드에서 인라인되는 것을 차단합니다. |  
|`COR_PRF_REJIT_INLINING_CALLBACKS`| ReJITted에 요청된 메서드를 인라인으로 하는 메서드에 대한 콜백을 받습니다. `GetFunctionParameters` |  

## <a name="requirements"></a>요구 사항  
 **플랫폼:** [.NET Core 지원 운영 체제를](../../../core/install/dependencies.md?pivots=os-windows)참조하십시오.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_core_22](../../../../includes/net-core-22-md.md)]
  
## <a name="see-also"></a>참고 항목

- [프로파일링 열거형](profiling-enumerations.md)
