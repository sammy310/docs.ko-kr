---
description: '자세히 알아보기: IActionOnCLREvent 인터페이스'
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
ms.openlocfilehash: 9d762635247f897663f4c6f2badf67edf98bd5d0
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99785174"
---
# <a name="iactiononclrevent-interface"></a><span data-ttu-id="ea349-103">IActionOnCLREvent 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ea349-103">IActionOnCLREvent Interface</span></span>

<span data-ttu-id="ea349-104">[ICLROnEventManager:: RegisterActionOnEvent](iclroneventmanager-registeractiononevent-method.md) 메서드를 호출 하 여 등록 된 이벤트에 대해 콜백을 수행 하는 [IActionOnCLREvent:: OnEvent](iactiononclrevent-onevent-method.md) 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea349-104">Provides the [IActionOnCLREvent::OnEvent](iactiononclrevent-onevent-method.md) method, which performs callbacks on events that have been registered by using a call to the [ICLROnEventManager::RegisterActionOnEvent](iclroneventmanager-registeractiononevent-method.md) method.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ea349-105">메서드</span><span class="sxs-lookup"><span data-stu-id="ea349-105">Methods</span></span>  
  
|<span data-ttu-id="ea349-106">메서드</span><span class="sxs-lookup"><span data-stu-id="ea349-106">Method</span></span>|<span data-ttu-id="ea349-107">설명</span><span class="sxs-lookup"><span data-stu-id="ea349-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ea349-108">OnEvent 메서드</span><span class="sxs-lookup"><span data-stu-id="ea349-108">OnEvent Method</span></span>](iactiononclrevent-onevent-method.md)|<span data-ttu-id="ea349-109">등록 된 이벤트에 대 한 콜백을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea349-109">Performs a callback for a registered event.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ea349-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ea349-110">Requirements</span></span>  

 <span data-ttu-id="ea349-111">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ea349-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ea349-112">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="ea349-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ea349-113">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ea349-113">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ea349-114">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ea349-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea349-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ea349-115">See also</span></span>

- [<span data-ttu-id="ea349-116">EClrEvent 열거형</span><span class="sxs-lookup"><span data-stu-id="ea349-116">EClrEvent Enumeration</span></span>](eclrevent-enumeration.md)
- [<span data-ttu-id="ea349-117">ICLRControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ea349-117">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="ea349-118">ICLROnEventManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ea349-118">ICLROnEventManager Interface</span></span>](iclroneventmanager-interface.md)
- [<span data-ttu-id="ea349-119">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ea349-119">Hosting Interfaces</span></span>](hosting-interfaces.md)
