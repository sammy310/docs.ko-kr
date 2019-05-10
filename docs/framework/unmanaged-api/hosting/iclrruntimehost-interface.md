---
title: ICLRRuntimeHost 인터페이스
ms.date: 03/30/2017
api_name:
- ICLRRuntimeHost
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeHost
helpviewer_keywords:
- ICLRRuntimeHost interface [.NET Framework hosting]
ms.assetid: cb0c5f65-3791-47bc-b833-2f84f4101ba5
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: da22cbfe06245d915bed6db9cba220fc32b38942
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64627138"
---
# <a name="iclrruntimehost-interface"></a><span data-ttu-id="60be3-102">ICLRRuntimeHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="60be3-102">ICLRRuntimeHost Interface</span></span>
<span data-ttu-id="60be3-103">유사한 기능을 제공 합니다 [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) 버전 1에서는 다음과 같이 변경을 사용 하 여.NET Framework에서 제공 하는 인터페이스:</span><span class="sxs-lookup"><span data-stu-id="60be3-103">Provides functionality similar to that of the [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) interface provided in the .NET Framework version 1, with the following changes:</span></span>  
  
- <span data-ttu-id="60be3-104">추가 된 [SetHostControl](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-sethostcontrol-method.md) 호스트 컨트롤 인터페이스를 설정 하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="60be3-104">The addition of the [SetHostControl](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-sethostcontrol-method.md) method to set the host control interface.</span></span>  
  
- <span data-ttu-id="60be3-105">제공 하는 몇 가지 방법 중 생략 `ICorRuntimeHost`합니다.</span><span class="sxs-lookup"><span data-stu-id="60be3-105">The omission of some methods provided by `ICorRuntimeHost`.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="60be3-106">메서드</span><span class="sxs-lookup"><span data-stu-id="60be3-106">Methods</span></span>  
  
