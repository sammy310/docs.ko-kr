---
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 861f4c18f4c5151dc7215d300775928b88f018aa
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59090630"
---
# <a name="corprfclausetype-enumeration"></a><span data-ttu-id="11168-102">COR_PRF_CLAUSE_TYPE 열거형</span><span class="sxs-lookup"><span data-stu-id="11168-102">COR_PRF_CLAUSE_TYPE Enumeration</span></span>
<span data-ttu-id="11168-103">코드에서 방금 시작되거나 끝난 예외 절 형식을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="11168-103">Indicates the type of exception clause that the code has just entered or left.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="11168-104">구문</span><span class="sxs-lookup"><span data-stu-id="11168-104">Syntax</span></span>  
  
```  
typedef enum {  
    COR_PRF_CLAUSE_NONE = 0,  
    COR_PRF_CLAUSE_FILTER = 1,  
    COR_PRF_CLAUSE_CATCH = 2,  
    COR_PRF_CLAUSE_FINALLY = 3,  
} COR_PRF_CLAUSE_TYPE;  
```  
  
## <a name="members"></a><span data-ttu-id="11168-105">멤버</span><span class="sxs-lookup"><span data-stu-id="11168-105">Members</span></span>  
  
|<span data-ttu-id="11168-106">멤버</span><span class="sxs-lookup"><span data-stu-id="11168-106">Member</span></span>|<span data-ttu-id="11168-107">설명</span><span class="sxs-lookup"><span data-stu-id="11168-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_CLAUSE_NONE`|<span data-ttu-id="11168-108">예외 절 올바르지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="11168-108">The exception clause is not valid.</span></span>|  
|`COR_PRF_CLAUSE_FILTER`|<span data-ttu-id="11168-109">예외 절을 필터 식입니다.</span><span class="sxs-lookup"><span data-stu-id="11168-109">The exception clause is a filter expression.</span></span>|  
|`COR_PRF_CLAUSE_CATCH`|<span data-ttu-id="11168-110">예외 절이는 `catch` 문입니다.</span><span class="sxs-lookup"><span data-stu-id="11168-110">The exception clause is a `catch` statement.</span></span>|  
|`COR_PRF_CLAUSE_FINALLY`|<span data-ttu-id="11168-111">예외 절이는 `finally` 문입니다.</span><span class="sxs-lookup"><span data-stu-id="11168-111">The exception clause is a `finally` statement.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="11168-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="11168-112">Requirements</span></span>  
 <span data-ttu-id="11168-113">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="11168-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="11168-114">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="11168-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="11168-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="11168-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="11168-116">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="11168-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11168-117">참고자료</span><span class="sxs-lookup"><span data-stu-id="11168-117">See also</span></span>

- [<span data-ttu-id="11168-118">프로파일링 열거형</span><span class="sxs-lookup"><span data-stu-id="11168-118">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
