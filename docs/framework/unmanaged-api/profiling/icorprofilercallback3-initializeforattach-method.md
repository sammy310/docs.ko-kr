---
title: ICorProfilerCallback3::InitializeForAttach 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback3.InitializeForAttach Method
api_location:
- Mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback3::InitializeForAttach
helpviewer_keywords:
- InitializeForAttach method [.NET Framework profiling]
- ICorProfilerCallback3::InitializeForAttach method [.NET Framework profiling]
ms.assetid: bed097b3-6d52-46c9-bee7-ac7910b6fc3f
topic_type:
- apiref
ms.openlocfilehash: c85bba9a5d913820b69cbc214275b733a53197ee
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729449"
---
# <a name="icorprofilercallback3initializeforattach-method"></a><span data-ttu-id="b7741-102">ICorProfilerCallback3::InitializeForAttach 메서드</span><span class="sxs-lookup"><span data-stu-id="b7741-102">ICorProfilerCallback3::InitializeForAttach Method</span></span>

<span data-ttu-id="b7741-103">프로파일러가 연결 작업 후 상태를 초기화할 수 있도록 CLR(공용 언어 런타임)에 의해 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7741-103">Called by the common language runtime (CLR) to give the profiler an opportunity to initialize its state after an attach operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b7741-104">구문</span><span class="sxs-lookup"><span data-stu-id="b7741-104">Syntax</span></span>  
  
```cpp  
HRESULT InitializeForAttach(  
            [in] IUnknown * pCorProfilerInfoUnk,  
            [in] void * pvClientData,  
            [in] UINT cbClientData);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b7741-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b7741-105">Parameters</span></span>  

 `pCorProfilerInfoUnk`  
 <span data-ttu-id="b7741-106">[in] `ICorProfilerInfo*` 인터페이스에 대한 인터페이스 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="b7741-106">[in] An interface pointer for the `ICorProfilerInfo*` interface.</span></span>  
  
 `pvClientData`  
 <span data-ttu-id="b7741-107">진행 매개 변수에서 [IClrProfiling:: AttachProfiler](iclrprofiling-attachprofiler-method.md) 메서드에 전달 된 데이터에 대 한 포인터 `pvClientData` 입니다.</span><span class="sxs-lookup"><span data-stu-id="b7741-107">[in] A pointer to the data passed to the [IClrProfiling::AttachProfiler](iclrprofiling-attachprofiler-method.md) method in its `pvClientData` parameter.</span></span> <span data-ttu-id="b7741-108">이 매개 변수가 null일 경우 `cbClientData`는 0이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7741-108">If this parameter is null, `cbClientData` will be 0 (zero).</span></span> <span data-ttu-id="b7741-109">CLR은 `InitializeForAttach`에서 반환될 때 이 메모리를 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="b7741-109">The CLR frees this memory when it returns from `InitializeForAttach`.</span></span>  
  
 `cbClientData`  
 <span data-ttu-id="b7741-110">[in] `pvClientData`가 가리키는 데이터의 크기(바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="b7741-110">[in] The size, in bytes, of the data that `pvClientData` points to.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b7741-111">설명</span><span class="sxs-lookup"><span data-stu-id="b7741-111">Remarks</span></span>  

 <span data-ttu-id="b7741-112">CLR은 프로파일러가 콜백을 요청할 수 있도록 `InitializeForAttach`를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="b7741-112">The CLR calls `InitializeForAttach` to give the profiler an opportunity to request callbacks.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b7741-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b7741-113">Requirements</span></span>  

 <span data-ttu-id="b7741-114">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b7741-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b7741-115">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b7741-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b7741-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b7741-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b7741-117">**.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b7741-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7741-118">참조</span><span class="sxs-lookup"><span data-stu-id="b7741-118">See also</span></span>

- [<span data-ttu-id="b7741-119">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b7741-119">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="b7741-120">ICorProfilerInfo3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b7741-120">ICorProfilerInfo3 Interface</span></span>](icorprofilerinfo3-interface.md)
- [<span data-ttu-id="b7741-121">프로파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b7741-121">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="b7741-122">프로파일링</span><span class="sxs-lookup"><span data-stu-id="b7741-122">Profiling</span></span>](index.md)
