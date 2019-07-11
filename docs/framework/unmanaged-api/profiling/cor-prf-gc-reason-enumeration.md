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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4f5a596608719889e6440e5cd42dafb82abaa074
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67753716"
---
# <a name="corprfgcreason-enumeration"></a><span data-ttu-id="7ad34-102">COR_PRF_GC_REASON 열거형</span><span class="sxs-lookup"><span data-stu-id="7ad34-102">COR_PRF_GC_REASON Enumeration</span></span>
<span data-ttu-id="7ad34-103">가비지 컬렉션이 수행되는 이유를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="7ad34-103">Indicates the reason that garbage collection is occurring.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7ad34-104">구문</span><span class="sxs-lookup"><span data-stu-id="7ad34-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_PRF_GC_INDUCED = 1,  
    COR_PRF_GC_OTHER = 0  
} COR_PRF_GC_REASON;  
```  
  
## <a name="members"></a><span data-ttu-id="7ad34-105">멤버</span><span class="sxs-lookup"><span data-stu-id="7ad34-105">Members</span></span>  
  
|<span data-ttu-id="7ad34-106">멤버</span><span class="sxs-lookup"><span data-stu-id="7ad34-106">Member</span></span>|<span data-ttu-id="7ad34-107">Description</span><span class="sxs-lookup"><span data-stu-id="7ad34-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_GC_INDUCED`|<span data-ttu-id="7ad34-108">하는 가비지 수집이 발생 한 <xref:System.GC.Collect%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="7ad34-108">The garbage collection was induced by a <xref:System.GC.Collect%2A> method.</span></span>|  
|`COR_PRF_GC_OTHER`|<span data-ttu-id="7ad34-109">이유 지정 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7ad34-109">The reason is unspecified.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7ad34-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7ad34-110">Requirements</span></span>  
 <span data-ttu-id="7ad34-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="7ad34-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7ad34-112">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="7ad34-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="7ad34-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7ad34-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7ad34-114">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7ad34-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ad34-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="7ad34-115">See also</span></span>

- [<span data-ttu-id="7ad34-116">프로파일링 열거형</span><span class="sxs-lookup"><span data-stu-id="7ad34-116">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
