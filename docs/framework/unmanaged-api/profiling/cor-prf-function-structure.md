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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 57520b4a67eb164c8f8631dc4d63d32c655dafa2
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67753827"
---
# <a name="corprffunction-structure"></a><span data-ttu-id="16b38-102">COR_PRF_FUNCTION 구조체</span><span class="sxs-lookup"><span data-stu-id="16b38-102">COR_PRF_FUNCTION Structure</span></span>
<span data-ttu-id="16b38-103">함수의 ID와 다시 컴파일된 함수 버전의 ID를 결합하여 함수의 고유한 표현을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="16b38-103">Provides a unique representation of a function by combining its ID with the ID of its recompiled version.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="16b38-104">구문</span><span class="sxs-lookup"><span data-stu-id="16b38-104">Syntax</span></span>  
  
```cpp  
typedef struct _COR_PRF_FUNCTION {    FunctionID functionId;    ReJITID    reJitId;} COR_PRF_FUNCTION;  
```  
  
## <a name="members"></a><span data-ttu-id="16b38-105">멤버</span><span class="sxs-lookup"><span data-stu-id="16b38-105">Members</span></span>  
  
|<span data-ttu-id="16b38-106">멤버</span><span class="sxs-lookup"><span data-stu-id="16b38-106">Member</span></span>|<span data-ttu-id="16b38-107">Description</span><span class="sxs-lookup"><span data-stu-id="16b38-107">Description</span></span>|  
|------------|-----------------|  
|`functionId`|<span data-ttu-id="16b38-108">ID 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="16b38-108">The ID of the function.</span></span>|  
|`reJitId`|<span data-ttu-id="16b38-109">다시 컴파일된 함수의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="16b38-109">The ID of the recompiled function.</span></span> <span data-ttu-id="16b38-110">값이 0 (영) 함수의 원래 버전을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="16b38-110">A value of 0 (zero) represents the original version of the function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="16b38-111">설명</span><span class="sxs-lookup"><span data-stu-id="16b38-111">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="16b38-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="16b38-112">Requirements</span></span>  
 <span data-ttu-id="16b38-113">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="16b38-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="16b38-114">**헤더:** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="16b38-114">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="16b38-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="16b38-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="16b38-116">**.NET Framework 버전:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="16b38-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16b38-117">참고자료</span><span class="sxs-lookup"><span data-stu-id="16b38-117">See also</span></span>

- [<span data-ttu-id="16b38-118">프로파일링 구조체</span><span class="sxs-lookup"><span data-stu-id="16b38-118">Profiling Structures</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)
