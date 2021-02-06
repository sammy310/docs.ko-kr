---
description: '다음에 대 한 자세한 정보: 열거형 COR_PRF_CLAUSE_TYPE'
title: COR_PRF_CLAUSE_TYPE 열거형
ms.date: 03/30/2017
api_name:
- COR_PRF_CLAUSE_TYPE
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_CLAUSE_TYPE
helpviewer_keywords:
- COR_PRF_CLAUSE_TYPE enumeration [.NET Framework profiling]
ms.assetid: f64c325a-ed3a-4aaf-b847-a88edbc4fefc
topic_type:
- apiref
ms.openlocfilehash: 413dbc0ad94e4ab670cd7cd9537bbd1735ffd7cf
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99649288"
---
# <a name="cor_prf_clause_type-enumeration"></a><span data-ttu-id="99823-103">COR_PRF_CLAUSE_TYPE 열거형</span><span class="sxs-lookup"><span data-stu-id="99823-103">COR_PRF_CLAUSE_TYPE Enumeration</span></span>

<span data-ttu-id="99823-104">코드에서 방금 시작되거나 끝난 예외 절 형식을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="99823-104">Indicates the type of exception clause that the code has just entered or left.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="99823-105">구문</span><span class="sxs-lookup"><span data-stu-id="99823-105">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_PRF_CLAUSE_NONE = 0,  
    COR_PRF_CLAUSE_FILTER = 1,  
    COR_PRF_CLAUSE_CATCH = 2,  
    COR_PRF_CLAUSE_FINALLY = 3,  
} COR_PRF_CLAUSE_TYPE;  
```  
  
## <a name="members"></a><span data-ttu-id="99823-106">구성원</span><span class="sxs-lookup"><span data-stu-id="99823-106">Members</span></span>  
  
|<span data-ttu-id="99823-107">멤버</span><span class="sxs-lookup"><span data-stu-id="99823-107">Member</span></span>|<span data-ttu-id="99823-108">설명</span><span class="sxs-lookup"><span data-stu-id="99823-108">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_CLAUSE_NONE`|<span data-ttu-id="99823-109">예외 절이 잘못 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="99823-109">The exception clause is not valid.</span></span>|  
|`COR_PRF_CLAUSE_FILTER`|<span data-ttu-id="99823-110">Exception 절은 필터 식입니다.</span><span class="sxs-lookup"><span data-stu-id="99823-110">The exception clause is a filter expression.</span></span>|  
|`COR_PRF_CLAUSE_CATCH`|<span data-ttu-id="99823-111">Exception 절은 `catch` 문입니다.</span><span class="sxs-lookup"><span data-stu-id="99823-111">The exception clause is a `catch` statement.</span></span>|  
|`COR_PRF_CLAUSE_FINALLY`|<span data-ttu-id="99823-112">Exception 절은 `finally` 문입니다.</span><span class="sxs-lookup"><span data-stu-id="99823-112">The exception clause is a `finally` statement.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="99823-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="99823-113">Requirements</span></span>  

 <span data-ttu-id="99823-114">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="99823-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="99823-115">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="99823-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="99823-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="99823-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="99823-117">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="99823-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99823-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="99823-118">See also</span></span>

- [<span data-ttu-id="99823-119">프로파일링 열거형</span><span class="sxs-lookup"><span data-stu-id="99823-119">Profiling Enumerations</span></span>](profiling-enumerations.md)
