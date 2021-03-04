---
description: '자세히 알아보기: ICorProfilerInfo10:: GetLOHObjectSizeThreshold 메서드'
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
ms.openlocfilehash: 96c502dba5b2807f9cd9c3c5cceb6b3b9985a406
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/04/2021
ms.locfileid: "102106958"
---
# <a name="icorprofilerinfo10getlohobjectsizethreshold-method"></a><span data-ttu-id="e94d1-103">ICorProfilerInfo10:: GetLOHObjectSizeThreshold 메서드</span><span class="sxs-lookup"><span data-stu-id="e94d1-103">ICorProfilerInfo10::GetLOHObjectSizeThreshold Method</span></span>

<span data-ttu-id="e94d1-104">구성 된 LOH (large object heap) 임계값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="e94d1-104">Gets the value of the configured large object heap (LOH) threshold.</span></span>

## <a name="syntax"></a><span data-ttu-id="e94d1-105">구문</span><span class="sxs-lookup"><span data-stu-id="e94d1-105">Syntax</span></span>

```cpp
HRESULT GetLOHObjectSizeThreshold( [out] DWORD *pThreshold );
```

## <a name="parameters"></a><span data-ttu-id="e94d1-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="e94d1-106">Parameters</span></span>

- `pThreshold`

  <span data-ttu-id="e94d1-107">\[out] 대량 개체 힙 임계값 (바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="e94d1-107">\[out] The large object heap threshold in bytes.</span></span>

## <a name="remarks"></a><span data-ttu-id="e94d1-108">설명</span><span class="sxs-lookup"><span data-stu-id="e94d1-108">Remarks</span></span>

<span data-ttu-id="e94d1-109">큰 개체 힙 임계값 보다 큰 개체는 큰 개체 힙에 할당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e94d1-109">Objects larger than the large object heap threshold will be allocated on the large object heap.</span></span> <span data-ttu-id="e94d1-110">.NET Core 3.0부터 큰 개체 힙 임계값은 구성 가능 하며, `pThreshold` 활성 큰 개체 힙 임계값 크기 (바이트)를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="e94d1-110">Starting with .NET Core 3.0 the large object heap threshold is configurable, `pThreshold` will contain the active large object heap threshold size in bytes.</span></span>

## <a name="requirements"></a><span data-ttu-id="e94d1-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e94d1-111">Requirements</span></span>

<span data-ttu-id="e94d1-112">**플랫폼:** [.Net Core 지원 운영 체제](../../../core/install/windows.md?pivots=os-windows)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e94d1-112">**Platforms:** See [.NET Core supported operating systems](../../../core/install/windows.md?pivots=os-windows).</span></span>

<span data-ttu-id="e94d1-113">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e94d1-113">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="e94d1-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e94d1-114">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="e94d1-115">**.Net 버전:**[!INCLUDE[net_core_30](../../../../includes/net-core-30-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e94d1-115">**.NET Versions:** [!INCLUDE[net_core_30](../../../../includes/net-core-30-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="e94d1-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e94d1-116">See also</span></span>

- [<span data-ttu-id="e94d1-117">ICorProfilerInfo10 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e94d1-117">ICorProfilerInfo10 Interface</span></span>](icorprofilerinfo10-interface.md)
