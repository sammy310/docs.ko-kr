---
description: '다음에 대 한 자세한 정보: 열거형 COR_PRF_REJIT_FLAGS'
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
ms.openlocfilehash: aad66285e9b31558a68b8ccdfc71f103d1772946
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/04/2021
ms.locfileid: "102106919"
---
# <a name="cor_prf_rejit_flags-enumeration"></a>COR_PRF_REJIT_FLAGS 열거형

[ICorProfilerInfo10:: RequestReJITWithInliners](icorprofilerinfo10-requestrejitwithinliners-method.md) API가 동작 하는 방법을 나타내는 값을 포함 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
typedef enum  
{
    COR_PRF_REJIT_BLOCK_INLINING = 0x1,
    COR_PRF_REJIT_INLINING_CALLBACKS    = 0x2
} COR_PRF_REJIT_FLAGS;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|`COR_PRF_REJIT_BLOCK_INLINING`| ReJITted 메서드는 다른 메서드에서 인라인 되지 않도록 차단 됩니다. |  
|`COR_PRF_REJIT_INLINING_CALLBACKS`| `GetFunctionParameters`ReJITted 하도록 요청 된 메서드를 인라인 하는 메서드에 대 한 콜백을 수신 합니다. |  

## <a name="requirements"></a>요구 사항  

 **플랫폼:** [.Net Core 지원 운영 체제](../../../core/install/windows.md?pivots=os-windows)를 참조 하세요.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_core_30](../../../../includes/net-core-30-md.md)]
  
## <a name="see-also"></a>참고 항목

- [프로파일링 열거형](profiling-enumerations.md)
