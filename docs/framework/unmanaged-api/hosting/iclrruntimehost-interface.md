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
ms.openlocfilehash: 568c63681b84d0ab3642d84e4a6715ad230582db
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120385"
---
# <a name="iclrruntimehost-interface"></a><span data-ttu-id="d7ec1-102">ICLRRuntimeHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d7ec1-102">ICLRRuntimeHost Interface</span></span>
<span data-ttu-id="d7ec1-103">.NET Framework 버전 1에서 제공 하는 [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) 인터페이스와 유사한 기능을 제공 하며 다음과 같이 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7ec1-103">Provides functionality similar to that of the [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) interface provided in the .NET Framework version 1, with the following changes:</span></span>  
  
- <span data-ttu-id="d7ec1-104">[SetHostControl](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-sethostcontrol-method.md) 메서드를 추가 하 여 호스트 컨트롤 인터페이스를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7ec1-104">The addition of the [SetHostControl](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-sethostcontrol-method.md) method to set the host control interface.</span></span>  
  
- <span data-ttu-id="d7ec1-105">`ICorRuntimeHost`에서 제공 하는 일부 메서드를 생략 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d7ec1-105">The omission of some methods provided by `ICorRuntimeHost`.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d7ec1-106">메서드</span><span class="sxs-lookup"><span data-stu-id="d7ec1-106">Methods</span></span>  
  
