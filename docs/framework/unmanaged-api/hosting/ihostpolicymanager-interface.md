---
title: IHostPolicyManager 인터페이스
ms.date: 03/30/2017
api_name:
- IHostPolicyManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostPolicyManager
helpviewer_keywords:
- IHostPolicyManager interface [.NET Framework hosting]
ms.assetid: 8c4aa124-5e00-46d9-b1e8-57ba6574bb0d
topic_type:
- apiref
ms.openlocfilehash: d6b34403a45cc40863d79b59396041e496989045
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503941"
---
# <a name="ihostpolicymanager-interface"></a><span data-ttu-id="6ca57-102">IHostPolicyManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6ca57-102">IHostPolicyManager Interface</span></span>
<span data-ttu-id="6ca57-103">중단, 시간 초과 또는 오류가 발생 하는 경우 CLR (공용 언어 런타임)에서 수행 하는 작업을 호스트에 알리는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ca57-103">Provides methods that notify the host of the actions the common language runtime (CLR) performs in case of aborts, timeouts, or failures.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="6ca57-104">메서드</span><span class="sxs-lookup"><span data-stu-id="6ca57-104">Methods</span></span>  
  
|<span data-ttu-id="6ca57-105">방법</span><span class="sxs-lookup"><span data-stu-id="6ca57-105">Method</span></span>|<span data-ttu-id="6ca57-106">설명</span><span class="sxs-lookup"><span data-stu-id="6ca57-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="6ca57-107">OnDefaultAction 메서드</span><span class="sxs-lookup"><span data-stu-id="6ca57-107">OnDefaultAction Method</span></span>](ihostpolicymanager-ondefaultaction-method.md)|<span data-ttu-id="6ca57-108">CLR이 스레드 abort 또는 unload에 대 한 응답으로 [ICLRPolicyManager:: SetDefaultAction](iclrpolicymanager-setdefaultaction-method.md) 에 대 한 호출로 지정 된 기본 작업을 수행 하려고 함을 호스트에 알립니다 <xref:System.AppDomain> .</span><span class="sxs-lookup"><span data-stu-id="6ca57-108">Notifies the host that the CLR is about to take the default action specified by a call to [ICLRPolicyManager::SetDefaultAction](iclrpolicymanager-setdefaultaction-method.md) in response to a thread abort or <xref:System.AppDomain> unload.</span></span>|  
|[<span data-ttu-id="6ca57-109">OnFailure 메서드</span><span class="sxs-lookup"><span data-stu-id="6ca57-109">OnFailure Method</span></span>](ihostpolicymanager-onfailure-method.md)|<span data-ttu-id="6ca57-110">리소스 할당 또는 재사용 실패에 대 한 응답으로 CLR이 [ICLRPolicyManager:: SetActionOnFailure](iclrpolicymanager-setactiononfailure-method.md) 호출에 지정 된 작업을 수행 하려고 함을 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="6ca57-110">Notifies the host that the CLR is about to take the action specified by a call to [ICLRPolicyManager::SetActionOnFailure](iclrpolicymanager-setactiononfailure-method.md) in response to a resource allocation or reclamation failure.</span></span>|  
|[<span data-ttu-id="6ca57-111">OnTimeout 메서드</span><span class="sxs-lookup"><span data-stu-id="6ca57-111">OnTimeout Method</span></span>](ihostpolicymanager-ontimeout-method.md)|<span data-ttu-id="6ca57-112">시간 제한에 대 한 응답으로 CLR이 [ICLRPolicyManager:: SetActionOnTimeout](iclrpolicymanager-setactionontimeout-method.md) 호출로 지정 된 작업을 수행 하려고 함을 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="6ca57-112">Notifies the host that the CLR is about to take the action specified by a call to [ICLRPolicyManager::SetActionOnTimeout](iclrpolicymanager-setactionontimeout-method.md) in response to a timeout.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6ca57-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6ca57-113">Requirements</span></span>  
 <span data-ttu-id="6ca57-114">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6ca57-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6ca57-115">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="6ca57-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6ca57-116">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ca57-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6ca57-117">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6ca57-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ca57-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6ca57-118">See also</span></span>

- [<span data-ttu-id="6ca57-119">EClrFailure 열거형</span><span class="sxs-lookup"><span data-stu-id="6ca57-119">EClrFailure Enumeration</span></span>](eclrfailure-enumeration.md)
- [<span data-ttu-id="6ca57-120">EClrOperation 열거형</span><span class="sxs-lookup"><span data-stu-id="6ca57-120">EClrOperation Enumeration</span></span>](eclroperation-enumeration.md)
- [<span data-ttu-id="6ca57-121">EPolicyAction 열거형</span><span class="sxs-lookup"><span data-stu-id="6ca57-121">EPolicyAction Enumeration</span></span>](epolicyaction-enumeration.md)
- [<span data-ttu-id="6ca57-122">ICLRPolicyManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6ca57-122">ICLRPolicyManager Interface</span></span>](iclrpolicymanager-interface.md)
- [<span data-ttu-id="6ca57-123">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6ca57-123">Hosting Interfaces</span></span>](hosting-interfaces.md)
