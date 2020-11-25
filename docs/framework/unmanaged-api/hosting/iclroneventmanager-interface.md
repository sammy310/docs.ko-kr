---
title: ICLROnEventManager 인터페이스
ms.date: 03/30/2017
api_name:
- ICLROnEventManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLROnEventManager
helpviewer_keywords:
- ICLROnEventManager interface [.NET Framework hosting]
ms.assetid: 9e15a0c1-8ab6-43d0-ae28-6ec7a4edd913
topic_type:
- apiref
ms.openlocfilehash: 1948075d87b5a44397a1eaab3adb4edbc96d7143
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725637"
---
# <a name="iclroneventmanager-interface"></a><span data-ttu-id="9475d-102">ICLROnEventManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9475d-102">ICLROnEventManager Interface</span></span>

<span data-ttu-id="9475d-103">호스트가 CLR (공용 언어 런타임) 이벤트에 대 한 콜백을 등록 하 고 등록 취소할 수 있도록 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="9475d-103">Provides methods that allow the host to register and unregister callbacks for common language runtime (CLR) events.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="9475d-104">메서드</span><span class="sxs-lookup"><span data-stu-id="9475d-104">Methods</span></span>  
  
|<span data-ttu-id="9475d-105">메서드</span><span class="sxs-lookup"><span data-stu-id="9475d-105">Method</span></span>|<span data-ttu-id="9475d-106">설명</span><span class="sxs-lookup"><span data-stu-id="9475d-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="9475d-107">RegisterActionOnEvent 메서드</span><span class="sxs-lookup"><span data-stu-id="9475d-107">RegisterActionOnEvent Method</span></span>](iclroneventmanager-registeractiononevent-method.md)|<span data-ttu-id="9475d-108">지정 된 이벤트에 대 한 콜백 포인터를 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="9475d-108">Registers a callback pointer for the specified event.</span></span>|  
|[<span data-ttu-id="9475d-109">UnregisterActionOnEvent 메서드</span><span class="sxs-lookup"><span data-stu-id="9475d-109">UnregisterActionOnEvent Method</span></span>](iclroneventmanager-unregisteractiononevent-method.md)|<span data-ttu-id="9475d-110">지정 된 이벤트에 대해 이전에 등록 된 콜백 포인터의 등록을 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="9475d-110">Unregisters a previously registered callback pointer for the specified event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9475d-111">설명</span><span class="sxs-lookup"><span data-stu-id="9475d-111">Remarks</span></span>  

 <span data-ttu-id="9475d-112">이벤트 콜백을 등록 하 고 등록을 취소 하기 위해 호스트는 `ICLROnEventManager` [ICLRControl:: GetCLRManager](iclrcontrol-getclrmanager-method.md) 메서드를 호출 하 여에 대 한 참조를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="9475d-112">To register and unregister event callbacks, the host gets a reference to `ICLROnEventManager` by calling the [ICLRControl::GetCLRManager](iclrcontrol-getclrmanager-method.md) method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9475d-113">[EClrEvent](eclrevent-enumeration.md) 에서 설명 하는 이벤트는 여러 스레드에서 두 번 이상 발생 하 여 언로드 또는 CLR 비활성화를 알릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9475d-113">The events described by [EClrEvent](eclrevent-enumeration.md) can be fired more than once and from different threads to signal an unload or the disabling of the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9475d-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9475d-114">Requirements</span></span>  

 <span data-ttu-id="9475d-115">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9475d-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9475d-116">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="9475d-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9475d-117">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9475d-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9475d-118">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9475d-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9475d-119">참조</span><span class="sxs-lookup"><span data-stu-id="9475d-119">See also</span></span>

- [<span data-ttu-id="9475d-120">EClrEvent 열거형</span><span class="sxs-lookup"><span data-stu-id="9475d-120">EClrEvent Enumeration</span></span>](eclrevent-enumeration.md)
- [<span data-ttu-id="9475d-121">IActionOnCLREvent 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9475d-121">IActionOnCLREvent Interface</span></span>](iactiononclrevent-interface.md)
- [<span data-ttu-id="9475d-122">ICLRControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9475d-122">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="9475d-123">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9475d-123">Hosting Interfaces</span></span>](hosting-interfaces.md)
