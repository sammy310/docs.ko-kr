---
title: COR_PRF_SNAPSHOT_INFO 열거형
ms.date: 03/30/2017
api_name:
- COR_PRF_SNAPSHOT_INFO
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_SNAPSHOT_INFO
helpviewer_keywords:
- COR_PRF_SNAPSHOT_INFO enumeration [.NET Framework profiling]
ms.assetid: a5906b2a-ad4a-4cc6-a421-2d7d8adf7468
topic_type:
- apiref
ms.openlocfilehash: 97bf3e69a8ea155d53479ba6f61988e56e3bd396
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/29/2020
ms.locfileid: "76867026"
---
# <a name="cor_prf_snapshot_info-enumeration"></a>COR_PRF_SNAPSHOT_INFO 열거형
프로파일러에서 [StackSnapshotCallback](stacksnapshotcallback-function.md) 함수를 호출할 때마다 스택 스냅숏으로 다시 전달할 데이터의 양을 지정 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
typedef enum _COR_PRF_SNAPSHOT_INFO {  
    COR_PRF_SNAPSHOT_DEFAULT = 0x0,  
    COR_PRF_SNAPSHOT_REGISTER_CONTEXT = 0x1,  
    COR_PRF_SNAPSHOT_X86_OPTIMIZED = 0X2  
} COR_PRF_SNAPSHOT_INFO;  
```  
  
## <a name="members"></a>Members  
  
|Members|설명|  
|-------------|-----------------|  
|`COR_PRF_SNAPSHOT_DEFAULT`|`context` 매개 변수를 제외 하 고 모든 `StackSnapshotCallback` 매개 변수에 대 한 값을 전달 해야 함을 나타냅니다.|  
|`COR_PRF_SNAPSHOT_REGISTER_CONTEXT`|`context` 매개 변수를 포함 하 여 모든 `StackSnapshotCallback` 매개 변수에 대 한 값을 전달 해야 함을 나타냅니다.|  
|`COR_PRF_SNAPSHOT_X86_OPTIMIZED`|더 간단한 다른 스택 탐색 알고리즘이 사용 됨을 나타냅니다.|  
  
## <a name="remarks"></a>주의  
 `COR_PRF_SNAPSHOT_INFO` 열거형에서 제공 하는 값은 [DoStackSnapshot](icorprofilerinfo2-dostacksnapshot-method.md) 메서드에 매개 변수로 전달 됩니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참조

- [DoStackSnapshot 메서드](icorprofilerinfo2-dostacksnapshot-method.md)
- [프로파일링 열거형](profiling-enumerations.md)
