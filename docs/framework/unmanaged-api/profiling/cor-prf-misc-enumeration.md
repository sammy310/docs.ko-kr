---
title: COR_PRF_MISC 열거형
ms.date: 03/30/2017
api_name:
- COR_PRF_MISC
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_MISC
helpviewer_keywords:
- COR_PRF_MISC enumeration [.NET Framework profiling]
ms.assetid: 619bb5de-e309-48b6-a3af-32d935a0ff46
topic_type:
- apiref
ms.openlocfilehash: 8105ba34ca400771fbc4273630f20941a4a9557d
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74432283"
---
# <a name="cor_prf_misc-enumeration"></a><span data-ttu-id="ff1ff-102">COR_PRF_MISC 열거형</span><span class="sxs-lookup"><span data-stu-id="ff1ff-102">COR_PRF_MISC Enumeration</span></span>
<span data-ttu-id="ff1ff-103">특수 식별자를 지정하는 상수 값을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="ff1ff-103">Contains constant values that specify special identifiers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ff1ff-104">구문</span><span class="sxs-lookup"><span data-stu-id="ff1ff-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    PROFILER_PARENT_UNKNOWN = 0xFFFFFFFD,  
    PROFILER_GLOBAL_CLASS   = 0xFFFFFFFE,  
    PROFILER_GLOBAL_MODULE  = 0xFFFFFFFF  
} COR_PRF_MISC;  
```  
  
## <a name="members"></a><span data-ttu-id="ff1ff-105">멤버</span><span class="sxs-lookup"><span data-stu-id="ff1ff-105">Members</span></span>  
  
|<span data-ttu-id="ff1ff-106">멤버</span><span class="sxs-lookup"><span data-stu-id="ff1ff-106">Member</span></span>|<span data-ttu-id="ff1ff-107">설명</span><span class="sxs-lookup"><span data-stu-id="ff1ff-107">Description</span></span>|  
|------------|-----------------|  
|`PROFILER_PARENT_UNKNOWN`|<span data-ttu-id="ff1ff-108">The default identifier used by [ICorProfilerInfo::GetModuleInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getmoduleinfo-method.md) for a module that has not yet been attached to an assembly.</span><span class="sxs-lookup"><span data-stu-id="ff1ff-108">The default identifier used by [ICorProfilerInfo::GetModuleInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getmoduleinfo-method.md) for a module that has not yet been attached to an assembly.</span></span>|  
|`PROFILER_GLOBAL_CLASS`|<span data-ttu-id="ff1ff-109">The default class identifier for global constants that do not belong to a class.</span><span class="sxs-lookup"><span data-stu-id="ff1ff-109">The default class identifier for global constants that do not belong to a class.</span></span>|  
|`PROFILER_GLOBAL_MODULE`|<span data-ttu-id="ff1ff-110">The default module identifier for global objects that do not belong to a module.</span><span class="sxs-lookup"><span data-stu-id="ff1ff-110">The default module identifier for global objects that do not belong to a module.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ff1ff-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ff1ff-111">Requirements</span></span>  
 <span data-ttu-id="ff1ff-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ff1ff-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ff1ff-113">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ff1ff-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ff1ff-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ff1ff-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ff1ff-115">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ff1ff-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff1ff-116">참조</span><span class="sxs-lookup"><span data-stu-id="ff1ff-116">See also</span></span>

- [<span data-ttu-id="ff1ff-117">프로파일링 열거형</span><span class="sxs-lookup"><span data-stu-id="ff1ff-117">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
