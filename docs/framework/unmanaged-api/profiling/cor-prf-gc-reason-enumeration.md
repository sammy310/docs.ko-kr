---
title: COR_PRF_GC_REASON 열거형
ms.date: 03/30/2017
api_name:
- COR_PRF_GC_REASON
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_GC_REASON
helpviewer_keywords:
- COR_PRF_GC_REASON enumeration [.NET Framework profiling]
ms.assetid: 72822b95-a7fb-485e-9d55-1cb016d9a458
topic_type:
- apiref
ms.openlocfilehash: 409a21238f172e5ecdaa8d5bfa237a9f3fe46345
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500912"
---
# <a name="cor_prf_gc_reason-enumeration"></a><span data-ttu-id="a0676-102">COR_PRF_GC_REASON 열거형</span><span class="sxs-lookup"><span data-stu-id="a0676-102">COR_PRF_GC_REASON Enumeration</span></span>
<span data-ttu-id="a0676-103">가비지 컬렉션이 수행되는 이유를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a0676-103">Indicates the reason that garbage collection is occurring.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a0676-104">구문</span><span class="sxs-lookup"><span data-stu-id="a0676-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_PRF_GC_INDUCED = 1,  
    COR_PRF_GC_OTHER = 0  
} COR_PRF_GC_REASON;  
```  
  
## <a name="members"></a><span data-ttu-id="a0676-105">멤버</span><span class="sxs-lookup"><span data-stu-id="a0676-105">Members</span></span>  
  
|<span data-ttu-id="a0676-106">멤버</span><span class="sxs-lookup"><span data-stu-id="a0676-106">Member</span></span>|<span data-ttu-id="a0676-107">설명</span><span class="sxs-lookup"><span data-stu-id="a0676-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_GC_INDUCED`|<span data-ttu-id="a0676-108">메서드에서 가비지 수집을 발생 시킨 경우 <xref:System.GC.Collect%2A></span><span class="sxs-lookup"><span data-stu-id="a0676-108">The garbage collection was induced by a <xref:System.GC.Collect%2A> method.</span></span>|  
|`COR_PRF_GC_OTHER`|<span data-ttu-id="a0676-109">이유가 지정 되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="a0676-109">The reason is unspecified.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a0676-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a0676-110">Requirements</span></span>  
 <span data-ttu-id="a0676-111">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a0676-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a0676-112">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a0676-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a0676-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a0676-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a0676-114">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a0676-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0676-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a0676-115">See also</span></span>

- [<span data-ttu-id="a0676-116">프로파일링 열거형</span><span class="sxs-lookup"><span data-stu-id="a0676-116">Profiling Enumerations</span></span>](profiling-enumerations.md)
