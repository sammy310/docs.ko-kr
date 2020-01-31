---
title: ICorProfilerModuleEnum 인터페이스
ms.date: 03/30/2017
api_name:
- ICorProfilerModuleEnum
api_location:
- mscorwks.cll
api_type:
- COM
f1_keywords:
- ICorProfilerModuleEnum
helpviewer_keywords:
- ICorProfilerModuleEnum interface [.NET Framework profiling]
ms.assetid: 24d0fcfa-1601-4fba-868f-da8c97303467
topic_type:
- apiref
ms.openlocfilehash: 2713fa90240cb0bf41f455b6ed65d76c568a2cf8
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868267"
---
# <a name="icorprofilermoduleenum-interface"></a><span data-ttu-id="40f62-102">ICorProfilerModuleEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="40f62-102">ICorProfilerModuleEnum Interface</span></span>
<span data-ttu-id="40f62-103">애플리케이션이나 프로파일러가 로드한 모듈 컬렉션을 순서대로 반복하는 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="40f62-103">Provides methods to sequentially iterate through a collection of modules loaded by the application or the profiler.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="40f62-104">메서드</span><span class="sxs-lookup"><span data-stu-id="40f62-104">Methods</span></span>  
  
|<span data-ttu-id="40f62-105">메서드</span><span class="sxs-lookup"><span data-stu-id="40f62-105">Method</span></span>|<span data-ttu-id="40f62-106">설명</span><span class="sxs-lookup"><span data-stu-id="40f62-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="40f62-107">Clone 메서드</span><span class="sxs-lookup"><span data-stu-id="40f62-107">Clone Method</span></span>](icorprofilermoduleenum-clone-method.md)|<span data-ttu-id="40f62-108">이 `ICorProfilerModuleEnum` 인터페이스의 복사본에 대한 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="40f62-108">Gets an interface pointer to a copy of this `ICorProfilerModuleEnum` interface.</span></span>|  
|[<span data-ttu-id="40f62-109">GetCount 메서드</span><span class="sxs-lookup"><span data-stu-id="40f62-109">GetCount Method</span></span>](icorprofilermoduleenum-getcount-method.md)|<span data-ttu-id="40f62-110">애플리케이션에 로드된 관리되는 모듈 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="40f62-110">Gets the number of managed modules that were loaded into the application.</span></span>|  
|[<span data-ttu-id="40f62-111">Next 메서드</span><span class="sxs-lookup"><span data-stu-id="40f62-111">Next Method</span></span>](icorprofilermoduleenum-next-method.md)|<span data-ttu-id="40f62-112">시퀀스에서 열거자의 현재 위치부터 시작하여 순차적 개체 컬렉션에서 지정된 개수의 연속 모듈을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="40f62-112">Gets the specified number of contiguous modules from a sequential collection of objects, starting at the enumerator's current position in the sequence.</span></span>|  
|[<span data-ttu-id="40f62-113">Reset 메서드</span><span class="sxs-lookup"><span data-stu-id="40f62-113">Reset Method</span></span>](icorprofilermoduleenum-reset-method.md)|<span data-ttu-id="40f62-114">열거자의 커서를 시퀀스의 시작 위치로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="40f62-114">Moves the enumerator's cursor to the starting position of the sequence.</span></span>|  
|[<span data-ttu-id="40f62-115">Skip 메서드</span><span class="sxs-lookup"><span data-stu-id="40f62-115">Skip Method</span></span>](icorprofilermoduleenum-skip-method.md)|<span data-ttu-id="40f62-116">지정한 개수의 요소를 건너뛰도록 열거자의 커서 위치를 진행합니다.</span><span class="sxs-lookup"><span data-stu-id="40f62-116">Advances the position of the enumerator's cursor so that the specified number of elements are skipped.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="40f62-117">주의</span><span class="sxs-lookup"><span data-stu-id="40f62-117">Remarks</span></span>  
 <span data-ttu-id="40f62-118">`ICorProfilerModuleEnum` 인터페이스는 열거자입니다.</span><span class="sxs-lookup"><span data-stu-id="40f62-118">The `ICorProfilerModuleEnum` interface is an enumerator.</span></span> <span data-ttu-id="40f62-119">배열의 수신기가 수신기에 적합한 속도로 송신기에서 요소를 끌어올 수 있게 합니다.</span><span class="sxs-lookup"><span data-stu-id="40f62-119">It allows the receiver of an array to pull elements from the sender at a rate that is appropriate for the receiver.</span></span> <span data-ttu-id="40f62-120">즉, 수신기가 배열 요소의 흐름을 명시적으로 제어하여 대형 배열을 메서드 매개 변수로 전달하는 기능과 관련된 문제를 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="40f62-120">In other words, the receiver is able to explicitly control the flow of array elements, thereby avoiding the problems associated with passing large arrays as method parameters.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="40f62-121">요구 사항</span><span class="sxs-lookup"><span data-stu-id="40f62-121">Requirements</span></span>  
 <span data-ttu-id="40f62-122">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="40f62-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="40f62-123">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="40f62-123">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="40f62-124">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="40f62-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="40f62-125">**.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="40f62-125">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40f62-126">참조</span><span class="sxs-lookup"><span data-stu-id="40f62-126">See also</span></span>

- [<span data-ttu-id="40f62-127">ICorProfilerInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="40f62-127">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="40f62-128">프로파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="40f62-128">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="40f62-129">EnumModules 메서드</span><span class="sxs-lookup"><span data-stu-id="40f62-129">EnumModules Method</span></span>](icorprofilerinfo3-enummodules-method.md)
