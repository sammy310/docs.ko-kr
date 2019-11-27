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
ms.openlocfilehash: f5104c779f99ef9f26a9eccc00008ded62336d8e
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74426970"
---
# <a name="icorprofilerinfo10suspendruntime-method"></a><span data-ttu-id="5130b-102">ICorProfilerInfo10:: SuspendRuntime 메서드</span><span class="sxs-lookup"><span data-stu-id="5130b-102">ICorProfilerInfo10::SuspendRuntime Method</span></span>

<span data-ttu-id="5130b-103">GC를 수행 하지 않고 런타임을 일시 중단 합니다.</span><span class="sxs-lookup"><span data-stu-id="5130b-103">Suspends the runtime without performing a GC.</span></span>

## <a name="syntax"></a><span data-ttu-id="5130b-104">구문</span><span class="sxs-lookup"><span data-stu-id="5130b-104">Syntax</span></span>

```cpp
HRESULT SuspendRuntime();
```

## <a name="requirements"></a><span data-ttu-id="5130b-105">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5130b-105">Requirements</span></span>

<span data-ttu-id="5130b-106">**플랫폼:** [.Net Core 지원 운영 체제](../../../core/install/dependencies.md?tabs=netcore30&pivots=os-windows)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5130b-106">**Platforms:** See [.NET Core supported operating systems](../../../core/install/dependencies.md?tabs=netcore30&pivots=os-windows).</span></span>

<span data-ttu-id="5130b-107">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="5130b-107">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="5130b-108">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5130b-108">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="5130b-109">**.Net 버전:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5130b-109">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="5130b-110">참고자료</span><span class="sxs-lookup"><span data-stu-id="5130b-110">See also</span></span>

- [<span data-ttu-id="5130b-111">ICorProfilerInfo10 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5130b-111">ICorProfilerInfo10 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-interface.md)
