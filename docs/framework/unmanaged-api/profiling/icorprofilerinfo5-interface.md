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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5b249605833e8fbd219495ab92bebc2eff6177eb
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59094257"
---
# <a name="icorprofilerinfo5-interface"></a><span data-ttu-id="7e64c-102">ICorProfilerInfo5 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7e64c-102">ICorProfilerInfo5 Interface</span></span>
<span data-ttu-id="7e64c-103">[.NET Framework 4.5.2 이상 버전에서 지원됨]</span><span class="sxs-lookup"><span data-stu-id="7e64c-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="7e64c-104">서브 클래스 [ICorProfilerInfo4](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md) 코드 프로파일러는 CLR (공용 언어 런타임) 이벤트 모니터링을 제어 하려면와 통신 하 여 사용할 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e64c-104">A subclass of [ICorProfilerInfo4](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md) that provides methods for use by code profilers to communicate with the common language runtime (CLR) to control event monitoring.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="7e64c-105">메서드</span><span class="sxs-lookup"><span data-stu-id="7e64c-105">Methods</span></span>  
  
|<span data-ttu-id="7e64c-106">메서드</span><span class="sxs-lookup"><span data-stu-id="7e64c-106">Method</span></span>|<span data-ttu-id="7e64c-107">설명</span><span class="sxs-lookup"><span data-stu-id="7e64c-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="7e64c-108">GetEventMask2 메서드</span><span class="sxs-lookup"><span data-stu-id="7e64c-108">GetEventMask2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-geteventmask2-method.md)|<span data-ttu-id="7e64c-109">프로파일러가 CLR에서 알림을 받으려는 현재 이벤트 범주를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="7e64c-109">Gets the current event categories for which the profiler wants to receive notifications from the CLR.</span></span>|  
|[<span data-ttu-id="7e64c-110">SetEventMask2 메서드</span><span class="sxs-lookup"><span data-stu-id="7e64c-110">SetEventMask2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md)|<span data-ttu-id="7e64c-111">프로파일러가 CLR에서 이벤트 알림을 받으려는 이벤트 형식을 지정하는 값을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="7e64c-111">Sets a value that specifies the types of events for which the profiler wants to receive event notifications from the CLR.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7e64c-112">설명</span><span class="sxs-lookup"><span data-stu-id="7e64c-112">Remarks</span></span>  
 <span data-ttu-id="7e64c-113">이 인터페이스에서 사용할 수 있는 방법을 대체 하기 위한은 [icorprofilerinfo:: Geteventmask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-geteventmask-method.md) 하 고 [icorprofilerinfo:: Seteventmask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="7e64c-113">The methods available on this interface are intended to replace the [ICorProfilerInfo::GetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-geteventmask-method.md) and [ICorProfilerInfo::SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7e64c-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7e64c-114">Requirements</span></span>  
 <span data-ttu-id="7e64c-115">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="7e64c-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7e64c-116">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="7e64c-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="7e64c-117">**.NET Framework 버전:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7e64c-117">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e64c-118">참고자료</span><span class="sxs-lookup"><span data-stu-id="7e64c-118">See also</span></span>

- [<span data-ttu-id="7e64c-119">프로파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7e64c-119">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
