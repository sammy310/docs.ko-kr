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
# <a name="icorprofilerinfo10suspendruntime-method"></a><span data-ttu-id="400ce-102">ICorProfilerInfo10:: SuspendRuntime 메서드</span><span class="sxs-lookup"><span data-stu-id="400ce-102">ICorProfilerInfo10::SuspendRuntime Method</span></span>

<span data-ttu-id="400ce-103">GC를 수행 하지 않고 런타임을 일시 중단 합니다.</span><span class="sxs-lookup"><span data-stu-id="400ce-103">Suspends the runtime without performing a GC.</span></span>

## <a name="syntax"></a><span data-ttu-id="400ce-104">구문</span><span class="sxs-lookup"><span data-stu-id="400ce-104">Syntax</span></span>

```cpp
HRESULT SuspendRuntime();
```

## <a name="requirements"></a><span data-ttu-id="400ce-105">요구 사항</span><span class="sxs-lookup"><span data-stu-id="400ce-105">Requirements</span></span>

<span data-ttu-id="400ce-106">**플랫폼:** [.Net Core 지원 운영 체제](../../../core/install/dependencies.md?tabs=netcore30&pivots=os-windows)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="400ce-106">**Platforms:** See [.NET Core supported operating systems](../../../core/install/dependencies.md?tabs=netcore30&pivots=os-windows).</span></span>

<span data-ttu-id="400ce-107">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="400ce-107">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="400ce-108">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="400ce-108">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="400ce-109">**.Net 버전:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span><span class="sxs-lookup"><span data-stu-id="400ce-109">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="400ce-110">참조</span><span class="sxs-lookup"><span data-stu-id="400ce-110">See also</span></span>

- [<span data-ttu-id="400ce-111">ICorProfilerInfo10 인터페이스</span><span class="sxs-lookup"><span data-stu-id="400ce-111">ICorProfilerInfo10 Interface</span></span>](icorprofilerinfo10-interface.md)
