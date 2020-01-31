---
title: ICorProfilerInfo5 인터페이스
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo5
api_location:
- mscorwks.dll
api_type:
- COM
ms.assetid: 7bd48c34-37ed-4230-9eec-39a17280f05d
topic_type:
- apiref
ms.openlocfilehash: 655cdd5db0894a4e44d43b071caf1ee0829ffe50
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/29/2020
ms.locfileid: "76861725"
---
# <a name="icorprofilerinfo5-interface"></a><span data-ttu-id="3344d-102">ICorProfilerInfo5 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3344d-102">ICorProfilerInfo5 Interface</span></span>
<span data-ttu-id="3344d-103">[.NET Framework 4.5.2 이상 버전에서 지원됨]</span><span class="sxs-lookup"><span data-stu-id="3344d-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="3344d-104">코드 프로파일러가 CLR (공용 언어 런타임)과 통신 하 여 이벤트 모니터링을 제어 하는 데 사용할 메서드를 제공 하는 [ICorProfilerInfo4](icorprofilerinfo4-interface.md) 의 서브 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="3344d-104">A subclass of [ICorProfilerInfo4](icorprofilerinfo4-interface.md) that provides methods for use by code profilers to communicate with the common language runtime (CLR) to control event monitoring.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3344d-105">메서드</span><span class="sxs-lookup"><span data-stu-id="3344d-105">Methods</span></span>  
  
|<span data-ttu-id="3344d-106">메서드</span><span class="sxs-lookup"><span data-stu-id="3344d-106">Method</span></span>|<span data-ttu-id="3344d-107">설명</span><span class="sxs-lookup"><span data-stu-id="3344d-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3344d-108">GetEventMask2 메서드</span><span class="sxs-lookup"><span data-stu-id="3344d-108">GetEventMask2 Method</span></span>](icorprofilerinfo5-geteventmask2-method.md)|<span data-ttu-id="3344d-109">프로파일러가 CLR에서 알림을 받으려는 현재 이벤트 범주를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="3344d-109">Gets the current event categories for which the profiler wants to receive notifications from the CLR.</span></span>|  
|[<span data-ttu-id="3344d-110">SetEventMask2 메서드</span><span class="sxs-lookup"><span data-stu-id="3344d-110">SetEventMask2 Method</span></span>](icorprofilerinfo5-seteventmask2-method.md)|<span data-ttu-id="3344d-111">프로파일러가 CLR에서 이벤트 알림을 받으려는 이벤트 형식을 지정하는 값을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="3344d-111">Sets a value that specifies the types of events for which the profiler wants to receive event notifications from the CLR.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3344d-112">주의</span><span class="sxs-lookup"><span data-stu-id="3344d-112">Remarks</span></span>  
 <span data-ttu-id="3344d-113">이 인터페이스에서 사용할 수 있는 메서드는 [ICorProfilerInfo:: geteventmask](icorprofilerinfo-geteventmask-method.md) 및 [ICorProfilerInfo:: seteventmask](icorprofilerinfo-seteventmask-method.md) 메서드를 대체 하기 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="3344d-113">The methods available on this interface are intended to replace the [ICorProfilerInfo::GetEventMask](icorprofilerinfo-geteventmask-method.md) and [ICorProfilerInfo::SetEventMask](icorprofilerinfo-seteventmask-method.md) methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3344d-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3344d-114">Requirements</span></span>  
 <span data-ttu-id="3344d-115">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3344d-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3344d-116">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="3344d-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="3344d-117">**.NET Framework 버전:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3344d-117">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3344d-118">참조</span><span class="sxs-lookup"><span data-stu-id="3344d-118">See also</span></span>

- [<span data-ttu-id="3344d-119">프로파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3344d-119">Profiling Interfaces</span></span>](profiling-interfaces.md)
