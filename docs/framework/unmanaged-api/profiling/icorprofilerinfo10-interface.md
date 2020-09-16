---
title: ICorProfilerInfo10 인터페이스
ms.date: 08/06/2019
author: davmason
ms.author: davmason
ms.openlocfilehash: 7e483bae9b7898e25c376fa92d0449fc49c6f9ee
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "90548688"
---
# <a name="icorprofilerinfo10-interface"></a>ICorProfilerInfo10 인터페이스

함수 IL을 수정 하 고, 런타임에서 정보를 쿼리하고, 런타임을 일시 중단 하 고 다시 시작 하는 메서드를 제공 하는 [ICorProfilerInfo9](icorprofilerinfo9-interface.md) 의 서브 클래스입니다.

## <a name="methods"></a>메서드  

| 메서드|Description|  
| ------------|-----------------|  
|[EnumerateObjectReferences 메서드](icorprofilerinfo10-enumerateobjectreferences-method.md)|ObjectID, callback 및 clientData가 지정 된 경우 각 개체 참조를 열거 합니다 (있는 경우). |
|[IsFrozenObject 메서드](icorprofilerinfo10-isfrozenobject-method.md)|ObjectID가 지정 된 경우 개체가 읽기 전용 세그먼트에 있는지 여부를 확인 합니다. |
|[GetLOHObjectSizeThreshold 메서드](icorprofilerinfo10-getlohobjectsizethreshold-method.md)|구성 된 LOH 임계값의 값을 가져옵니다. |
|[RequestReJITWithInliners 메서드](icorprofilerinfo10-requestrejitwithinliners-method.md)| 요청 된 메서드 뿐 아니라 요청 된 메서드의 모든 inliners ReJITs 합니다.  |
|[SuspendRuntime 메서드](icorprofilerinfo10-suspendruntime-method.md)| GC를 수행 하지 않고 런타임을 일시 중단 합니다. |
|[ResumeRuntime 메서드](icorprofilerinfo10-resumeruntime-method.md)| GC를 수행 하지 않고 런타임을 다시 시작 합니다. |

## <a name="requirements"></a>요구 사항  
**플랫폼:** [.Net Core 지원 운영 체제](../../../core/install/windows.md?pivots=os-windows)를 참조 하세요.  
**헤더:** CorProf.idl, CorProf.h  
**.Net 버전:**[!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]

## <a name="see-also"></a>참조

- [프로파일링 인터페이스](profiling-interfaces.md)
