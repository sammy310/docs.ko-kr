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
ms.openlocfilehash: d6b6575cf04635b40b504b11bc415f61f05b4205
ms.sourcegitcommit: a97ecb94437362b21fffc5eb3c38b6c0b4368999
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/13/2019
ms.locfileid: "68974023"
---
# <a name="icorprofilerinfo10getlohobjectsizethreshold-method"></a><span data-ttu-id="56f4e-102">ICorProfilerInfo10:: GetLOHObjectSizeThreshold 메서드</span><span class="sxs-lookup"><span data-stu-id="56f4e-102">ICorProfilerInfo10::GetLOHObjectSizeThreshold Method</span></span>
  
 <span data-ttu-id="56f4e-103">구성 된 LOH (large object heap) 임계값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="56f4e-103">Gets the value of the configured large object heap (LOH) threshold.</span></span>   
  
## <a name="syntax"></a><span data-ttu-id="56f4e-104">구문</span><span class="sxs-lookup"><span data-stu-id="56f4e-104">Syntax</span></span>  
  
```cpp
HRESULT GetLOHObjectSizeThreshold( [out] DWORD *pThreshold );
```  
  
#### <a name="parameters"></a><span data-ttu-id="56f4e-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="56f4e-105">Parameters</span></span>  
 `pThreshold` \
 <span data-ttu-id="56f4e-106">제한이 대량 개체 힙 임계값 (바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="56f4e-106">[out] The large object heap threshold in bytes.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="56f4e-107">설명</span><span class="sxs-lookup"><span data-stu-id="56f4e-107">Remarks</span></span>  
 <span data-ttu-id="56f4e-108">큰 개체 힙 임계값 보다 큰 개체는 큰 개체 힙에 할당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="56f4e-108">Objects larger than the large object heap threshold will be allocated on the large object heap.</span></span> <span data-ttu-id="56f4e-109">.Net Core 3.0부터 큰 개체 힙 임계값은 구성 가능 하며, `pThreshold` 활성 큰 개체 힙 임계값 크기 (바이트)를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="56f4e-109">Starting with .NET Core 3.0 the large object heap threshold is configurable, `pThreshold` will contain the active large object heap threshold size in bytes.</span></span>

## <a name="requirements"></a><span data-ttu-id="56f4e-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="56f4e-110">Requirements</span></span>  
 <span data-ttu-id="56f4e-111">**플랫폼** [.Net Core 지원 운영 체제](../../../core/windows-prerequisites.md#net-core-supported-operating-systems)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="56f4e-111">**Platforms:** See [.NET Core supported operating systems](../../../core/windows-prerequisites.md#net-core-supported-operating-systems).</span></span>  
  
 <span data-ttu-id="56f4e-112">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="56f4e-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="56f4e-113">**라이브러리** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="56f4e-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="56f4e-114">**.Net 버전:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span><span class="sxs-lookup"><span data-stu-id="56f4e-114">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span></span>
  
## <a name="see-also"></a><span data-ttu-id="56f4e-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="56f4e-115">See also</span></span>
- [<span data-ttu-id="56f4e-116">ICorProfilerInfo10 인터페이스</span><span class="sxs-lookup"><span data-stu-id="56f4e-116">ICorProfilerInfo10 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-interface.md)

