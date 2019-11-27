---
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
ms.openlocfilehash: 40698a49ac7012c4f67eb88b1ead04c80f3dea77
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74428319"
---
# <a name="cor_prf_function-structure"></a><span data-ttu-id="eea4f-102">COR_PRF_FUNCTION 구조체</span><span class="sxs-lookup"><span data-stu-id="eea4f-102">COR_PRF_FUNCTION Structure</span></span>
<span data-ttu-id="eea4f-103">함수의 ID와 다시 컴파일된 함수 버전의 ID를 결합하여 함수의 고유한 표현을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="eea4f-103">Provides a unique representation of a function by combining its ID with the ID of its recompiled version.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eea4f-104">구문</span><span class="sxs-lookup"><span data-stu-id="eea4f-104">Syntax</span></span>  
  
```cpp  
typedef struct _COR_PRF_FUNCTION {    FunctionID functionId;    ReJITID    reJitId;} COR_PRF_FUNCTION;  
```  
  
## <a name="members"></a><span data-ttu-id="eea4f-105">멤버</span><span class="sxs-lookup"><span data-stu-id="eea4f-105">Members</span></span>  
  
|<span data-ttu-id="eea4f-106">멤버</span><span class="sxs-lookup"><span data-stu-id="eea4f-106">Member</span></span>|<span data-ttu-id="eea4f-107">설명</span><span class="sxs-lookup"><span data-stu-id="eea4f-107">Description</span></span>|  
|------------|-----------------|  
|`functionId`|<span data-ttu-id="eea4f-108">함수의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="eea4f-108">The ID of the function.</span></span>|  
|`reJitId`|<span data-ttu-id="eea4f-109">다시 컴파일된 함수의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="eea4f-109">The ID of the recompiled function.</span></span> <span data-ttu-id="eea4f-110">값이 0 이면 함수의 원래 버전을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="eea4f-110">A value of 0 (zero) represents the original version of the function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="eea4f-111">주의</span><span class="sxs-lookup"><span data-stu-id="eea4f-111">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eea4f-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="eea4f-112">Requirements</span></span>  
 <span data-ttu-id="eea4f-113">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="eea4f-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eea4f-114">**헤더:** Corprof.idl</span><span class="sxs-lookup"><span data-stu-id="eea4f-114">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="eea4f-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="eea4f-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="eea4f-116">**.NET Framework 버전:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eea4f-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eea4f-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="eea4f-117">See also</span></span>

- [<span data-ttu-id="eea4f-118">프로파일링 구조체</span><span class="sxs-lookup"><span data-stu-id="eea4f-118">Profiling Structures</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)
