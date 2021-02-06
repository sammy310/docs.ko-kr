---
description: '다음에 대 한 자세한 정보: 열거형 COR_PRF_GC_REASON'
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
ms.openlocfilehash: f5c8201f2023e07f9bb9d540f6d5f8fca1c19419
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99648798"
---
# <a name="cor_prf_gc_reason-enumeration"></a><span data-ttu-id="18943-103">COR_PRF_GC_REASON 열거형</span><span class="sxs-lookup"><span data-stu-id="18943-103">COR_PRF_GC_REASON Enumeration</span></span>

<span data-ttu-id="18943-104">가비지 컬렉션이 수행되는 이유를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="18943-104">Indicates the reason that garbage collection is occurring.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="18943-105">구문</span><span class="sxs-lookup"><span data-stu-id="18943-105">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_PRF_GC_INDUCED = 1,  
    COR_PRF_GC_OTHER = 0  
} COR_PRF_GC_REASON;  
```  
  
## <a name="members"></a><span data-ttu-id="18943-106">구성원</span><span class="sxs-lookup"><span data-stu-id="18943-106">Members</span></span>  
  
|<span data-ttu-id="18943-107">멤버</span><span class="sxs-lookup"><span data-stu-id="18943-107">Member</span></span>|<span data-ttu-id="18943-108">설명</span><span class="sxs-lookup"><span data-stu-id="18943-108">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_GC_INDUCED`|<span data-ttu-id="18943-109">메서드에서 가비지 수집을 발생 시킨 경우 <xref:System.GC.Collect%2A></span><span class="sxs-lookup"><span data-stu-id="18943-109">The garbage collection was induced by a <xref:System.GC.Collect%2A> method.</span></span>|  
|`COR_PRF_GC_OTHER`|<span data-ttu-id="18943-110">이유가 지정 되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="18943-110">The reason is unspecified.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="18943-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="18943-111">Requirements</span></span>  

 <span data-ttu-id="18943-112">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="18943-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="18943-113">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="18943-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="18943-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="18943-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="18943-115">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="18943-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18943-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="18943-116">See also</span></span>

- [<span data-ttu-id="18943-117">프로파일링 열거형</span><span class="sxs-lookup"><span data-stu-id="18943-117">Profiling Enumerations</span></span>](profiling-enumerations.md)
