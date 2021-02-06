---
description: '다음에 대 한 자세한 정보: COR_PRF_FUNCTION 구조체'
title: COR_PRF_FUNCTION 구조체
ms.date: 03/30/2017
api_name:
- COR_PRF_FUNCTION
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_FUNCTION
helpviewer_keywords:
- COR_PRF_FUNCTION structure [.NET Framework profiling]
ms.assetid: 8bb5acf5-cf4b-4ccb-93f1-46db1f3f8bf3
topic_type:
- apiref
ms.openlocfilehash: 494f3cfe6d1e3641645ef0050c06014e67bf4475
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99648976"
---
# <a name="cor_prf_function-structure"></a><span data-ttu-id="bf45a-103">COR_PRF_FUNCTION 구조체</span><span class="sxs-lookup"><span data-stu-id="bf45a-103">COR_PRF_FUNCTION Structure</span></span>

<span data-ttu-id="bf45a-104">함수의 ID와 다시 컴파일된 함수 버전의 ID를 결합하여 함수의 고유한 표현을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="bf45a-104">Provides a unique representation of a function by combining its ID with the ID of its recompiled version.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bf45a-105">구문</span><span class="sxs-lookup"><span data-stu-id="bf45a-105">Syntax</span></span>  
  
```cpp  
typedef struct _COR_PRF_FUNCTION {    FunctionID functionId;    ReJITID    reJitId;} COR_PRF_FUNCTION;  
```  
  
## <a name="members"></a><span data-ttu-id="bf45a-106">구성원</span><span class="sxs-lookup"><span data-stu-id="bf45a-106">Members</span></span>  
  
|<span data-ttu-id="bf45a-107">멤버</span><span class="sxs-lookup"><span data-stu-id="bf45a-107">Member</span></span>|<span data-ttu-id="bf45a-108">설명</span><span class="sxs-lookup"><span data-stu-id="bf45a-108">Description</span></span>|  
|------------|-----------------|  
|`functionId`|<span data-ttu-id="bf45a-109">함수의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="bf45a-109">The ID of the function.</span></span>|  
|`reJitId`|<span data-ttu-id="bf45a-110">다시 컴파일된 함수의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="bf45a-110">The ID of the recompiled function.</span></span> <span data-ttu-id="bf45a-111">값이 0 이면 함수의 원래 버전을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="bf45a-111">A value of 0 (zero) represents the original version of the function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bf45a-112">설명</span><span class="sxs-lookup"><span data-stu-id="bf45a-112">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bf45a-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="bf45a-113">Requirements</span></span>  

 <span data-ttu-id="bf45a-114">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bf45a-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bf45a-115">**헤더:** Corprof.idl</span><span class="sxs-lookup"><span data-stu-id="bf45a-115">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="bf45a-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bf45a-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bf45a-117">**.NET Framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bf45a-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf45a-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bf45a-118">See also</span></span>

- [<span data-ttu-id="bf45a-119">프로파일링 구조체</span><span class="sxs-lookup"><span data-stu-id="bf45a-119">Profiling Structures</span></span>](profiling-structures.md)
