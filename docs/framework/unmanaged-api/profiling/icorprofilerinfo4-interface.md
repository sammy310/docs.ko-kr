---
title: ICorProfilerInfo4 인터페이스
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo4
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo4
helpviewer_keywords:
- ICorProfilerInfo4 interface [.NET Framework profiling]
ms.assetid: 80a5308e-c22f-4201-ba89-31cc8562515b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 177e5ef8054f408dc8ec3475c56043394a636bc0
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59194216"
---
# <a name="icorprofilerinfo4-interface"></a><span data-ttu-id="77f02-102">ICorProfilerInfo4 인터페이스</span><span class="sxs-lookup"><span data-stu-id="77f02-102">ICorProfilerInfo4 Interface</span></span>
<span data-ttu-id="77f02-103">코드 프로파일러가 CLR (공용 언어 런타임) 이벤트 모니터링을 제어 하 고 요청 정보를 사용 하 여 통신에 사용 되는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="77f02-103">Provides methods that code profilers use to communicate with the common language runtime (CLR) to control event monitoring and request information.</span></span> <span data-ttu-id="77f02-104">.</span><span class="sxs-lookup"><span data-stu-id="77f02-104">.</span></span> <span data-ttu-id="77f02-105">합니다 `ICorProfilerInfo4` 인터페이스는 다른 확장 `ICorProfilerInfo` 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="77f02-105">The `ICorProfilerInfo4` interface is an extension of the other `ICorProfilerInfo` interfaces.</span></span> <span data-ttu-id="77f02-106">추가 시간 (JIT) 컴파일을 지원 하기 위해 새 메서드를 제공 합니다 [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="77f02-106">It provides new methods to support just-in-time (JIT) recompilation, added in the [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)].</span></span>  
  
## <a name="methods"></a><span data-ttu-id="77f02-107">메서드</span><span class="sxs-lookup"><span data-stu-id="77f02-107">Methods</span></span>  
  
