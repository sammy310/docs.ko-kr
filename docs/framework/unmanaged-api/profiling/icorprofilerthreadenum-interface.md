---
description: '자세히 알아보기: ICorProfilerThreadEnum 인터페이스'
title: ICorProfilerThreadEnum 인터페이스
ms.date: 03/30/2017
api_name:
- ICorProfilerThreadEnum
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerThreadEnum
helpviewer_keywords:
- ICorProfilerThreadEnum interface [.NET Framework profiling]
ms.assetid: 1e35031b-e095-4c14-9644-8deeb3081e0b
topic_type:
- apiref
ms.openlocfilehash: 035296412aabf20503588a558c8e8ccc1338210e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99636392"
---
# <a name="icorprofilerthreadenum-interface"></a><span data-ttu-id="7785f-103">ICorProfilerThreadEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7785f-103">ICorProfilerThreadEnum Interface</span></span>

<span data-ttu-id="7785f-104">공용 언어 런타임에서 스레드 컬렉션을 순차적으로 반복하는 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="7785f-104">Provides methods to sequentially iterate through a collection of threads in the common language runtime.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="7785f-105">메서드</span><span class="sxs-lookup"><span data-stu-id="7785f-105">Methods</span></span>  
  
|<span data-ttu-id="7785f-106">메서드</span><span class="sxs-lookup"><span data-stu-id="7785f-106">Method</span></span>|<span data-ttu-id="7785f-107">설명</span><span class="sxs-lookup"><span data-stu-id="7785f-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="7785f-108">Clone 메서드</span><span class="sxs-lookup"><span data-stu-id="7785f-108">Clone Method</span></span>](icorprofilerthreadenum-clone-method.md)|<span data-ttu-id="7785f-109">이 `ICorProfilerThreadEnum` 인터페이스의 복사본에 대한 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="7785f-109">Gets an interface pointer to a copy of this `ICorProfilerThreadEnum` interface.</span></span>|  
|[<span data-ttu-id="7785f-110">GetCount 메서드</span><span class="sxs-lookup"><span data-stu-id="7785f-110">GetCount Method</span></span>](icorprofilerthreadenum-getcount-method.md)|<span data-ttu-id="7785f-111">애플리케이션에서 사용하는 스레드 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="7785f-111">Gets the number of threads that are used by the application.</span></span>|  
|[<span data-ttu-id="7785f-112">Next 메서드</span><span class="sxs-lookup"><span data-stu-id="7785f-112">Next Method</span></span>](icorprofilerthreadenum-next-method.md)|<span data-ttu-id="7785f-113">시퀀스에서 열거자의 현재 위치부터 시작하여 순차적 스레드 컬렉션에서 지정된 개수의 연속 스레드를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="7785f-113">Gets the specified number of contiguous threads from a sequential collection of threads, starting at the enumerator's current position in the sequence.</span></span>|  
|[<span data-ttu-id="7785f-114">Reset 메서드</span><span class="sxs-lookup"><span data-stu-id="7785f-114">Reset Method</span></span>](icorprofilerthreadenum-reset-method.md)|<span data-ttu-id="7785f-115">열거자의 커서를 시퀀스의 시작 위치로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="7785f-115">Moves the enumerator's cursor to the starting position of the sequence.</span></span>|  
|[<span data-ttu-id="7785f-116">Skip 메서드</span><span class="sxs-lookup"><span data-stu-id="7785f-116">Skip Method</span></span>](icorprofilerthreadenum-skip-method.md)|<span data-ttu-id="7785f-117">지정한 개수의 요소를 건너뛰도록 현재 위치에서 열거자의 커서를 진행합니다.</span><span class="sxs-lookup"><span data-stu-id="7785f-117">Advances the enumerator's cursor from its current position to skip the specified number of elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7785f-118">설명</span><span class="sxs-lookup"><span data-stu-id="7785f-118">Remarks</span></span>  

 <span data-ttu-id="7785f-119">`ICorProfilerThreadEnum` 인터페이스는 열거자입니다.</span><span class="sxs-lookup"><span data-stu-id="7785f-119">The `ICorProfilerThreadEnum` interface is an enumerator.</span></span> <span data-ttu-id="7785f-120">배열의 수신기가 수신기에 적합한 속도로 송신기에서 요소를 끌어올 수 있게 합니다.</span><span class="sxs-lookup"><span data-stu-id="7785f-120">It allows the receiver of an array to pull elements from the sender at a rate that is appropriate for the receiver.</span></span> <span data-ttu-id="7785f-121">즉, 수신기가 배열 요소의 흐름을 명시적으로 제어하여 대형 배열을 메서드 매개 변수로 전달하는 기능과 관련된 문제를 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7785f-121">In other words, the receiver is able to explicitly control the flow of array elements, thereby avoiding the problems associated with passing large arrays as method parameters.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7785f-122">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7785f-122">Requirements</span></span>  

 <span data-ttu-id="7785f-123">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7785f-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7785f-124">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="7785f-124">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="7785f-125">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7785f-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7785f-126">**.NET Framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7785f-126">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7785f-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7785f-127">See also</span></span>

- [<span data-ttu-id="7785f-128">ICorProfilerInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7785f-128">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="7785f-129">프로파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7785f-129">Profiling Interfaces</span></span>](profiling-interfaces.md)
