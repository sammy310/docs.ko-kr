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
ms.openlocfilehash: 3c85bcbe8aee453b19217ebd1f48feea113e3bb1
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731222"
---
# <a name="ihostpolicymanager-interface"></a><span data-ttu-id="a5b29-102">IHostPolicyManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a5b29-102">IHostPolicyManager Interface</span></span>

<span data-ttu-id="a5b29-103">중단, 시간 초과 또는 오류가 발생 하는 경우 CLR (공용 언어 런타임)에서 수행 하는 작업을 호스트에 알리는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a5b29-103">Provides methods that notify the host of the actions the common language runtime (CLR) performs in case of aborts, timeouts, or failures.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a5b29-104">메서드</span><span class="sxs-lookup"><span data-stu-id="a5b29-104">Methods</span></span>  
  
|<span data-ttu-id="a5b29-105">메서드</span><span class="sxs-lookup"><span data-stu-id="a5b29-105">Method</span></span>|<span data-ttu-id="a5b29-106">설명</span><span class="sxs-lookup"><span data-stu-id="a5b29-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a5b29-107">OnDefaultAction 메서드</span><span class="sxs-lookup"><span data-stu-id="a5b29-107">OnDefaultAction Method</span></span>](ihostpolicymanager-ondefaultaction-method.md)|<span data-ttu-id="a5b29-108">CLR이 스레드 abort 또는 unload에 대 한 응답으로 [ICLRPolicyManager:: SetDefaultAction](iclrpolicymanager-setdefaultaction-method.md) 에 대 한 호출로 지정 된 기본 작업을 수행 하려고 함을 호스트에 알립니다 <xref:System.AppDomain> .</span><span class="sxs-lookup"><span data-stu-id="a5b29-108">Notifies the host that the CLR is about to take the default action specified by a call to [ICLRPolicyManager::SetDefaultAction](iclrpolicymanager-setdefaultaction-method.md) in response to a thread abort or <xref:System.AppDomain> unload.</span></span>|  
|[<span data-ttu-id="a5b29-109">OnFailure 메서드</span><span class="sxs-lookup"><span data-stu-id="a5b29-109">OnFailure Method</span></span>](ihostpolicymanager-onfailure-method.md)|<span data-ttu-id="a5b29-110">리소스 할당 또는 재사용 실패에 대 한 응답으로 CLR이 [ICLRPolicyManager:: SetActionOnFailure](iclrpolicymanager-setactiononfailure-method.md) 호출에 지정 된 작업을 수행 하려고 함을 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="a5b29-110">Notifies the host that the CLR is about to take the action specified by a call to [ICLRPolicyManager::SetActionOnFailure](iclrpolicymanager-setactiononfailure-method.md) in response to a resource allocation or reclamation failure.</span></span>|  
|[<span data-ttu-id="a5b29-111">OnTimeout 메서드</span><span class="sxs-lookup"><span data-stu-id="a5b29-111">OnTimeout Method</span></span>](ihostpolicymanager-ontimeout-method.md)|<span data-ttu-id="a5b29-112">시간 제한에 대 한 응답으로 CLR이 [ICLRPolicyManager:: SetActionOnTimeout](iclrpolicymanager-setactionontimeout-method.md) 호출로 지정 된 작업을 수행 하려고 함을 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="a5b29-112">Notifies the host that the CLR is about to take the action specified by a call to [ICLRPolicyManager::SetActionOnTimeout](iclrpolicymanager-setactionontimeout-method.md) in response to a timeout.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a5b29-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a5b29-113">Requirements</span></span>  

 <span data-ttu-id="a5b29-114">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a5b29-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a5b29-115">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="a5b29-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a5b29-116">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a5b29-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a5b29-117">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a5b29-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5b29-118">참조</span><span class="sxs-lookup"><span data-stu-id="a5b29-118">See also</span></span>

- [<span data-ttu-id="a5b29-119">EClrFailure 열거형</span><span class="sxs-lookup"><span data-stu-id="a5b29-119">EClrFailure Enumeration</span></span>](eclrfailure-enumeration.md)
- [<span data-ttu-id="a5b29-120">EClrOperation 열거형</span><span class="sxs-lookup"><span data-stu-id="a5b29-120">EClrOperation Enumeration</span></span>](eclroperation-enumeration.md)
- [<span data-ttu-id="a5b29-121">EPolicyAction 열거형</span><span class="sxs-lookup"><span data-stu-id="a5b29-121">EPolicyAction Enumeration</span></span>](epolicyaction-enumeration.md)
- [<span data-ttu-id="a5b29-122">ICLRPolicyManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a5b29-122">ICLRPolicyManager Interface</span></span>](iclrpolicymanager-interface.md)
- [<span data-ttu-id="a5b29-123">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a5b29-123">Hosting Interfaces</span></span>](hosting-interfaces.md)
