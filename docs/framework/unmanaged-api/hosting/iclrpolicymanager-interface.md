---
title: ICLRPolicyManager 인터페이스
ms.date: 03/30/2017
api_name:
- ICLRPolicyManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRPolicyManager
helpviewer_keywords:
- ICLRPolicyManager interface [.NET Framework hosting]
ms.assetid: 5c834aa1-f2db-408a-b230-c7bec093d364
topic_type:
- apiref
ms.openlocfilehash: 59aa904d4c67326b60381d3476eaab179d7fa42b
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140811"
---
# <a name="iclrpolicymanager-interface"></a><span data-ttu-id="2a625-102">ICLRPolicyManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2a625-102">ICLRPolicyManager Interface</span></span>
<span data-ttu-id="2a625-103">호스트에서 오류 및 시간 제한이 발생 하는 경우 수행할 정책 작업을 지정할 수 있도록 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a625-103">Provides methods that allow the host to specify policy actions to be taken in the event of failures and timeouts.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="2a625-104">메서드</span><span class="sxs-lookup"><span data-stu-id="2a625-104">Methods</span></span>  
  
|<span data-ttu-id="2a625-105">메서드</span><span class="sxs-lookup"><span data-stu-id="2a625-105">Method</span></span>|<span data-ttu-id="2a625-106">설명</span><span class="sxs-lookup"><span data-stu-id="2a625-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="2a625-107">SetActionOnFailure 메서드</span><span class="sxs-lookup"><span data-stu-id="2a625-107">SetActionOnFailure Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactiononfailure-method.md)|<span data-ttu-id="2a625-108">지정 된 오류가 발생할 때 CLR (공용 언어 런타임)이 수행 해야 하는 정책 동작을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a625-108">Specifies the policy action the common language runtime (CLR) should take when the specified failure occurs.</span></span>|  
|[<span data-ttu-id="2a625-109">SetActionOnTimeout 메서드</span><span class="sxs-lookup"><span data-stu-id="2a625-109">SetActionOnTimeout Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactionontimeout-method.md)|<span data-ttu-id="2a625-110">지정 된 작업의 제한 시간이 초과 될 때 CLR에서 수행 해야 하는 정책 동작을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a625-110">Specifies the policy action the CLR should take when the specified operation times out.</span></span>|  
|[<span data-ttu-id="2a625-111">SetDefaultAction 메서드</span><span class="sxs-lookup"><span data-stu-id="2a625-111">SetDefaultAction Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setdefaultaction-method.md)|<span data-ttu-id="2a625-112">지정 된 작업이 발생 했을 때 CLR에서 수행 해야 하는 정책 동작을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a625-112">Specifies the policy action the CLR should take when the specified operation occurs.</span></span>|  
|[<span data-ttu-id="2a625-113">SetTimeout 메서드</span><span class="sxs-lookup"><span data-stu-id="2a625-113">SetTimeout Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-settimeout-method.md)|<span data-ttu-id="2a625-114">지정 된 작업에 대 한 시간 제한 값을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a625-114">Sets a timeout value for the specified operation.</span></span>|  
|[<span data-ttu-id="2a625-115">SetTimeoutAndAction 메서드</span><span class="sxs-lookup"><span data-stu-id="2a625-115">SetTimeoutAndAction Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-settimeoutandaction-method.md)|<span data-ttu-id="2a625-116">지정 된 작업에 대 한 시간 제한 값을 설정 하 고 작업이 발생 했을 때 CLR에서 수행 해야 하는 정책 동작을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a625-116">Sets a timeout value for the specified operation, and specifies the policy action the CLR should take when the operation occurs.</span></span>|  
|[<span data-ttu-id="2a625-117">SetUnhandledExceptionPolicy 메서드</span><span class="sxs-lookup"><span data-stu-id="2a625-117">SetUnhandledExceptionPolicy Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setunhandledexceptionpolicy-method.md)|<span data-ttu-id="2a625-118">처리 되지 않은 예외가 발생할 때 CLR의 동작을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a625-118">Specifies the behavior of the CLR when an unhandled exception occurs.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="2a625-119">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2a625-119">Requirements</span></span>  
 <span data-ttu-id="2a625-120">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2a625-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2a625-121">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="2a625-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2a625-122">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2a625-122">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2a625-123">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2a625-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a625-124">참조</span><span class="sxs-lookup"><span data-stu-id="2a625-124">See also</span></span>

- [<span data-ttu-id="2a625-125">EClrFailure 열거형</span><span class="sxs-lookup"><span data-stu-id="2a625-125">EClrFailure Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)
- [<span data-ttu-id="2a625-126">EClrOperation 열거형</span><span class="sxs-lookup"><span data-stu-id="2a625-126">EClrOperation Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)
- [<span data-ttu-id="2a625-127">EPolicyAction 열거형</span><span class="sxs-lookup"><span data-stu-id="2a625-127">EPolicyAction Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)
- [<span data-ttu-id="2a625-128">ICLRControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2a625-128">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
