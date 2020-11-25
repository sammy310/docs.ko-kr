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
ms.openlocfilehash: bbdc68721378e6bbb09f5e4eade08e2e6e03b097
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729917"
---
# <a name="stackoverflowtype-enumeration"></a><span data-ttu-id="48c57-102">StackOverflowType 열거형</span><span class="sxs-lookup"><span data-stu-id="48c57-102">StackOverflowType Enumeration</span></span>

<span data-ttu-id="48c57-103">스택 오버플로 이벤트의 근본 원인을 나타내는 값을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="48c57-103">Contains values that indicate the underlying cause of a stack overflow event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="48c57-104">구문</span><span class="sxs-lookup"><span data-stu-id="48c57-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    SO_Managed,  
    SO_ClrEngine,  
    SO_Other  
} StackOverflowType;  
```  
  
## <a name="members"></a><span data-ttu-id="48c57-105">멤버</span><span class="sxs-lookup"><span data-stu-id="48c57-105">Members</span></span>  
  
|<span data-ttu-id="48c57-106">멤버</span><span class="sxs-lookup"><span data-stu-id="48c57-106">Member</span></span>|<span data-ttu-id="48c57-107">설명</span><span class="sxs-lookup"><span data-stu-id="48c57-107">Description</span></span>|  
|------------|-----------------|  
|`SO_ClrEngine`|<span data-ttu-id="48c57-108">실행 엔진에서 스택 오버플로가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="48c57-108">The stack overflow was caused by the execution engine.</span></span>|  
|`SO_Managed`|<span data-ttu-id="48c57-109">관리 코드 때문에 스택 오버플로가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="48c57-109">The stack overflow was caused by managed code.</span></span>|  
|`SO_Other`|<span data-ttu-id="48c57-110">비관리 코드에서 스택 오버플로가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="48c57-110">The stack overflow was caused by unmanaged code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="48c57-111">설명</span><span class="sxs-lookup"><span data-stu-id="48c57-111">Remarks</span></span>  

 <span data-ttu-id="48c57-112">이 정보는 [IActionOnCLREvent:: OnEvent](iactiononclrevent-onevent-method.md) 메서드를 호출 하 여 호스트에 전달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="48c57-112">This information is passed to the host through a call to the [IActionOnCLREvent::OnEvent](iactiononclrevent-onevent-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="48c57-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="48c57-113">Requirements</span></span>  

 <span data-ttu-id="48c57-114">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="48c57-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="48c57-115">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="48c57-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="48c57-116">**라이브러리:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="48c57-116">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="48c57-117">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="48c57-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48c57-118">참조</span><span class="sxs-lookup"><span data-stu-id="48c57-118">See also</span></span>

- [<span data-ttu-id="48c57-119">호스팅 열거형</span><span class="sxs-lookup"><span data-stu-id="48c57-119">Hosting Enumerations</span></span>](hosting-enumerations.md)
