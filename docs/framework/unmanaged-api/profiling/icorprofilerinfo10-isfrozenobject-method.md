---
title: ICorProfilerInfo10::IsFrozenObject
ms.date: 08/06/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo10.IsFrozenObject
api_location:
- mscorwks.dll
api_type:
- COM
author: davmason
ms.author: davmason
ms.openlocfilehash: 05f25d8fb61a16f41a82a987529017db6a687740
ms.sourcegitcommit: a97ecb94437362b21fffc5eb3c38b6c0b4368999
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/13/2019
ms.locfileid: "68973993"
---
# <a name="icorprofilerinfo10isfrozenobject-method"></a>ICorProfilerInfo10:: IsFrozenObject 메서드
  
 ObjectID가 지정 된 경우 개체가 읽기 전용 세그먼트에 있는지 여부를 확인 합니다.   
  
## <a name="syntax"></a>구문  
  
```cpp
HRESULT IsFrozenObject( [in]  ObjectID objectId,
                        [out] BOOL *pbFrozen);
```  
  
#### <a name="parameters"></a>매개 변수  
 
 `objectId` \
 진행 검사할 개체입니다.

 `pbFrozen` \
 제한이 개체가 `BOOL` 읽기 전용 세그먼트에 있는지 여부를 나타내는입니다.

## <a name="requirements"></a>요구 사항  
 **플랫폼** [.Net Core 지원 운영 체제](../../../core/windows-prerequisites.md#net-core-supported-operating-systems)를 참조 하세요.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리** CorGuids.lib  
  
 **.Net 버전:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)] 
  
## <a name="see-also"></a>참고자료
- [ICorProfilerInfo10 인터페이스](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-interface.md)

