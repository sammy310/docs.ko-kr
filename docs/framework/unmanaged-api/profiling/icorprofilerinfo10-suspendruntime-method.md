---
title: ICorProfilerInfo10::SuspendRuntime
ms.date: 08/06/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo10.SuspendRuntime
api_location:
- mscorwks.dll
api_type:
- COM
author: davmason
ms.author: davmason
ms.openlocfilehash: a4c875f6aae996271dee9ac193768ef6981efc19
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/29/2020
ms.locfileid: "76863038"
---
# <a name="icorprofilerinfo10suspendruntime-method"></a>ICorProfilerInfo10:: SuspendRuntime 메서드

GC를 수행 하지 않고 런타임을 일시 중단 합니다.

## <a name="syntax"></a>구문

```cpp
HRESULT SuspendRuntime();
```

## <a name="requirements"></a>요구 사항

**플랫폼:** [.Net Core 지원 운영 체제](../../../core/install/dependencies.md?tabs=netcore30&pivots=os-windows)를 참조 하세요.

**헤더:** CorProf.idl, CorProf.h

**라이브러리:** CorGuids.lib

**.Net 버전:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]

## <a name="see-also"></a>참조

- [ICorProfilerInfo10 인터페이스](icorprofilerinfo10-interface.md)
