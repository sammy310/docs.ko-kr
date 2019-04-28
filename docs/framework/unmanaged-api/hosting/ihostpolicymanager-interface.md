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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cf9d903b4e44ea7a185ad8b3b71b7a5da2f2bda3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61760118"
---
# <a name="ihostpolicymanager-interface"></a><span data-ttu-id="4fcb9-102">IHostPolicyManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4fcb9-102">IHostPolicyManager Interface</span></span>
<span data-ttu-id="4fcb9-103">중단, 제한 시간 또는 오류는 CLR (공용 언어 런타임)의 경우 수행 하는 동작의 호스트에 알리는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="4fcb9-103">Provides methods that notify the host of the actions the common language runtime (CLR) performs in case of aborts, timeouts, or failures.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="4fcb9-104">메서드</span><span class="sxs-lookup"><span data-stu-id="4fcb9-104">Methods</span></span>  
  
|<span data-ttu-id="4fcb9-105">메서드</span><span class="sxs-lookup"><span data-stu-id="4fcb9-105">Method</span></span>|<span data-ttu-id="4fcb9-106">설명</span><span class="sxs-lookup"><span data-stu-id="4fcb9-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="4fcb9-107">OnDefaultAction 메서드</span><span class="sxs-lookup"><span data-stu-id="4fcb9-107">OnDefaultAction Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-ondefaultaction-method.md)|<span data-ttu-id="4fcb9-108">호출 하 여 지정 된 기본 작업을 수행 하려고 합니다. CLR은 호스트에 알리는 [iclrpolicymanager:: Setdefaultaction](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setdefaultaction-method.md) 대 한 응답으로 스레드 중단 또는 <xref:System.AppDomain> 언로드합니다.</span><span class="sxs-lookup"><span data-stu-id="4fcb9-108">Notifies the host that the CLR is about to take the default action specified by a call to [ICLRPolicyManager::SetDefaultAction](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setdefaultaction-method.md) in response to a thread abort or <xref:System.AppDomain> unload.</span></span>|  
|[<span data-ttu-id="4fcb9-109">OnFailure 메서드</span><span class="sxs-lookup"><span data-stu-id="4fcb9-109">OnFailure Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-onfailure-method.md)|<span data-ttu-id="4fcb9-110">호출 하 여 지정 된 작업을 수행 하려고 합니다. CLR은 호스트에 알리는 [iclrpolicymanager:: Setactiononfailure](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactiononfailure-method.md) 리소스 확보 또는 할당 실패에 대 한 응답에서입니다.</span><span class="sxs-lookup"><span data-stu-id="4fcb9-110">Notifies the host that the CLR is about to take the action specified by a call to [ICLRPolicyManager::SetActionOnFailure](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactiononfailure-method.md) in response to a resource allocation or reclamation failure.</span></span>|  
|[<span data-ttu-id="4fcb9-111">OnTimeout 메서드</span><span class="sxs-lookup"><span data-stu-id="4fcb9-111">OnTimeout Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-ontimeout-method.md)|<span data-ttu-id="4fcb9-112">호출 하 여 지정 된 작업을 수행 하려고 합니다. CLR은 호스트에 알리는 [iclrpolicymanager:: Setactionontimeout](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactionontimeout-method.md) 제한 시간에 대 한 응답에서입니다.</span><span class="sxs-lookup"><span data-stu-id="4fcb9-112">Notifies the host that the CLR is about to take the action specified by a call to [ICLRPolicyManager::SetActionOnTimeout](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactionontimeout-method.md) in response to a timeout.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4fcb9-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4fcb9-113">Requirements</span></span>  
 <span data-ttu-id="4fcb9-114">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="4fcb9-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4fcb9-115">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="4fcb9-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4fcb9-116">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="4fcb9-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4fcb9-117">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4fcb9-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4fcb9-118">참고자료</span><span class="sxs-lookup"><span data-stu-id="4fcb9-118">See also</span></span>

- [<span data-ttu-id="4fcb9-119">EClrFailure 열거형</span><span class="sxs-lookup"><span data-stu-id="4fcb9-119">EClrFailure Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)
- [<span data-ttu-id="4fcb9-120">EClrOperation 열거형</span><span class="sxs-lookup"><span data-stu-id="4fcb9-120">EClrOperation Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)
- [<span data-ttu-id="4fcb9-121">EPolicyAction 열거형</span><span class="sxs-lookup"><span data-stu-id="4fcb9-121">EPolicyAction Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)
- [<span data-ttu-id="4fcb9-122">ICLRPolicyManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4fcb9-122">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
- [<span data-ttu-id="4fcb9-123">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4fcb9-123">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