|<span data-ttu-id="d7ec1-107">메서드</span><span class="sxs-lookup"><span data-stu-id="d7ec1-107">Method</span></span>|<span data-ttu-id="d7ec1-108">설명</span><span class="sxs-lookup"><span data-stu-id="d7ec1-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d7ec1-109">ExecuteApplication 메서드</span><span class="sxs-lookup"><span data-stu-id="d7ec1-109">ExecuteApplication Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-executeapplication-method.md)|<span data-ttu-id="d7ec1-110">매니페스트 기반 ClickOnce 배포 시나리오에서 새 도메인에 활성화 될 응용 프로그램을 지정 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d7ec1-110">Used in manifest-based ClickOnce deployment scenarios to specify the application to be activated in a new domain.</span></span>|  
|[<span data-ttu-id="d7ec1-111">ExecuteInAppDomain 메서드</span><span class="sxs-lookup"><span data-stu-id="d7ec1-111">ExecuteInAppDomain Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-executeinappdomain-method.md)|<span data-ttu-id="d7ec1-112">지정 된 관리 코드를 실행할 <xref:System.AppDomain>를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7ec1-112">Specifies the <xref:System.AppDomain> in which to execute the specified managed code.</span></span>|  
|[<span data-ttu-id="d7ec1-113">ExecuteInDefaultAppDomain 메서드</span><span class="sxs-lookup"><span data-stu-id="d7ec1-113">ExecuteInDefaultAppDomain Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-executeindefaultappdomain-method.md)|<span data-ttu-id="d7ec1-114">지정 된 어셈블리에서 지정 된 형식의 지정 된 메서드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7ec1-114">Invokes the specified method of the specified type in the specified assembly.</span></span>|  
|[<span data-ttu-id="d7ec1-115">GetCLRControl 메서드</span><span class="sxs-lookup"><span data-stu-id="d7ec1-115">GetCLRControl Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-getclrcontrol-method.md)|<span data-ttu-id="d7ec1-116">호스트가 CLR (공용 언어 런타임)의 측면을 사용자 지정 하는 데 사용할 수 있는 [ICLRControl](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md) 형식의 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="d7ec1-116">Gets an interface pointer of type [ICLRControl](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md) that hosts can use to customize aspects of the common language runtime (CLR).</span></span>|  
|[<span data-ttu-id="d7ec1-117">GetCurrentAppDomainId 메서드</span><span class="sxs-lookup"><span data-stu-id="d7ec1-117">GetCurrentAppDomainId Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-getcurrentappdomainid-method.md)|<span data-ttu-id="d7ec1-118">현재 실행 중인 <xref:System.AppDomain>의 숫자 식별자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="d7ec1-118">Gets the numeric identifier of the <xref:System.AppDomain> that is currently executing.</span></span>|  
|[<span data-ttu-id="d7ec1-119">SetHostControl 메서드</span><span class="sxs-lookup"><span data-stu-id="d7ec1-119">SetHostControl Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-sethostcontrol-method.md)|<span data-ttu-id="d7ec1-120">호스트 컨트롤 인터페이스를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7ec1-120">Sets the host control interface.</span></span> <span data-ttu-id="d7ec1-121">`Start`를 호출 하기 전에 `SetHostControl`를 호출 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7ec1-121">You must call `SetHostControl` before calling `Start`.</span></span>|  
|[<span data-ttu-id="d7ec1-122">Start 메서드</span><span class="sxs-lookup"><span data-stu-id="d7ec1-122">Start Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md)|<span data-ttu-id="d7ec1-123">CLR을 프로세스로 초기화 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7ec1-123">Initializes the CLR into a process.</span></span>|  
|[<span data-ttu-id="d7ec1-124">Stop 메서드</span><span class="sxs-lookup"><span data-stu-id="d7ec1-124">Stop Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-stop-method.md)|<span data-ttu-id="d7ec1-125">런타임에의 한 코드 실행을 중지 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7ec1-125">Stops the execution of code by the runtime.</span></span>|  
|[<span data-ttu-id="d7ec1-126">UnloadAppDomain 메서드</span><span class="sxs-lookup"><span data-stu-id="d7ec1-126">UnloadAppDomain Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-unloadappdomain-method.md)|<span data-ttu-id="d7ec1-127">지정 된 숫자 식별자에 해당 하는 <xref:System.AppDomain>를 언로드합니다.</span><span class="sxs-lookup"><span data-stu-id="d7ec1-127">Unloads the <xref:System.AppDomain> that corresponds to the specified numeric identifier.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d7ec1-128">주의</span><span class="sxs-lookup"><span data-stu-id="d7ec1-128">Remarks</span></span>  
 <span data-ttu-id="d7ec1-129">.NET Framework 4부터 [ICLRMetaHost](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md) 인터페이스를 사용 하 여 [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) 인터페이스에 대 한 포인터를 가져온 다음 [ICLRRuntimeInfo:: getinterface](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getinterface-method.md) 메서드를 호출 하 여 `ICLRRuntimeHost`에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="d7ec1-129">Starting with the .NET Framework 4, use the [ICLRMetaHost](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md) interface to get a pointer to the [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface, and then call the [ICLRRuntimeInfo::GetInterface](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getinterface-method.md) method to get a pointer to `ICLRRuntimeHost`.</span></span> <span data-ttu-id="d7ec1-130">이전 버전의 .NET Framework에서 호스트 `ICLRRuntimeHost` [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) 또는 [CorBindToCurrentRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md)를 호출 하 여 해당 인스턴스에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="d7ec1-130">In earlier versions of the .NET Framework, the host gets a pointer to an `ICLRRuntimeHost` instance by calling [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) or [CorBindToCurrentRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md).</span></span> <span data-ttu-id="d7ec1-131">.NET Framework 버전 2.0에 제공 된 기술의 구현을 제공 하려면 `ICorRuntimeHost`대신 `ICLRRuntimeHost`를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7ec1-131">To provide implementations of any of the technologies provided in the .NET Framework version 2.0, you must use `ICLRRuntimeHost` instead of `ICorRuntimeHost`.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="d7ec1-132">매니페스트 기반 응용 프로그램을 활성화 하기 위해 [Executeapplication](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-executeapplication-method.md) 메서드를 호출 하기 전에 [Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) 메서드를 호출 하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="d7ec1-132">Do not call the [Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) method before calling the [ExecuteApplication](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-executeapplication-method.md) method to activate a manifest-based application.</span></span> <span data-ttu-id="d7ec1-133">`Start` 메서드를 먼저 호출 하면 `ExecuteApplication` 메서드 호출이 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7ec1-133">If the `Start` method is called first, the `ExecuteApplication` method call will fail.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d7ec1-134">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d7ec1-134">Requirements</span></span>  
 <span data-ttu-id="d7ec1-135">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d7ec1-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d7ec1-136">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="d7ec1-136">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d7ec1-137">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d7ec1-137">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d7ec1-138">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d7ec1-138">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7ec1-139">참조</span><span class="sxs-lookup"><span data-stu-id="d7ec1-139">See also</span></span>

- [<span data-ttu-id="d7ec1-140">CorBindToCurrentRuntime 함수</span><span class="sxs-lookup"><span data-stu-id="d7ec1-140">CorBindToCurrentRuntime Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md)
- [<span data-ttu-id="d7ec1-141">CorBindToRuntimeEx 함수</span><span class="sxs-lookup"><span data-stu-id="d7ec1-141">CorBindToRuntimeEx Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)
- [<span data-ttu-id="d7ec1-142">ICLRControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d7ec1-142">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="d7ec1-143">ICorRuntimeHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d7ec1-143">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
- [<span data-ttu-id="d7ec1-144">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d7ec1-144">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="d7ec1-145">CLRRuntimeHost Coclass</span><span class="sxs-lookup"><span data-stu-id="d7ec1-145">CLRRuntimeHost Coclass</span></span>](../../../../docs/framework/unmanaged-api/hosting/clrruntimehost-coclass.md)
