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
# <a name="icorprofilerinfo10resumeruntime-method"></a><span data-ttu-id="e044f-102">ICorProfilerInfo10:: ResumeRuntime 메서드</span><span class="sxs-lookup"><span data-stu-id="e044f-102">ICorProfilerInfo10::ResumeRuntime Method</span></span>

<span data-ttu-id="e044f-103">GC를 수행 하지 않고 런타임을 다시 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="e044f-103">Resumes the runtime without performing a GC.</span></span>

## <a name="syntax"></a><span data-ttu-id="e044f-104">구문</span><span class="sxs-lookup"><span data-stu-id="e044f-104">Syntax</span></span>

```cpp
HRESULT ResumeRuntime();
```

## <a name="requirements"></a><span data-ttu-id="e044f-105">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e044f-105">Requirements</span></span>

<span data-ttu-id="e044f-106">**플랫폼:** [.Net Core 지원 운영 체제](../../../core/install/dependencies.md?tabs=netcore30&pivots=os-windows)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e044f-106">**Platforms:** See [.NET Core supported operating systems](../../../core/install/dependencies.md?tabs=netcore30&pivots=os-windows).</span></span>

<span data-ttu-id="e044f-107">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e044f-107">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="e044f-108">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e044f-108">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="e044f-109">**.Net 버전:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e044f-109">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="e044f-110">참고자료</span><span class="sxs-lookup"><span data-stu-id="e044f-110">See also</span></span>

- [<span data-ttu-id="e044f-111">ICorProfilerInfo10 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e044f-111">ICorProfilerInfo10 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-interface.md)