|<span data-ttu-id="60be3-107">메서드</span><span class="sxs-lookup"><span data-stu-id="60be3-107">Method</span></span>|<span data-ttu-id="60be3-108">설명</span><span class="sxs-lookup"><span data-stu-id="60be3-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="60be3-109">ExecuteApplication 메서드</span><span class="sxs-lookup"><span data-stu-id="60be3-109">ExecuteApplication Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-executeapplication-method.md)|<span data-ttu-id="60be3-110">ClickOnce 배포 매니페스트 기반 시나리오에서 새 도메인에서 활성화 될 응용 프로그램을 지정 하는 데 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="60be3-110">Used in manifest-based ClickOnce deployment scenarios to specify the application to be activated in a new domain.</span></span>|  
|[<span data-ttu-id="60be3-111">ExecuteInAppDomain 메서드</span><span class="sxs-lookup"><span data-stu-id="60be3-111">ExecuteInAppDomain Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-executeinappdomain-method.md)|<span data-ttu-id="60be3-112">지정 된 <xref:System.AppDomain> 지정 된 관리 되는 코드를 실행 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="60be3-112">Specifies the <xref:System.AppDomain> in which to execute the specified managed code.</span></span>|  
|[<span data-ttu-id="60be3-113">ExecuteInDefaultAppDomain 메서드</span><span class="sxs-lookup"><span data-stu-id="60be3-113">ExecuteInDefaultAppDomain Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-executeindefaultappdomain-method.md)|<span data-ttu-id="60be3-114">지정된 된 어셈블리에 지정 된 형식의 지정된 된 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="60be3-114">Invokes the specified method of the specified type in the specified assembly.</span></span>|  
|[<span data-ttu-id="60be3-115">GetCLRControl 메서드</span><span class="sxs-lookup"><span data-stu-id="60be3-115">GetCLRControl Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-getclrcontrol-method.md)|<span data-ttu-id="60be3-116">형식의 인터페이스 포인터를 가져옵니다 [ICLRControl](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md) 호스트의 CLR (공용 언어 런타임)의 측면을 사용자 지정 하는 데 사용할 수 있는 합니다.</span><span class="sxs-lookup"><span data-stu-id="60be3-116">Gets an interface pointer of type [ICLRControl](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md) that hosts can use to customize aspects of the common language runtime (CLR).</span></span>|  
|[<span data-ttu-id="60be3-117">GetCurrentAppDomainId 메서드</span><span class="sxs-lookup"><span data-stu-id="60be3-117">GetCurrentAppDomainId Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-getcurrentappdomainid-method.md)|<span data-ttu-id="60be3-118">숫자 식별자를 가져옵니다는 <xref:System.AppDomain> 현재 실행 되는 합니다.</span><span class="sxs-lookup"><span data-stu-id="60be3-118">Gets the numeric identifier of the <xref:System.AppDomain> that is currently executing.</span></span>|  
|[<span data-ttu-id="60be3-119">SetHostControl 메서드</span><span class="sxs-lookup"><span data-stu-id="60be3-119">SetHostControl Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-sethostcontrol-method.md)|<span data-ttu-id="60be3-120">호스트 컨트롤 인터페이스를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="60be3-120">Sets the host control interface.</span></span> <span data-ttu-id="60be3-121">호출 해야 합니다 `SetHostControl` 호출 하기 전에 `Start`입니다.</span><span class="sxs-lookup"><span data-stu-id="60be3-121">You must call `SetHostControl` before calling `Start`.</span></span>|  
|[<span data-ttu-id="60be3-122">Start 메서드</span><span class="sxs-lookup"><span data-stu-id="60be3-122">Start Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md)|<span data-ttu-id="60be3-123">프로세스에 CLR을 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="60be3-123">Initializes the CLR into a process.</span></span>|  
|[<span data-ttu-id="60be3-124">Stop 메서드</span><span class="sxs-lookup"><span data-stu-id="60be3-124">Stop Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-stop-method.md)|<span data-ttu-id="60be3-125">런타임에서 코드의 실행을 중지합니다.</span><span class="sxs-lookup"><span data-stu-id="60be3-125">Stops the execution of code by the runtime.</span></span>|  
|[<span data-ttu-id="60be3-126">UnloadAppDomain 메서드</span><span class="sxs-lookup"><span data-stu-id="60be3-126">UnloadAppDomain Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-unloadappdomain-method.md)|<span data-ttu-id="60be3-127">언로드를 <xref:System.AppDomain> 지정된 된 숫자 식별자에 해당 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="60be3-127">Unloads the <xref:System.AppDomain> that corresponds to the specified numeric identifier.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="60be3-128">설명</span><span class="sxs-lookup"><span data-stu-id="60be3-128">Remarks</span></span>  
 <span data-ttu-id="60be3-129">부터 [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]를 사용 하 여는 [ICLRMetaHost](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md) 인터페이스에 대 한 포인터를 가져오려면를 [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) 인터페이스를 고를 호출 하는 [iclrruntimeinfo:: Getinterface](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getinterface-method.md) 에 대 한 포인터를 가져올 메서드를 `ICLRRuntimeHost`입니다.</span><span class="sxs-lookup"><span data-stu-id="60be3-129">Starting with the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)], use the [ICLRMetaHost](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md) interface to get a pointer to the [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface, and then call the [ICLRRuntimeInfo::GetInterface](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getinterface-method.md) method to get a pointer to `ICLRRuntimeHost`.</span></span> <span data-ttu-id="60be3-130">.NET Framework의 이전 버전에서는 호스트에 대 한 포인터를 가져옵니다는 `ICLRRuntimeHost` 를 호출 하 여 인스턴스 [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) 하거나 [CorBindToCurrentRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="60be3-130">In earlier versions of the .NET Framework, the host gets a pointer to an `ICLRRuntimeHost` instance by calling [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) or [CorBindToCurrentRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md).</span></span> <span data-ttu-id="60be3-131">.NET Framework 버전 2.0에서에서 제공 하는 기술을의 구현에 제공 하려면 사용 해야 `ICLRRuntimeHost` 대신 `ICorRuntimeHost`합니다.</span><span class="sxs-lookup"><span data-stu-id="60be3-131">To provide implementations of any of the technologies provided in the .NET Framework version 2.0, you must use `ICLRRuntimeHost` instead of `ICorRuntimeHost`.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="60be3-132">호출 하지 마십시오 합니다 [시작](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) 메서드를 호출 하기 전에 [ExecuteApplication](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-executeapplication-method.md) 매니페스트 기반 응용 프로그램을 활성화 하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="60be3-132">Do not call the [Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) method before calling the [ExecuteApplication](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-executeapplication-method.md) method to activate a manifest-based application.</span></span> <span data-ttu-id="60be3-133">경우는 `Start` 메서드를 먼저 호출 된 `ExecuteApplication` 메서드 호출이 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="60be3-133">If the `Start` method is called first, the `ExecuteApplication` method call will fail.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="60be3-134">요구 사항</span><span class="sxs-lookup"><span data-stu-id="60be3-134">Requirements</span></span>  
 <span data-ttu-id="60be3-135">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="60be3-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="60be3-136">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="60be3-136">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="60be3-137">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="60be3-137">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="60be3-138">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="60be3-138">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60be3-139">참고자료</span><span class="sxs-lookup"><span data-stu-id="60be3-139">See also</span></span>

- [<span data-ttu-id="60be3-140">CorBindToCurrentRuntime 함수</span><span class="sxs-lookup"><span data-stu-id="60be3-140">CorBindToCurrentRuntime Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md)
- [<span data-ttu-id="60be3-141">CorBindToRuntimeEx 함수</span><span class="sxs-lookup"><span data-stu-id="60be3-141">CorBindToRuntimeEx Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)
- [<span data-ttu-id="60be3-142">ICLRControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="60be3-142">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="60be3-143">ICorRuntimeHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="60be3-143">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
- [<span data-ttu-id="60be3-144">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="60be3-144">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="60be3-145">CLRRuntimeHost Coclass</span><span class="sxs-lookup"><span data-stu-id="60be3-145">CLRRuntimeHost Coclass</span></span>](../../../../docs/framework/unmanaged-api/hosting/clrruntimehost-coclass.md)
