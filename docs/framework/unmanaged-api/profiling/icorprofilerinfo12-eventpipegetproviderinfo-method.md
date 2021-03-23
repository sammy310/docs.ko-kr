---
description: '자세히 알아보기: ICorProfilerInfo12:: EventPipeGetProviderInfo 메서드'
title: 'ICorProfilerInfo12:: EventPipeGetProviderInfo 메서드'
ms.date: 03/19/2021
api_name:
- ICorProfilerInfo12.EventPipeGetProviderInfo
api_location:
- coreclr.dll
- corprof.idl
api_type:
- COM
ms.openlocfilehash: 7bc7ffe1c31e88dc1c65f1670f9bd179e732abfe
ms.sourcegitcommit: 20b4565974d185c7716656a6c63e3cfdbdf4bf41
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "104805703"
---
# <a name="icorprofilerinfo12eventpipegetproviderinfo-method"></a><span data-ttu-id="e72b6-103">ICorProfilerInfo12:: EventPipeGetProviderInfo 메서드</span><span class="sxs-lookup"><span data-stu-id="e72b6-103">ICorProfilerInfo12::EventPipeGetProviderInfo Method</span></span>

<span data-ttu-id="e72b6-104">프로파일러에서 다른 EventPipe 수신기가 받을 이벤트를 작성 하는 데 사용할 수 있는 EventPipe 공급자를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="e72b6-104">Creates an EventPipe provider that the profiler can use to write events for other EventPipe listeners to receive.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="e72b6-105">구문</span><span class="sxs-lookup"><span data-stu-id="e72b6-105">Syntax</span></span>  
  
```cpp  
    HRESULT EventPipeGetProviderInfo(
                [in] EVENTPIPE_PROVIDER provider,
                [in]  ULONG      cchName,
                [out] ULONG      *pcchName,
                [out, annotation("_Out_writes_to_(cchName, *pcchName)")]
                      WCHAR      providerName[]);
```  
  
## <a name="parameters"></a><span data-ttu-id="e72b6-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="e72b6-106">Parameters</span></span>

<span data-ttu-id="e72b6-107">`provider` 진행 이름을 제공할 공급자의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="e72b6-107">`provider` [in] The ID of the provider to provide the name for.</span></span>

<span data-ttu-id="e72b6-108">`cchName` 진행 의 크기 (문자) `providerName` 입니다.</span><span class="sxs-lookup"><span data-stu-id="e72b6-108">`cchName` [in] The size, in characters, of `providerName`.</span></span>

<span data-ttu-id="e72b6-109">`pcchName` 제한이 의 총 문자 길이에 대 한 포인터 `providerName` 입니다.</span><span class="sxs-lookup"><span data-stu-id="e72b6-109">`pcchName` [out] A pointer to the total character length of `providerName`.</span></span>

<span data-ttu-id="e72b6-110">`providerName` 제한이 호출자가 와이드 문자 버퍼를 제공 했습니다.</span><span class="sxs-lookup"><span data-stu-id="e72b6-110">`providerName` [out] A caller provided wide character buffer.</span></span> <span data-ttu-id="e72b6-111">함수가 반환 될 때 버퍼에는 공급자 이름이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e72b6-111">When the function returns the buffer will contain the name of the provider.</span></span>

## <a name="requirements"></a><span data-ttu-id="e72b6-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e72b6-112">Requirements</span></span>  

<span data-ttu-id="e72b6-113">**플랫폼:** [.Net Core 지원 운영 체제](../../../core/install/windows.md?pivots=os-windows)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e72b6-113">**Platforms:** See [.NET Core supported operating systems](../../../core/install/windows.md?pivots=os-windows).</span></span>
<span data-ttu-id="e72b6-114">**헤더:** Corprof.idl, Corprof.idl **.Net 버전:**[!INCLUDE[net_core](../../../../includes/net-core-50-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e72b6-114">**Header:** CorProf.idl, CorProf.h **.NET Versions:** [!INCLUDE[net_core](../../../../includes/net-core-50-md.md)]</span></span>
  
## <a name="see-also"></a><span data-ttu-id="e72b6-115">참조</span><span class="sxs-lookup"><span data-stu-id="e72b6-115">See also</span></span>

- [<span data-ttu-id="e72b6-116">EventPipe 개요</span><span class="sxs-lookup"><span data-stu-id="e72b6-116">EventPipe Overview</span></span>](../../../core/diagnostics/eventpipe.md)
- [<span data-ttu-id="e72b6-117">잘 알려진 EventProviders</span><span class="sxs-lookup"><span data-stu-id="e72b6-117">Well Known EventProviders</span></span>](../../../core/diagnostics/well-known-event-providers.md)
- [<span data-ttu-id="e72b6-118">프로파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e72b6-118">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="e72b6-119">ICorProfilerCallback10 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e72b6-119">ICorProfilerCallback10 Interface</span></span>](icorprofilercallback10-interface.md)
- [<span data-ttu-id="e72b6-120">ICorProfilerInfo12 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e72b6-120">ICorProfilerInfo12 Interface</span></span>](icorprofilerinfo12-interface.md)
