---
title: COR_PRF_SNAPSHOT_INFO 열거형
ms.date: 03/30/2017
api_name:
- COR_PRF_SNAPSHOT_INFO
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_SNAPSHOT_INFO
helpviewer_keywords:
- COR_PRF_SNAPSHOT_INFO enumeration [.NET Framework profiling]
ms.assetid: a5906b2a-ad4a-4cc6-a421-2d7d8adf7468
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: fa85fb2cebb47ecbd7b0f091cb79f6ea0936b1cb
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59177842"
---
# <a name="corprfsnapshotinfo-enumeration"></a><span data-ttu-id="5f81c-102">COR_PRF_SNAPSHOT_INFO 열거형</span><span class="sxs-lookup"><span data-stu-id="5f81c-102">COR_PRF_SNAPSHOT_INFO Enumeration</span></span>
<span data-ttu-id="5f81c-103">얼마나 프로파일러의 각 호출 스택의 스냅숏을 사용 하 여 다시 전달할 데이터 지정 [StackSnapshotCallback](../../../../docs/framework/unmanaged-api/profiling/stacksnapshotcallback-function.md) 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="5f81c-103">Specifies how much data to pass back with a stack snapshot in each call to the profiler's [StackSnapshotCallback](../../../../docs/framework/unmanaged-api/profiling/stacksnapshotcallback-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5f81c-104">구문</span><span class="sxs-lookup"><span data-stu-id="5f81c-104">Syntax</span></span>  
  
```  
typedef enum _COR_PRF_SNAPSHOT_INFO {  
    COR_PRF_SNAPSHOT_DEFAULT = 0x0,  
    COR_PRF_SNAPSHOT_REGISTER_CONTEXT = 0x1,  
    COR_PRF_SNAPSHOT_X86_OPTIMIZED = 0X2  
} COR_PRF_SNAPSHOT_INFO;  
```  
  
## <a name="members"></a><span data-ttu-id="5f81c-105">멤버</span><span class="sxs-lookup"><span data-stu-id="5f81c-105">Members</span></span>  
  
|<span data-ttu-id="5f81c-106">멤버</span><span class="sxs-lookup"><span data-stu-id="5f81c-106">Members</span></span>|<span data-ttu-id="5f81c-107">설명</span><span class="sxs-lookup"><span data-stu-id="5f81c-107">Description</span></span>|  
|-------------|-----------------|  
|`COR_PRF_SNAPSHOT_DEFAULT`|<span data-ttu-id="5f81c-108">모든 값을 전달 해야 나타냅니다 `StackSnapshotCallback` 매개 변수를 제외 하 고는 `context` 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="5f81c-108">Indicates that values must be passed for all `StackSnapshotCallback` parameters, except the `context` parameter.</span></span>|  
|`COR_PRF_SNAPSHOT_REGISTER_CONTEXT`|<span data-ttu-id="5f81c-109">모든 값을 전달 해야 나타냅니다 `StackSnapshotCallback` 매개 변수를 포함 하 여는 `context` 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="5f81c-109">Indicates that values must be passed for all `StackSnapshotCallback` parameters, including the `context` parameter.</span></span>|  
|`COR_PRF_SNAPSHOT_X86_OPTIMIZED`|<span data-ttu-id="5f81c-110">간단 하 고 대체 스택 워킹 알고리즘 사용 됨을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="5f81c-110">Indicates that a simpler, alternative stack-walking algorithm will be used.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5f81c-111">설명</span><span class="sxs-lookup"><span data-stu-id="5f81c-111">Remarks</span></span>  
 <span data-ttu-id="5f81c-112">제공 하는 값을 `COR_PRF_SNAPSHOT_INFO` 열거형을 매개 변수로 전달 되는 [DoStackSnapshot](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="5f81c-112">Values that are provided by the `COR_PRF_SNAPSHOT_INFO` enumeration are passed as parameters to the [DoStackSnapshot](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5f81c-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5f81c-113">Requirements</span></span>  
 <span data-ttu-id="5f81c-114">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="5f81c-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5f81c-115">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="5f81c-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="5f81c-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5f81c-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5f81c-117">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5f81c-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f81c-118">참고자료</span><span class="sxs-lookup"><span data-stu-id="5f81c-118">See also</span></span>

- [<span data-ttu-id="5f81c-119">DoStackSnapshot 메서드</span><span class="sxs-lookup"><span data-stu-id="5f81c-119">DoStackSnapshot Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md)
- [<span data-ttu-id="5f81c-120">프로파일링 열거형</span><span class="sxs-lookup"><span data-stu-id="5f81c-120">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
