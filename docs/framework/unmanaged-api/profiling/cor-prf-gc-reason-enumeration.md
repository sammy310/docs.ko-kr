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
ms.openlocfilehash: daf97f25b1adc30b173fcd81812a4b197915cdd1
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59196946"
---
# <a name="corprfgcreason-enumeration"></a><span data-ttu-id="538fd-102">COR_PRF_GC_REASON 열거형</span><span class="sxs-lookup"><span data-stu-id="538fd-102">COR_PRF_GC_REASON Enumeration</span></span>
<span data-ttu-id="538fd-103">가비지 컬렉션이 수행되는 이유를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="538fd-103">Indicates the reason that garbage collection is occurring.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="538fd-104">구문</span><span class="sxs-lookup"><span data-stu-id="538fd-104">Syntax</span></span>  
  
```  
typedef enum {  
    COR_PRF_GC_INDUCED = 1,  
    COR_PRF_GC_OTHER = 0  
} COR_PRF_GC_REASON;  
```  
  
## <a name="members"></a><span data-ttu-id="538fd-105">멤버</span><span class="sxs-lookup"><span data-stu-id="538fd-105">Members</span></span>  
  
|<span data-ttu-id="538fd-106">멤버</span><span class="sxs-lookup"><span data-stu-id="538fd-106">Member</span></span>|<span data-ttu-id="538fd-107">설명</span><span class="sxs-lookup"><span data-stu-id="538fd-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_GC_INDUCED`|<span data-ttu-id="538fd-108">하는 가비지 수집이 발생 한 <xref:System.GC.Collect%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="538fd-108">The garbage collection was induced by a <xref:System.GC.Collect%2A> method.</span></span>|  
|`COR_PRF_GC_OTHER`|<span data-ttu-id="538fd-109">이유 지정 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="538fd-109">The reason is unspecified.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="538fd-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="538fd-110">Requirements</span></span>  
 <span data-ttu-id="538fd-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="538fd-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="538fd-112">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="538fd-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="538fd-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="538fd-113">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="538fd-114">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="538fd-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="538fd-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="538fd-115">See also</span></span>

- [<span data-ttu-id="538fd-116">프로파일링 열거형</span><span class="sxs-lookup"><span data-stu-id="538fd-116">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
