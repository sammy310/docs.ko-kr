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
ms.openlocfilehash: 6ba7b7adc104db528293d77c3591370c6ce02c25
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73128596"
---
# <a name="ihostpolicymanager-interface"></a><span data-ttu-id="1c5ab-102">IHostPolicyManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1c5ab-102">IHostPolicyManager Interface</span></span>
<span data-ttu-id="1c5ab-103">중단, 시간 초과 또는 오류가 발생 하는 경우 CLR (공용 언어 런타임)에서 수행 하는 작업을 호스트에 알리는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c5ab-103">Provides methods that notify the host of the actions the common language runtime (CLR) performs in case of aborts, timeouts, or failures.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1c5ab-104">메서드</span><span class="sxs-lookup"><span data-stu-id="1c5ab-104">Methods</span></span>  
  
|<span data-ttu-id="1c5ab-105">메서드</span><span class="sxs-lookup"><span data-stu-id="1c5ab-105">Method</span></span>|<span data-ttu-id="1c5ab-106">설명</span><span class="sxs-lookup"><span data-stu-id="1c5ab-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1c5ab-107">OnDefaultAction 메서드</span><span class="sxs-lookup"><span data-stu-id="1c5ab-107">OnDefaultAction Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-ondefaultaction-method.md)|<span data-ttu-id="1c5ab-108">CLR이 스레드 abort 또는 <xref:System.AppDomain> unload에 대 한 응답으로 [ICLRPolicyManager:: SetDefaultAction](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setdefaultaction-method.md) 에 대 한 호출로 지정 된 기본 작업을 수행 하려고 함을 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="1c5ab-108">Notifies the host that the CLR is about to take the default action specified by a call to [ICLRPolicyManager::SetDefaultAction](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setdefaultaction-method.md) in response to a thread abort or <xref:System.AppDomain> unload.</span></span>|  
|[<span data-ttu-id="1c5ab-109">OnFailure 메서드</span><span class="sxs-lookup"><span data-stu-id="1c5ab-109">OnFailure Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-onfailure-method.md)|<span data-ttu-id="1c5ab-110">리소스 할당 또는 재사용 실패에 대 한 응답으로 CLR이 [ICLRPolicyManager:: SetActionOnFailure](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactiononfailure-method.md) 호출에 지정 된 작업을 수행 하려고 함을 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="1c5ab-110">Notifies the host that the CLR is about to take the action specified by a call to [ICLRPolicyManager::SetActionOnFailure](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactiononfailure-method.md) in response to a resource allocation or reclamation failure.</span></span>|  
|[<span data-ttu-id="1c5ab-111">OnTimeout 메서드</span><span class="sxs-lookup"><span data-stu-id="1c5ab-111">OnTimeout Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-ontimeout-method.md)|<span data-ttu-id="1c5ab-112">시간 제한에 대 한 응답으로 CLR이 [ICLRPolicyManager:: SetActionOnTimeout](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactionontimeout-method.md) 호출로 지정 된 작업을 수행 하려고 함을 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="1c5ab-112">Notifies the host that the CLR is about to take the action specified by a call to [ICLRPolicyManager::SetActionOnTimeout](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactionontimeout-method.md) in response to a timeout.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="1c5ab-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1c5ab-113">Requirements</span></span>  
 <span data-ttu-id="1c5ab-114">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1c5ab-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1c5ab-115">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="1c5ab-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1c5ab-116">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c5ab-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1c5ab-117">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1c5ab-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c5ab-118">참조</span><span class="sxs-lookup"><span data-stu-id="1c5ab-118">See also</span></span>

- [<span data-ttu-id="1c5ab-119">EClrFailure 열거형</span><span class="sxs-lookup"><span data-stu-id="1c5ab-119">EClrFailure Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)
- [<span data-ttu-id="1c5ab-120">EClrOperation 열거형</span><span class="sxs-lookup"><span data-stu-id="1c5ab-120">EClrOperation Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)
- [<span data-ttu-id="1c5ab-121">EPolicyAction 열거형</span><span class="sxs-lookup"><span data-stu-id="1c5ab-121">EPolicyAction Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)
- [<span data-ttu-id="1c5ab-122">ICLRPolicyManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1c5ab-122">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
- [<span data-ttu-id="1c5ab-123">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1c5ab-123">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
