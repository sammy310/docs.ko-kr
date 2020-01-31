---
title: 'ICorProfilerInfo10:: GetLOHObjectSizeThreshold'
ms.date: 08/06/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo10.GetLOHObjectSizeThreshold
api_location:
- mscorwks.dll
api_type:
- COM
author: davmason
ms.author: davmason
ms.openlocfilehash: d4d498c1d75625b2abc37dc1f4c88d73b58ec675
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790025"
---
# <a name="icorprofilerinfo10getlohobjectsizethreshold-method"></a><span data-ttu-id="370d6-102">ICorProfilerInfo10:: GetLOHObjectSizeThreshold 메서드</span><span class="sxs-lookup"><span data-stu-id="370d6-102">ICorProfilerInfo10::GetLOHObjectSizeThreshold Method</span></span>

<span data-ttu-id="370d6-103">구성 된 LOH (large object heap) 임계값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="370d6-103">Gets the value of the configured large object heap (LOH) threshold.</span></span>

## <a name="syntax"></a><span data-ttu-id="370d6-104">구문</span><span class="sxs-lookup"><span data-stu-id="370d6-104">Syntax</span></span>

```cpp
HRESULT GetLOHObjectSizeThreshold( [out] DWORD *pThreshold );
```

## <a name="parameters"></a><span data-ttu-id="370d6-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="370d6-105">Parameters</span></span>

- `pThreshold`

  <span data-ttu-id="370d6-106">\[out] 대량 개체 힙 임계값 (바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="370d6-106">\[out] The large object heap threshold in bytes.</span></span>

## <a name="remarks"></a><span data-ttu-id="370d6-107">주의</span><span class="sxs-lookup"><span data-stu-id="370d6-107">Remarks</span></span>

<span data-ttu-id="370d6-108">큰 개체 힙 임계값 보다 큰 개체는 큰 개체 힙에 할당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="370d6-108">Objects larger than the large object heap threshold will be allocated on the large object heap.</span></span> <span data-ttu-id="370d6-109">.NET Core 3.0부터 큰 개체 힙 임계값은 구성 가능 하며, `pThreshold`은 활성 큰 개체 힙 임계값 크기 (바이트)를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="370d6-109">Starting with .NET Core 3.0 the large object heap threshold is configurable, `pThreshold` will contain the active large object heap threshold size in bytes.</span></span>

## <a name="requirements"></a><span data-ttu-id="370d6-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="370d6-110">Requirements</span></span>

<span data-ttu-id="370d6-111">**플랫폼:** [.Net Core 지원 운영 체제](../../../core/install/dependencies.md?tabs=netcore30&pivots=os-windows)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="370d6-111">**Platforms:** See [.NET Core supported operating systems](../../../core/install/dependencies.md?tabs=netcore30&pivots=os-windows).</span></span>

<span data-ttu-id="370d6-112">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="370d6-112">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="370d6-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="370d6-113">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="370d6-114">**.Net 버전:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span><span class="sxs-lookup"><span data-stu-id="370d6-114">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="370d6-115">참조</span><span class="sxs-lookup"><span data-stu-id="370d6-115">See also</span></span>

- [<span data-ttu-id="370d6-116">ICorProfilerInfo10 인터페이스</span><span class="sxs-lookup"><span data-stu-id="370d6-116">ICorProfilerInfo10 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-interface.md)
