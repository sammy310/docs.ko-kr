---
description: '다음에 대 한 자세한 정보: 열거형 COR_PRF_RUNTIME_TYPE'
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
ms.openlocfilehash: 8f4b4a0c51c43b1db97b511387eaee1aee79f523
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99789047"
---
# <a name="cor_prf_runtime_type-enumeration"></a><span data-ttu-id="1d046-103">COR_PRF_RUNTIME_TYPE 열거형</span><span class="sxs-lookup"><span data-stu-id="1d046-103">COR_PRF_RUNTIME_TYPE Enumeration</span></span>

<span data-ttu-id="1d046-104">Silverlight에서 사용 되는 CLR (공용 언어 런타임)의 버전 (CLR)을 나타내는 값을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d046-104">Contains values that indicate the version of the common language runtime (CLR): desktop or CoreCLR, which is used in Silverlight.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1d046-105">구문</span><span class="sxs-lookup"><span data-stu-id="1d046-105">Syntax</span></span>  
  
```cpp  
typedef enum  
{  
    COR_PRF_DESKTOP_CLR = 0x1,  
    COR_PRF_CORE_CLR    = 0x2,  
} COR_PRF_RUNTIME_TYPE;  
```  
  
## <a name="members"></a><span data-ttu-id="1d046-106">구성원</span><span class="sxs-lookup"><span data-stu-id="1d046-106">Members</span></span>  
  
|<span data-ttu-id="1d046-107">멤버</span><span class="sxs-lookup"><span data-stu-id="1d046-107">Member</span></span>|<span data-ttu-id="1d046-108">설명</span><span class="sxs-lookup"><span data-stu-id="1d046-108">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_DESKTOP_CLR`|<span data-ttu-id="1d046-109">CLR의 데스크톱 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="1d046-109">The desktop version of the CLR.</span></span>|  
|`COR_PRF_CORE_CLR`|<span data-ttu-id="1d046-110">Silverlight에서 사용 되는 CLR의 핵심 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="1d046-110">The core version of the CLR, used in Silverlight.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1d046-111">설명</span><span class="sxs-lookup"><span data-stu-id="1d046-111">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1d046-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1d046-112">Requirements</span></span>  

 <span data-ttu-id="1d046-113">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1d046-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1d046-114">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="1d046-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="1d046-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1d046-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1d046-116">**.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1d046-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d046-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1d046-117">See also</span></span>

- [<span data-ttu-id="1d046-118">프로파일링 열거형</span><span class="sxs-lookup"><span data-stu-id="1d046-118">Profiling Enumerations</span></span>](profiling-enumerations.md)
