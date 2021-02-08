---
description: '자세히 알아보기: ICLROnEventManager 인터페이스'
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
ms.openlocfilehash: 7a9c0beec5083bc93f5361bb0e701da5beeedea2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99789829"
---
# <a name="iclroneventmanager-interface"></a><span data-ttu-id="e0ec4-103">ICLROnEventManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e0ec4-103">ICLROnEventManager Interface</span></span>

<span data-ttu-id="e0ec4-104">호스트가 CLR (공용 언어 런타임) 이벤트에 대 한 콜백을 등록 하 고 등록 취소할 수 있도록 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0ec4-104">Provides methods that allow the host to register and unregister callbacks for common language runtime (CLR) events.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e0ec4-105">메서드</span><span class="sxs-lookup"><span data-stu-id="e0ec4-105">Methods</span></span>  
  
|<span data-ttu-id="e0ec4-106">메서드</span><span class="sxs-lookup"><span data-stu-id="e0ec4-106">Method</span></span>|<span data-ttu-id="e0ec4-107">설명</span><span class="sxs-lookup"><span data-stu-id="e0ec4-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e0ec4-108">RegisterActionOnEvent 메서드</span><span class="sxs-lookup"><span data-stu-id="e0ec4-108">RegisterActionOnEvent Method</span></span>](iclroneventmanager-registeractiononevent-method.md)|<span data-ttu-id="e0ec4-109">지정 된 이벤트에 대 한 콜백 포인터를 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0ec4-109">Registers a callback pointer for the specified event.</span></span>|  
|[<span data-ttu-id="e0ec4-110">UnregisterActionOnEvent 메서드</span><span class="sxs-lookup"><span data-stu-id="e0ec4-110">UnregisterActionOnEvent Method</span></span>](iclroneventmanager-unregisteractiononevent-method.md)|<span data-ttu-id="e0ec4-111">지정 된 이벤트에 대해 이전에 등록 된 콜백 포인터의 등록을 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0ec4-111">Unregisters a previously registered callback pointer for the specified event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e0ec4-112">설명</span><span class="sxs-lookup"><span data-stu-id="e0ec4-112">Remarks</span></span>  

 <span data-ttu-id="e0ec4-113">이벤트 콜백을 등록 하 고 등록을 취소 하기 위해 호스트는 `ICLROnEventManager` [ICLRControl:: GetCLRManager](iclrcontrol-getclrmanager-method.md) 메서드를 호출 하 여에 대 한 참조를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="e0ec4-113">To register and unregister event callbacks, the host gets a reference to `ICLROnEventManager` by calling the [ICLRControl::GetCLRManager](iclrcontrol-getclrmanager-method.md) method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e0ec4-114">[EClrEvent](eclrevent-enumeration.md) 에서 설명 하는 이벤트는 여러 스레드에서 두 번 이상 발생 하 여 언로드 또는 CLR 비활성화를 알릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0ec4-114">The events described by [EClrEvent](eclrevent-enumeration.md) can be fired more than once and from different threads to signal an unload or the disabling of the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e0ec4-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e0ec4-115">Requirements</span></span>  

 <span data-ttu-id="e0ec4-116">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e0ec4-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e0ec4-117">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="e0ec4-117">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e0ec4-118">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0ec4-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e0ec4-119">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e0ec4-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0ec4-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e0ec4-120">See also</span></span>

- [<span data-ttu-id="e0ec4-121">EClrEvent 열거형</span><span class="sxs-lookup"><span data-stu-id="e0ec4-121">EClrEvent Enumeration</span></span>](eclrevent-enumeration.md)
- [<span data-ttu-id="e0ec4-122">IActionOnCLREvent 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e0ec4-122">IActionOnCLREvent Interface</span></span>](iactiononclrevent-interface.md)
- [<span data-ttu-id="e0ec4-123">ICLRControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e0ec4-123">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="e0ec4-124">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e0ec4-124">Hosting Interfaces</span></span>](hosting-interfaces.md)
