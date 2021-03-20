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
ms.openlocfilehash: 7dca887f6d0ff5f9360b0edaa1568bc4b1bb42ac
ms.sourcegitcommit: 20b4565974d185c7716656a6c63e3cfdbdf4bf41
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/20/2021
ms.locfileid: "104759770"
---
# <a name="icorprofilerinfo10getlohobjectsizethreshold-method"></a><span data-ttu-id="66ee8-103">ICorProfilerInfo10:: GetLOHObjectSizeThreshold 메서드</span><span class="sxs-lookup"><span data-stu-id="66ee8-103">ICorProfilerInfo10::GetLOHObjectSizeThreshold Method</span></span>

<span data-ttu-id="66ee8-104">구성 된 LOH (large object heap) 임계값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="66ee8-104">Gets the value of the configured large object heap (LOH) threshold.</span></span>

## <a name="syntax"></a><span data-ttu-id="66ee8-105">구문</span><span class="sxs-lookup"><span data-stu-id="66ee8-105">Syntax</span></span>

```cpp
HRESULT GetLOHObjectSizeThreshold( [out] DWORD *pThreshold );
```

## <a name="parameters"></a><span data-ttu-id="66ee8-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="66ee8-106">Parameters</span></span>

<span data-ttu-id="66ee8-107">`pThreshold` 제한이 대량 개체 힙 임계값 (바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="66ee8-107">`pThreshold` [out] The large object heap threshold in bytes.</span></span>

## <a name="remarks"></a><span data-ttu-id="66ee8-108">설명</span><span class="sxs-lookup"><span data-stu-id="66ee8-108">Remarks</span></span>

<span data-ttu-id="66ee8-109">큰 개체 힙 임계값 보다 큰 개체는 큰 개체 힙에 할당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="66ee8-109">Objects larger than the large object heap threshold will be allocated on the large object heap.</span></span> <span data-ttu-id="66ee8-110">.NET Core 3.0부터 큰 개체 힙 임계값은 구성 가능 하며, `pThreshold` 활성 큰 개체 힙 임계값 크기 (바이트)를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="66ee8-110">Starting with .NET Core 3.0 the large object heap threshold is configurable, `pThreshold` will contain the active large object heap threshold size in bytes.</span></span>

## <a name="requirements"></a><span data-ttu-id="66ee8-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="66ee8-111">Requirements</span></span>

<span data-ttu-id="66ee8-112">**플랫폼:** [.Net Core 지원 운영 체제](../../../core/install/windows.md?pivots=os-windows)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="66ee8-112">**Platforms:** See [.NET Core supported operating systems](../../../core/install/windows.md?pivots=os-windows).</span></span>

<span data-ttu-id="66ee8-113">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="66ee8-113">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="66ee8-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="66ee8-114">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="66ee8-115">**.Net 버전:**[!INCLUDE[net_core_30](../../../../includes/net-core-30-md.md)]</span><span class="sxs-lookup"><span data-stu-id="66ee8-115">**.NET Versions:** [!INCLUDE[net_core_30](../../../../includes/net-core-30-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="66ee8-116">참조</span><span class="sxs-lookup"><span data-stu-id="66ee8-116">See also</span></span>

- [<span data-ttu-id="66ee8-117">ICorProfilerInfo10 인터페이스</span><span class="sxs-lookup"><span data-stu-id="66ee8-117">ICorProfilerInfo10 Interface</span></span>](icorprofilerinfo10-interface.md)
