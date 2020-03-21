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
ms.openlocfilehash: 8fc5f1a488826d8adc6aecb8ef122609bebbe813
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177092"
---
# <a name="cor_prf_rejit_flags-enumeration"></a><span data-ttu-id="44995-102">COR_PRF_REJIT_FLAGS 열거형</span><span class="sxs-lookup"><span data-stu-id="44995-102">COR_PRF_REJIT_FLAGS Enumeration</span></span>
<span data-ttu-id="44995-103">[ICorProfilerInfo10:::RequestReJITWithInliners](icorprofilerinfo10-requestrejitwithinliners-method.md) API가 어떻게 작동해야 하는지 나타내는 값을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="44995-103">Contains values that indicate how the [ICorProfilerInfo10::RequestReJITWithInliners](icorprofilerinfo10-requestrejitwithinliners-method.md) API should behave.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="44995-104">구문</span><span class="sxs-lookup"><span data-stu-id="44995-104">Syntax</span></span>  
  
```cpp  
typedef enum  
{
    COR_PRF_REJIT_BLOCK_INLINING = 0x1,
    COR_PRF_REJIT_INLINING_CALLBACKS    = 0x2
} COR_PRF_REJIT_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="44995-105">구성원</span><span class="sxs-lookup"><span data-stu-id="44995-105">Members</span></span>  
  
|<span data-ttu-id="44995-106">멤버</span><span class="sxs-lookup"><span data-stu-id="44995-106">Member</span></span>|<span data-ttu-id="44995-107">Description</span><span class="sxs-lookup"><span data-stu-id="44995-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_REJIT_BLOCK_INLINING`| <span data-ttu-id="44995-108">ReJITted 메서드는 다른 메서드에서 인라인되는 것을 차단합니다.</span><span class="sxs-lookup"><span data-stu-id="44995-108">ReJITted methods will be blocked from being inlined in other methods.</span></span> |  
|`COR_PRF_REJIT_INLINING_CALLBACKS`| <span data-ttu-id="44995-109">ReJITted에 요청된 메서드를 인라인으로 하는 메서드에 대한 콜백을 받습니다. `GetFunctionParameters`</span><span class="sxs-lookup"><span data-stu-id="44995-109">Receive `GetFunctionParameters` callbacks for any methods that inline the methods requested to be ReJITted.</span></span> |  

## <a name="requirements"></a><span data-ttu-id="44995-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="44995-110">Requirements</span></span>  
 <span data-ttu-id="44995-111">**플랫폼:** [.NET Core 지원 운영 체제를](../../../core/install/dependencies.md?pivots=os-windows)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="44995-111">**Platforms:** See [.NET Core supported operating systems](../../../core/install/dependencies.md?pivots=os-windows).</span></span>  
  
 <span data-ttu-id="44995-112">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="44995-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="44995-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="44995-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="44995-114">**.NET Framework 버전:** [!INCLUDE[net_core_22](../../../../includes/net-core-22-md.md)]</span><span class="sxs-lookup"><span data-stu-id="44995-114">**.NET Framework Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-22-md.md)]</span></span>
  
## <a name="see-also"></a><span data-ttu-id="44995-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="44995-115">See also</span></span>

- [<span data-ttu-id="44995-116">프로파일링 열거형</span><span class="sxs-lookup"><span data-stu-id="44995-116">Profiling Enumerations</span></span>](profiling-enumerations.md)
