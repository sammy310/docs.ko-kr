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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3b40ac5f49288f7b30018e0c8c727e3ce6b73ae8
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59199494"
---
# <a name="corprfmisc-enumeration"></a><span data-ttu-id="254f3-102">COR_PRF_MISC 열거형</span><span class="sxs-lookup"><span data-stu-id="254f3-102">COR_PRF_MISC Enumeration</span></span>
<span data-ttu-id="254f3-103">특수 식별자를 지정하는 상수 값을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="254f3-103">Contains constant values that specify special identifiers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="254f3-104">구문</span><span class="sxs-lookup"><span data-stu-id="254f3-104">Syntax</span></span>  
  
```  
typedef enum {  
    PROFILER_PARENT_UNKNOWN = 0xFFFFFFFD,  
    PROFILER_GLOBAL_CLASS   = 0xFFFFFFFE,  
    PROFILER_GLOBAL_MODULE  = 0xFFFFFFFF  
} COR_PRF_MISC;  
```  
  
## <a name="members"></a><span data-ttu-id="254f3-105">멤버</span><span class="sxs-lookup"><span data-stu-id="254f3-105">Members</span></span>  
  
|<span data-ttu-id="254f3-106">멤버</span><span class="sxs-lookup"><span data-stu-id="254f3-106">Member</span></span>|<span data-ttu-id="254f3-107">설명</span><span class="sxs-lookup"><span data-stu-id="254f3-107">Description</span></span>|  
|------------|-----------------|  
|`PROFILER_PARENT_UNKNOWN`|<span data-ttu-id="254f3-108">사용 되는 기본 식별자 [icorprofilerinfo:: Getmoduleinfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getmoduleinfo-method.md) 어셈블리에 아직 연결 되지 않은 모듈에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="254f3-108">The default identifier used by [ICorProfilerInfo::GetModuleInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getmoduleinfo-method.md) for a module that has not yet been attached to an assembly.</span></span>|  
|`PROFILER_GLOBAL_CLASS`|<span data-ttu-id="254f3-109">클래스에 속하지 않는 전역 상수에 대 한 기본 클래스 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="254f3-109">The default class identifier for global constants that do not belong to a class.</span></span>|  
|`PROFILER_GLOBAL_MODULE`|<span data-ttu-id="254f3-110">모듈에 속하지 않는 전역 개체에 대 한 기본 모듈 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="254f3-110">The default module identifier for global objects that do not belong to a module.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="254f3-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="254f3-111">Requirements</span></span>  
 <span data-ttu-id="254f3-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="254f3-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="254f3-113">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="254f3-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="254f3-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="254f3-114">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="254f3-115">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="254f3-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="254f3-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="254f3-116">See also</span></span>

- [<span data-ttu-id="254f3-117">프로파일링 열거형</span><span class="sxs-lookup"><span data-stu-id="254f3-117">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