|<span data-ttu-id="77f02-108">메서드</span><span class="sxs-lookup"><span data-stu-id="77f02-108">Method</span></span>|<span data-ttu-id="77f02-109">설명</span><span class="sxs-lookup"><span data-stu-id="77f02-109">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="77f02-110">EnumJITedFunctions2 메서드</span><span class="sxs-lookup"><span data-stu-id="77f02-110">EnumJITedFunctions2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-enumjitedfunctions2-method.md)|<span data-ttu-id="77f02-111">JIT로 컴파일되고 JIT 다시 컴파일된 이전에 있던 모든 함수에 대 한 열거자를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="77f02-111">Returns an enumerator for all functions that were previously JIT-compiled and JIT-recompiled.</span></span>|  
|[<span data-ttu-id="77f02-112">EnumThreads 메서드</span><span class="sxs-lookup"><span data-stu-id="77f02-112">EnumThreads Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-enumthreads-method.md)|<span data-ttu-id="77f02-113">프로 파일링된 된 프로세스의 모든 관리 되는 스레드 컬렉션을 순차적으로 반복 하는 메서드를 제공 하는 열거자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="77f02-113">Gets an enumerator that provides methods to sequentially iterate through the collection of all managed threads in the profiled process.</span></span>|  
|[<span data-ttu-id="77f02-114">GetCodeInfo3 메서드</span><span class="sxs-lookup"><span data-stu-id="77f02-114">GetCodeInfo3 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-getcodeinfo3-method.md)|<span data-ttu-id="77f02-115">지정된 함수의 JIT 다시 컴파일된 버전과 연결된 네이티브 코드의 범위를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="77f02-115">Gets the extents of native code associated with the JIT-recompiled version of the specified function.</span></span>|  
|[<span data-ttu-id="77f02-116">GetFunctionFromIP2 메서드</span><span class="sxs-lookup"><span data-stu-id="77f02-116">GetFunctionFromIP2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-getfunctionfromip2-method.md)|<span data-ttu-id="77f02-117">지정 된 함수의 JIT 다시 컴파일된 버전으로 관리 되는 코드 명령 포인터를 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="77f02-117">Maps a managed code instruction pointer to the JIT-recompiled version of a specified function.</span></span>|  
|[<span data-ttu-id="77f02-118">GetILToNativeMapping2 메서드</span><span class="sxs-lookup"><span data-stu-id="77f02-118">GetILToNativeMapping2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-getiltonativemapping2-method.md)|<span data-ttu-id="77f02-119">MSIL (intermediate language) 오프셋과 네이티브 오프셋 간의 지정 된 함수의 JIT 다시 컴파일된 버전에 포함 된 코드에 대 한 Microsoft의 맵을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="77f02-119">Gets a map from Microsoft intermediate language (MSIL) offsets to native offsets for the code contained in the JIT-recompiled version of the specified function .</span></span>|  
|[<span data-ttu-id="77f02-120">GetObjectSize2 메서드</span><span class="sxs-lookup"><span data-stu-id="77f02-120">GetObjectSize2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-getobjectsize2-method.md)|<span data-ttu-id="77f02-121">지정된 된 개체의 크기를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="77f02-121">Returns the size of a specified object.</span></span>|  
|[<span data-ttu-id="77f02-122">GetReJITIDs 메서드</span><span class="sxs-lookup"><span data-stu-id="77f02-122">GetReJITIDs Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-getrejitids-method.md)|<span data-ttu-id="77f02-123">모든 JIT 다시 컴파일된 버전의 지정 된 함수가 여전히 할당 되는 식별 하는 Id의 배열을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="77f02-123">Returns an array of IDs that identify all JIT-recompiled versions of the specified function that are still allocated.</span></span>|  
|[<span data-ttu-id="77f02-124">InitializeCurrentThread 메서드</span><span class="sxs-lookup"><span data-stu-id="77f02-124">InitializeCurrentThread Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-initializecurrentthread-method.md)|<span data-ttu-id="77f02-125">후속 프로파일러 해당 교착 상태를 방지할 수 있도록 동일한 스레드에서 API 호출 하기 전에 현재 스레드를 초기화 합니다.</span><span class="sxs-lookup"><span data-stu-id="77f02-125">Initializes the current thread in advance of subsequent profiler API calls on the same thread, so that deadlock can be avoided.</span></span>|  
|[<span data-ttu-id="77f02-126">RequestReJIT 메서드</span><span class="sxs-lookup"><span data-stu-id="77f02-126">RequestReJIT Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-requestrejit-method.md)|<span data-ttu-id="77f02-127">지정된 함수의 모든 인스턴스에 대한 JIT 다시 컴파일을 요청합니다.</span><span class="sxs-lookup"><span data-stu-id="77f02-127">Requests a JIT recompilation of all instances of the specified functions.</span></span>|  
|[<span data-ttu-id="77f02-128">RequestRevert 메서드</span><span class="sxs-lookup"><span data-stu-id="77f02-128">RequestRevert Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-requestrevert-method.md)|<span data-ttu-id="77f02-129">지정된 함수의 모든 인스턴스를 원래 버전으로 되돌립니다.</span><span class="sxs-lookup"><span data-stu-id="77f02-129">Reverts all instances of the specified functions to their original versions.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="77f02-130">설명</span><span class="sxs-lookup"><span data-stu-id="77f02-130">Remarks</span></span>  
 <span data-ttu-id="77f02-131">CLR은 자유 스레드 모델을 사용하여 `ICorProfilerInfo4` 인터페이스의 메서드를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="77f02-131">The CLR implements the methods of the `ICorProfilerInfo4` interface by using the free-threaded model.</span></span> <span data-ttu-id="77f02-132">각 메서드가 HRESULT를 반환하여 성공 또는 실패를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="77f02-132">Each method returns an HRESULT to indicate success or failure.</span></span> <span data-ttu-id="77f02-133">가능한 반환 코드 목록은 CorError.h 파일을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="77f02-133">For a list of possible return codes, see the CorError.h file.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="77f02-134">요구 사항</span><span class="sxs-lookup"><span data-stu-id="77f02-134">Requirements</span></span>  
 <span data-ttu-id="77f02-135">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="77f02-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="77f02-136">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="77f02-136">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="77f02-137">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="77f02-137">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="77f02-138">**.NET Framework 버전:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="77f02-138">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77f02-139">참고자료</span><span class="sxs-lookup"><span data-stu-id="77f02-139">See also</span></span>

- [<span data-ttu-id="77f02-140">프로파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="77f02-140">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="77f02-141">ICorProfilerInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="77f02-141">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
