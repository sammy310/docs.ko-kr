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
ms.openlocfilehash: cf599e5ded73b09d54c98dcd99f51b30c6a4ba82
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/21/2019
ms.locfileid: "69661198"
---
# <a name="icorprofilerinfo10resumeruntime-method"></a><span data-ttu-id="30ff8-102">ICorProfilerInfo10:: ResumeRuntime 메서드</span><span class="sxs-lookup"><span data-stu-id="30ff8-102">ICorProfilerInfo10::ResumeRuntime Method</span></span>

<span data-ttu-id="30ff8-103">GC를 수행 하지 않고 런타임을 다시 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="30ff8-103">Resumes the runtime without performing a GC.</span></span>

## <a name="syntax"></a><span data-ttu-id="30ff8-104">구문</span><span class="sxs-lookup"><span data-stu-id="30ff8-104">Syntax</span></span>

```cpp
HRESULT ResumeRuntime();
```

## <a name="requirements"></a><span data-ttu-id="30ff8-105">요구 사항</span><span class="sxs-lookup"><span data-stu-id="30ff8-105">Requirements</span></span>

<span data-ttu-id="30ff8-106">**플랫폼** [.Net Core 지원 운영 체제](../../../core/windows-prerequisites.md#net-core-supported-operating-systems)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="30ff8-106">**Platforms:** See [.NET Core supported operating systems](../../../core/windows-prerequisites.md#net-core-supported-operating-systems).</span></span>

<span data-ttu-id="30ff8-107">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="30ff8-107">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="30ff8-108">**라이브러리** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="30ff8-108">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="30ff8-109">**.Net 버전:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span><span class="sxs-lookup"><span data-stu-id="30ff8-109">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="30ff8-110">참고자료</span><span class="sxs-lookup"><span data-stu-id="30ff8-110">See also</span></span>

- [<span data-ttu-id="30ff8-111">ICorProfilerInfo10 인터페이스</span><span class="sxs-lookup"><span data-stu-id="30ff8-111">ICorProfilerInfo10 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-interface.md)
