---
title: COR_PRF_REJIT_FLAGS 열거형
ms.date: 08/06/2019
api_name:
- COR_PRF_REJIT_FLAGS Enumeration
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_REJIT_FLAGS
helpviewer_keywords:
- COR_PRF_REJIT_FLAGS enumeration [.NET Framework profiling]
topic_type:
- apiref
author: davmason
ms.author: davmason
ms.openlocfilehash: 66933b3778807b40f1d39d8b4c565c334328812f
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74450395"
---
# <a name="cor_prf_rejit_flags-enumeration"></a><span data-ttu-id="63868-102">COR_PRF_REJIT_FLAGS 열거형</span><span class="sxs-lookup"><span data-stu-id="63868-102">COR_PRF_REJIT_FLAGS Enumeration</span></span>
<span data-ttu-id="63868-103">[ICorProfilerInfo10:: RequestReJITWithInliners](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-requestrejitwithinliners-method.md) API가 동작 하는 방법을 나타내는 값을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="63868-103">Contains values that indicate how the [ICorProfilerInfo10::RequestReJITWithInliners](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-requestrejitwithinliners-method.md) API should behave.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="63868-104">구문</span><span class="sxs-lookup"><span data-stu-id="63868-104">Syntax</span></span>  
  
```cpp  
typedef enum  
{      
    COR_PRF_REJIT_BLOCK_INLINING = 0x1,
    COR_PRF_REJIT_INLINING_CALLBACKS    = 0x2
} COR_PRF_REJIT_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="63868-105">멤버</span><span class="sxs-lookup"><span data-stu-id="63868-105">Members</span></span>  
  
|<span data-ttu-id="63868-106">멤버</span><span class="sxs-lookup"><span data-stu-id="63868-106">Member</span></span>|<span data-ttu-id="63868-107">설명</span><span class="sxs-lookup"><span data-stu-id="63868-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_REJIT_BLOCK_INLINING`| <span data-ttu-id="63868-108">ReJITted 메서드는 다른 메서드에서 인라인 되지 않도록 차단 됩니다.</span><span class="sxs-lookup"><span data-stu-id="63868-108">ReJITted methods will be blocked from being inlined in other methods.</span></span> |  
|`COR_PRF_REJIT_INLINING_CALLBACKS`| <span data-ttu-id="63868-109">ReJITted 하도록 요청 된 메서드를 인라인 하는 모든 메서드에 대 한 `GetFunctionParameters` 콜백을 수신 합니다.</span><span class="sxs-lookup"><span data-stu-id="63868-109">Receive `GetFunctionParameters` callbacks for any methods that inline the methods requested to be ReJITted.</span></span> |  

## <a name="requirements"></a><span data-ttu-id="63868-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="63868-110">Requirements</span></span>  
 <span data-ttu-id="63868-111">**플랫폼:** [.Net Core 지원 운영 체제](../../../core/install/dependencies.md?tabs=netcore30&pivots=os-windows)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="63868-111">**Platforms:** See [.NET Core supported operating systems](../../../core/install/dependencies.md?tabs=netcore30&pivots=os-windows).</span></span>  
  
 <span data-ttu-id="63868-112">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="63868-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="63868-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="63868-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="63868-114">**.NET Framework 버전:** [!INCLUDE[net_core_22](../../../../includes/net-core-22-md.md)]</span><span class="sxs-lookup"><span data-stu-id="63868-114">**.NET Framework Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-22-md.md)]</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="63868-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="63868-115">See also</span></span>

- [<span data-ttu-id="63868-116">프로파일링 열거형</span><span class="sxs-lookup"><span data-stu-id="63868-116">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
