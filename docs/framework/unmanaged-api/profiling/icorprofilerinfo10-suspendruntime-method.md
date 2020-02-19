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
ms.openlocfilehash: 8d00718579f44a164cd83e2b05d41f70f1c65785
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452151"
---
# <a name="icorprofilerinfo10suspendruntime-method"></a><span data-ttu-id="c3ef3-102">ICorProfilerInfo10:: SuspendRuntime 메서드</span><span class="sxs-lookup"><span data-stu-id="c3ef3-102">ICorProfilerInfo10::SuspendRuntime Method</span></span>

<span data-ttu-id="c3ef3-103">GC를 수행 하지 않고 런타임을 일시 중단 합니다.</span><span class="sxs-lookup"><span data-stu-id="c3ef3-103">Suspends the runtime without performing a GC.</span></span>

## <a name="syntax"></a><span data-ttu-id="c3ef3-104">구문</span><span class="sxs-lookup"><span data-stu-id="c3ef3-104">Syntax</span></span>

```cpp
HRESULT SuspendRuntime();
```

## <a name="requirements"></a><span data-ttu-id="c3ef3-105">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c3ef3-105">Requirements</span></span>

<span data-ttu-id="c3ef3-106">**플랫폼:** [.Net Core 지원 운영 체제](../../../core/install/dependencies.md?pivots=os-windows)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c3ef3-106">**Platforms:** See [.NET Core supported operating systems](../../../core/install/dependencies.md?pivots=os-windows).</span></span>

<span data-ttu-id="c3ef3-107">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c3ef3-107">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="c3ef3-108">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c3ef3-108">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="c3ef3-109">**.Net 버전:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c3ef3-109">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="c3ef3-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c3ef3-110">See also</span></span>

- [<span data-ttu-id="c3ef3-111">ICorProfilerInfo10 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c3ef3-111">ICorProfilerInfo10 Interface</span></span>](icorprofilerinfo10-interface.md)
