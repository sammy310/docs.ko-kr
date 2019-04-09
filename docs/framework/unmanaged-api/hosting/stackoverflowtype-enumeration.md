---
title: StackOverflowType 열거형
ms.date: 03/30/2017
api_name:
- StackOverflowType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- StackOverflowType
helpviewer_keywords:
- StackOverflowType enumeration [.NET Framework hosting]
ms.assetid: dab648ad-972b-479c-b129-b4c1dcbd932e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8541ea7b614ff4a6ca666f0e2549a7f50e190192
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59135878"
---
# <a name="stackoverflowtype-enumeration"></a><span data-ttu-id="cada4-102">StackOverflowType 열거형</span><span class="sxs-lookup"><span data-stu-id="cada4-102">StackOverflowType Enumeration</span></span>
<span data-ttu-id="cada4-103">스택 오버플로 이벤트의 근본 원인을 나타내는 값을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="cada4-103">Contains values that indicate the underlying cause of a stack overflow event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cada4-104">구문</span><span class="sxs-lookup"><span data-stu-id="cada4-104">Syntax</span></span>  
  
```  
typedef enum {  
    SO_Managed,  
    SO_ClrEngine,  
    SO_Other  
} StackOverflowType;  
```  
  
## <a name="members"></a><span data-ttu-id="cada4-105">멤버</span><span class="sxs-lookup"><span data-stu-id="cada4-105">Members</span></span>  
  
|<span data-ttu-id="cada4-106">멤버</span><span class="sxs-lookup"><span data-stu-id="cada4-106">Member</span></span>|<span data-ttu-id="cada4-107">설명</span><span class="sxs-lookup"><span data-stu-id="cada4-107">Description</span></span>|  
|------------|-----------------|  
|`SO_ClrEngine`|<span data-ttu-id="cada4-108">실행 엔진에서 스택 오버플로가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="cada4-108">The stack overflow was caused by the execution engine.</span></span>|  
|`SO_Managed`|<span data-ttu-id="cada4-109">관리 코드에서 스택 오버플로가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="cada4-109">The stack overflow was caused by managed code.</span></span>|  
|`SO_Other`|<span data-ttu-id="cada4-110">비관리 코드에서 스택 오버플로가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="cada4-110">The stack overflow was caused by unmanaged code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cada4-111">설명</span><span class="sxs-lookup"><span data-stu-id="cada4-111">Remarks</span></span>  
 <span data-ttu-id="cada4-112">이 정보는 호출을 통해 호스트에 전달 된 [iactiononclrevent:: Onevent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-onevent-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="cada4-112">This information is passed to the host through a call to the [IActionOnCLREvent::OnEvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-onevent-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cada4-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="cada4-113">Requirements</span></span>  
 <span data-ttu-id="cada4-114">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="cada4-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cada4-115">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="cada4-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="cada4-116">**라이브러리:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="cada4-116">**Library:** MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="cada4-117">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="cada4-117">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="cada4-118">참고자료</span><span class="sxs-lookup"><span data-stu-id="cada4-118">See also</span></span>

- [<span data-ttu-id="cada4-119">호스팅 열거형</span><span class="sxs-lookup"><span data-stu-id="cada4-119">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
