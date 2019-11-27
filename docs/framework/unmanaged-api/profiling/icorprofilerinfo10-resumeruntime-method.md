---
title: ICorProfilerInfo10::ResumeRuntime
ms.date: 08/06/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo10.ResumeRuntime
api_location:
- mscorwks.dll
api_type:
- COM
author: davmason
ms.author: davmason
ms.openlocfilehash: 515b42d649f68345f9924f57a91d146556480e0a
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449797"
---
# <a name="icorprofilerinfo10resumeruntime-method"></a>ICorProfilerInfo10:: ResumeRuntime 메서드

GC를 수행 하지 않고 런타임을 다시 시작 합니다.

## <a name="syntax"></a>구문

```cpp
HRESULT ResumeRuntime();
```

## <a name="requirements"></a>요구 사항

**플랫폼:** [.Net Core 지원 운영 체제](../../../core/install/dependencies.md?tabs=netcore30&pivots=os-windows)를 참조 하세요.

**헤더:** CorProf.idl, CorProf.h

**라이브러리:** CorGuids.lib

**.Net 버전:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]

## <a name="see-also"></a>참고자료

- [ICorProfilerInfo10 인터페이스](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-interface.md)
