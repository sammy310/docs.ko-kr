---
description: '자세히 알아보기: StackOverflowType 열거형'
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
ms.openlocfilehash: d39ccd99331a3e839236f1ede21254edb92b2dfb
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99679357"
---
# <a name="stackoverflowtype-enumeration"></a><span data-ttu-id="8bc80-103">StackOverflowType 열거형</span><span class="sxs-lookup"><span data-stu-id="8bc80-103">StackOverflowType Enumeration</span></span>

<span data-ttu-id="8bc80-104">스택 오버플로 이벤트의 근본 원인을 나타내는 값을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="8bc80-104">Contains values that indicate the underlying cause of a stack overflow event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8bc80-105">구문</span><span class="sxs-lookup"><span data-stu-id="8bc80-105">Syntax</span></span>  
  
```cpp  
typedef enum {  
    SO_Managed,  
    SO_ClrEngine,  
    SO_Other  
} StackOverflowType;  
```  
  
## <a name="members"></a><span data-ttu-id="8bc80-106">구성원</span><span class="sxs-lookup"><span data-stu-id="8bc80-106">Members</span></span>  
  
|<span data-ttu-id="8bc80-107">멤버</span><span class="sxs-lookup"><span data-stu-id="8bc80-107">Member</span></span>|<span data-ttu-id="8bc80-108">설명</span><span class="sxs-lookup"><span data-stu-id="8bc80-108">Description</span></span>|  
|------------|-----------------|  
|`SO_ClrEngine`|<span data-ttu-id="8bc80-109">실행 엔진에서 스택 오버플로가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="8bc80-109">The stack overflow was caused by the execution engine.</span></span>|  
|`SO_Managed`|<span data-ttu-id="8bc80-110">관리 코드 때문에 스택 오버플로가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="8bc80-110">The stack overflow was caused by managed code.</span></span>|  
|`SO_Other`|<span data-ttu-id="8bc80-111">비관리 코드에서 스택 오버플로가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="8bc80-111">The stack overflow was caused by unmanaged code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8bc80-112">설명</span><span class="sxs-lookup"><span data-stu-id="8bc80-112">Remarks</span></span>  

 <span data-ttu-id="8bc80-113">이 정보는 [IActionOnCLREvent:: OnEvent](iactiononclrevent-onevent-method.md) 메서드를 호출 하 여 호스트에 전달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8bc80-113">This information is passed to the host through a call to the [IActionOnCLREvent::OnEvent](iactiononclrevent-onevent-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8bc80-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8bc80-114">Requirements</span></span>  

 <span data-ttu-id="8bc80-115">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8bc80-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8bc80-116">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="8bc80-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8bc80-117">**라이브러리:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8bc80-117">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8bc80-118">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8bc80-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8bc80-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8bc80-119">See also</span></span>

- [<span data-ttu-id="8bc80-120">호스팅 열거형</span><span class="sxs-lookup"><span data-stu-id="8bc80-120">Hosting Enumerations</span></span>](hosting-enumerations.md)
