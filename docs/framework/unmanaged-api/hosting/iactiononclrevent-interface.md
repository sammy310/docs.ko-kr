---
title: IActionOnCLREvent 인터페이스
ms.date: 03/30/2017
api_name:
- IActionOnCLREvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IActionOnCLREvent
helpviewer_keywords:
- IActionOnCLREvent interface [.NET Framework hosting]
ms.assetid: b5f9b41e-7301-429c-911f-21d5422292b3
topic_type:
- apiref
ms.openlocfilehash: f577e9252d97ec188ff1076fd8340336b16c8257
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2020
ms.locfileid: "84504331"
---
# <a name="iactiononclrevent-interface"></a><span data-ttu-id="e5403-102">IActionOnCLREvent 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e5403-102">IActionOnCLREvent Interface</span></span>
<span data-ttu-id="e5403-103">[ICLROnEventManager:: RegisterActionOnEvent](iclroneventmanager-registeractiononevent-method.md) 메서드를 호출 하 여 등록 된 이벤트에 대해 콜백을 수행 하는 [IActionOnCLREvent:: OnEvent](iactiononclrevent-onevent-method.md) 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5403-103">Provides the [IActionOnCLREvent::OnEvent](iactiononclrevent-onevent-method.md) method, which performs callbacks on events that have been registered by using a call to the [ICLROnEventManager::RegisterActionOnEvent](iclroneventmanager-registeractiononevent-method.md) method.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e5403-104">메서드</span><span class="sxs-lookup"><span data-stu-id="e5403-104">Methods</span></span>  
  
|<span data-ttu-id="e5403-105">방법</span><span class="sxs-lookup"><span data-stu-id="e5403-105">Method</span></span>|<span data-ttu-id="e5403-106">설명</span><span class="sxs-lookup"><span data-stu-id="e5403-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e5403-107">OnEvent 메서드</span><span class="sxs-lookup"><span data-stu-id="e5403-107">OnEvent Method</span></span>](iactiononclrevent-onevent-method.md)|<span data-ttu-id="e5403-108">등록 된 이벤트에 대 한 콜백을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5403-108">Performs a callback for a registered event.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e5403-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e5403-109">Requirements</span></span>  
 <span data-ttu-id="e5403-110">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e5403-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e5403-111">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="e5403-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e5403-112">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e5403-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e5403-113">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e5403-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5403-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e5403-114">See also</span></span>

- [<span data-ttu-id="e5403-115">EClrEvent 열거형</span><span class="sxs-lookup"><span data-stu-id="e5403-115">EClrEvent Enumeration</span></span>](eclrevent-enumeration.md)
- [<span data-ttu-id="e5403-116">ICLRControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e5403-116">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="e5403-117">ICLROnEventManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e5403-117">ICLROnEventManager Interface</span></span>](iclroneventmanager-interface.md)
- [<span data-ttu-id="e5403-118">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e5403-118">Hosting Interfaces</span></span>](hosting-interfaces.md)
