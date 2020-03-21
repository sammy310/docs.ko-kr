---
title: ICorProfilerInfo10 인터페이스
ms.date: 08/06/2019
author: davmason
ms.author: davmason
ms.openlocfilehash: 4c5d553744008734037975d6e63e1b07b89cf886
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175072"
---
# <a name="icorprofilerinfo10-interface"></a>ICorProfilerInfo10 인터페이스

함수 IL을 수정하고, 런타임에서 정보를 쿼리하고, 런타임을 일시 중단하고 다시 시작하려는 메서드를 제공하는 [ICorProfilerInfo9의](icorprofilerinfo9-interface.md) 하위 클래스입니다.

## <a name="methods"></a>메서드  

| 방법|Description|  
| ------------|-----------------|  
|[EnumerateObjectReferences 메서드](icorprofilerinfo10-enumerateobjectreferences-method.md)|ObjectID, 콜백 및 clientData가 주어지면 각 개체 참조(있는 경우)를 유거합니다. |
|[IsFrozenObject 메서드](icorprofilerinfo10-isfrozenobject-method.md)|ObjectID가 주어지면 개체가 읽기 전용 세그먼트에 있는지 여부를 결정합니다. |
|[GetLOHObjectSizeThreshold 메서드](icorprofilerinfo10-getlohobjectsizethreshold-method.md)|구성된 LOH 임계값값을 가져옵니다. |
|[RequestReJITWithInliners 메서드](icorprofilerinfo10-requestrejitwithinliners-method.md)| 요청된 메서드와 요청된 메서드의 인라이너를 ReJIT합니다.  |
|[SuspendRuntime 메서드](icorprofilerinfo10-suspendruntime-method.md)| GC를 수행하지 않고 런타임을 일시 중단합니다. |
|[ResumeRuntime 메서드](icorprofilerinfo10-resumeruntime-method.md)| GC를 수행하지 않고 런타임을 다시 시작합니다. |

## <a name="requirements"></a>요구 사항  
**플랫폼:** [.NET Core 지원 운영 체제를](../../../core/install/dependencies.md?pivots=os-windows)참조하십시오.  
**헤더:** CorProf.idl, CorProf.h  
**.NET 버전:**[!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]

## <a name="see-also"></a>참고 항목

- [프로파일링 인터페이스](profiling-interfaces.md)
