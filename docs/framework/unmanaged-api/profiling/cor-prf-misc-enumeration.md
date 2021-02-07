---
description: '다음에 대 한 자세한 정보: 열거형 COR_PRF_MISC'
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
ms.openlocfilehash: 037ea040dfdf9f5be48369ab4d8e94b12aea51ff
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99687599"
---
# <a name="cor_prf_misc-enumeration"></a><span data-ttu-id="38b4c-103">COR_PRF_MISC 열거형</span><span class="sxs-lookup"><span data-stu-id="38b4c-103">COR_PRF_MISC Enumeration</span></span>

<span data-ttu-id="38b4c-104">특수 식별자를 지정하는 상수 값을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="38b4c-104">Contains constant values that specify special identifiers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="38b4c-105">구문</span><span class="sxs-lookup"><span data-stu-id="38b4c-105">Syntax</span></span>  
  
```cpp  
typedef enum {  
    PROFILER_PARENT_UNKNOWN = 0xFFFFFFFD,  
    PROFILER_GLOBAL_CLASS   = 0xFFFFFFFE,  
    PROFILER_GLOBAL_MODULE  = 0xFFFFFFFF  
} COR_PRF_MISC;  
```  
  
## <a name="members"></a><span data-ttu-id="38b4c-106">구성원</span><span class="sxs-lookup"><span data-stu-id="38b4c-106">Members</span></span>  
  
|<span data-ttu-id="38b4c-107">멤버</span><span class="sxs-lookup"><span data-stu-id="38b4c-107">Member</span></span>|<span data-ttu-id="38b4c-108">설명</span><span class="sxs-lookup"><span data-stu-id="38b4c-108">Description</span></span>|  
|------------|-----------------|  
|`PROFILER_PARENT_UNKNOWN`|<span data-ttu-id="38b4c-109">아직 어셈블리에 연결 되지 않은 모듈에 대해 [ICorProfilerInfo:: GetModuleInfo](icorprofilerinfo-getmoduleinfo-method.md) 에서 사용 하는 기본 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="38b4c-109">The default identifier used by [ICorProfilerInfo::GetModuleInfo](icorprofilerinfo-getmoduleinfo-method.md) for a module that has not yet been attached to an assembly.</span></span>|  
|`PROFILER_GLOBAL_CLASS`|<span data-ttu-id="38b4c-110">클래스에 속하지 않는 전역 상수에 대 한 기본 클래스 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="38b4c-110">The default class identifier for global constants that do not belong to a class.</span></span>|  
|`PROFILER_GLOBAL_MODULE`|<span data-ttu-id="38b4c-111">모듈에 속하지 않는 전역 개체에 대 한 기본 모듈 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="38b4c-111">The default module identifier for global objects that do not belong to a module.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="38b4c-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="38b4c-112">Requirements</span></span>  

 <span data-ttu-id="38b4c-113">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="38b4c-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="38b4c-114">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="38b4c-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="38b4c-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="38b4c-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="38b4c-116">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="38b4c-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38b4c-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="38b4c-117">See also</span></span>

- [<span data-ttu-id="38b4c-118">프로파일링 열거형</span><span class="sxs-lookup"><span data-stu-id="38b4c-118">Profiling Enumerations</span></span>](profiling-enumerations.md)
