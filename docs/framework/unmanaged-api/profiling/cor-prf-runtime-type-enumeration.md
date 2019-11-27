---
title: COR_PRF_RUNTIME_TYPE 열거형
ms.date: 03/30/2017
api_name:
- COR_PRF_RUNTIME_TYPE Enumeration
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_RUNTIME_TYPE
helpviewer_keywords:
- COR_PRF_RUNTIME_TYPE enumeration [.NET Framework profiling]
ms.assetid: 35449514-333f-4918-9c60-7aa198d655d2
topic_type:
- apiref
ms.openlocfilehash: 26948261c571dbe963811e8e9631551685a63bdb
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74450377"
---
# <a name="cor_prf_runtime_type-enumeration"></a><span data-ttu-id="837fe-102">COR_PRF_RUNTIME_TYPE 열거형</span><span class="sxs-lookup"><span data-stu-id="837fe-102">COR_PRF_RUNTIME_TYPE Enumeration</span></span>
<span data-ttu-id="837fe-103">Silverlight에서 사용 되는 CLR (공용 언어 런타임)의 버전 (CLR)을 나타내는 값을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="837fe-103">Contains values that indicate the version of the common language runtime (CLR): desktop or CoreCLR, which is used in Silverlight.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="837fe-104">구문</span><span class="sxs-lookup"><span data-stu-id="837fe-104">Syntax</span></span>  
  
```cpp  
typedef enum  
{  
    COR_PRF_DESKTOP_CLR = 0x1,  
    COR_PRF_CORE_CLR    = 0x2,  
} COR_PRF_RUNTIME_TYPE;  
```  
  
## <a name="members"></a><span data-ttu-id="837fe-105">멤버</span><span class="sxs-lookup"><span data-stu-id="837fe-105">Members</span></span>  
  
|<span data-ttu-id="837fe-106">멤버</span><span class="sxs-lookup"><span data-stu-id="837fe-106">Member</span></span>|<span data-ttu-id="837fe-107">설명</span><span class="sxs-lookup"><span data-stu-id="837fe-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_DESKTOP_CLR`|<span data-ttu-id="837fe-108">CLR의 데스크톱 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="837fe-108">The desktop version of the CLR.</span></span>|  
|`COR_PRF_CORE_CLR`|<span data-ttu-id="837fe-109">Silverlight에서 사용 되는 CLR의 핵심 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="837fe-109">The core version of the CLR, used in Silverlight.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="837fe-110">주의</span><span class="sxs-lookup"><span data-stu-id="837fe-110">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="837fe-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="837fe-111">Requirements</span></span>  
 <span data-ttu-id="837fe-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="837fe-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="837fe-113">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="837fe-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="837fe-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="837fe-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="837fe-115">**.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="837fe-115">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="837fe-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="837fe-116">See also</span></span>

- [<span data-ttu-id="837fe-117">프로파일링 열거형</span><span class="sxs-lookup"><span data-stu-id="837fe-117">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
