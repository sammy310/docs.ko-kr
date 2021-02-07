---
description: '자세히 알아보기: ICLRRuntimeHost 인터페이스'
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
ms.openlocfilehash: 92bab42fa1cf2cca5caa0eb039c88fec3e65390c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99753889"
---
# <a name="iclrruntimehost-interface"></a><span data-ttu-id="fa3cb-103">ICLRRuntimeHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fa3cb-103">ICLRRuntimeHost Interface</span></span>

<span data-ttu-id="fa3cb-104">.NET Framework 버전 1에서 제공 하는 [ICorRuntimeHost](icorruntimehost-interface.md) 인터페이스와 유사한 기능을 제공 하며 다음과 같이 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa3cb-104">Provides functionality similar to that of the [ICorRuntimeHost](icorruntimehost-interface.md) interface provided in the .NET Framework version 1, with the following changes:</span></span>  
  
- <span data-ttu-id="fa3cb-105">[SetHostControl](iclrruntimehost-sethostcontrol-method.md) 메서드를 추가 하 여 호스트 컨트롤 인터페이스를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa3cb-105">The addition of the [SetHostControl](iclrruntimehost-sethostcontrol-method.md) method to set the host control interface.</span></span>  
  
- <span data-ttu-id="fa3cb-106">에서 제공 하는 일부 메서드를 생략 하는 것입니다 `ICorRuntimeHost` .</span><span class="sxs-lookup"><span data-stu-id="fa3cb-106">The omission of some methods provided by `ICorRuntimeHost`.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="fa3cb-107">메서드</span><span class="sxs-lookup"><span data-stu-id="fa3cb-107">Methods</span></span>  
  
|<span data-ttu-id="fa3cb-108">메서드</span><span class="sxs-lookup"><span data-stu-id="fa3cb-108">Method</span></span>|<span data-ttu-id="fa3cb-109">설명</span><span class="sxs-lookup"><span data-stu-id="fa3cb-109">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="fa3cb-110">ExecuteApplication 메서드</span><span class="sxs-lookup"><span data-stu-id="fa3cb-110">ExecuteApplication Method</span></span>](iclrruntimehost-executeapplication-method.md)|<span data-ttu-id="fa3cb-111">매니페스트 기반 ClickOnce 배포 시나리오에서 새 도메인에 활성화 될 응용 프로그램을 지정 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fa3cb-111">Used in manifest-based ClickOnce deployment scenarios to specify the application to be activated in a new domain.</span></span>|  
|[<span data-ttu-id="fa3cb-112">ExecuteInAppDomain 메서드</span><span class="sxs-lookup"><span data-stu-id="fa3cb-112">ExecuteInAppDomain Method</span></span>](iclrruntimehost-executeinappdomain-method.md)|<span data-ttu-id="fa3cb-113">지정 된 <xref:System.AppDomain> 관리 코드를 실행할를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa3cb-113">Specifies the <xref:System.AppDomain> in which to execute the specified managed code.</span></span>|  
|[<span data-ttu-id="fa3cb-114">ExecuteInDefaultAppDomain 메서드</span><span class="sxs-lookup"><span data-stu-id="fa3cb-114">ExecuteInDefaultAppDomain Method</span></span>](iclrruntimehost-executeindefaultappdomain-method.md)|<span data-ttu-id="fa3cb-115">지정 된 어셈블리에서 지정 된 형식의 지정 된 메서드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa3cb-115">Invokes the specified method of the specified type in the specified assembly.</span></span>|  
|[<span data-ttu-id="fa3cb-116">GetCLRControl 메서드</span><span class="sxs-lookup"><span data-stu-id="fa3cb-116">GetCLRControl Method</span></span>](iclrruntimehost-getclrcontrol-method.md)|<span data-ttu-id="fa3cb-117">호스트가 CLR (공용 언어 런타임)의 측면을 사용자 지정 하는 데 사용할 수 있는 [ICLRControl](iclrcontrol-interface.md) 형식의 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="fa3cb-117">Gets an interface pointer of type [ICLRControl](iclrcontrol-interface.md) that hosts can use to customize aspects of the common language runtime (CLR).</span></span>|  
|[<span data-ttu-id="fa3cb-118">GetCurrentAppDomainId 메서드</span><span class="sxs-lookup"><span data-stu-id="fa3cb-118">GetCurrentAppDomainId Method</span></span>](iclrruntimehost-getcurrentappdomainid-method.md)|<span data-ttu-id="fa3cb-119">현재 실행 중인의 숫자 식별자를 가져옵니다 <xref:System.AppDomain> .</span><span class="sxs-lookup"><span data-stu-id="fa3cb-119">Gets the numeric identifier of the <xref:System.AppDomain> that is currently executing.</span></span>|  
|[<span data-ttu-id="fa3cb-120">SetHostControl 메서드</span><span class="sxs-lookup"><span data-stu-id="fa3cb-120">SetHostControl Method</span></span>](iclrruntimehost-sethostcontrol-method.md)|<span data-ttu-id="fa3cb-121">호스트 컨트롤 인터페이스를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa3cb-121">Sets the host control interface.</span></span> <span data-ttu-id="fa3cb-122">를 호출 하기 전에를 호출 해야 합니다 `SetHostControl` `Start` .</span><span class="sxs-lookup"><span data-stu-id="fa3cb-122">You must call `SetHostControl` before calling `Start`.</span></span>|  
|[<span data-ttu-id="fa3cb-123">Start 메서드</span><span class="sxs-lookup"><span data-stu-id="fa3cb-123">Start Method</span></span>](iclrruntimehost-start-method.md)|<span data-ttu-id="fa3cb-124">CLR을 프로세스로 초기화 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa3cb-124">Initializes the CLR into a process.</span></span>|  
|[<span data-ttu-id="fa3cb-125">Stop 메서드</span><span class="sxs-lookup"><span data-stu-id="fa3cb-125">Stop Method</span></span>](iclrruntimehost-stop-method.md)|<span data-ttu-id="fa3cb-126">런타임에의 한 코드 실행을 중지 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa3cb-126">Stops the execution of code by the runtime.</span></span>|  
|[<span data-ttu-id="fa3cb-127">UnloadAppDomain 메서드</span><span class="sxs-lookup"><span data-stu-id="fa3cb-127">UnloadAppDomain Method</span></span>](iclrruntimehost-unloadappdomain-method.md)|<span data-ttu-id="fa3cb-128">지정 된 <xref:System.AppDomain> 숫자 식별자에 해당 하는를 언로드합니다.</span><span class="sxs-lookup"><span data-stu-id="fa3cb-128">Unloads the <xref:System.AppDomain> that corresponds to the specified numeric identifier.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fa3cb-129">설명</span><span class="sxs-lookup"><span data-stu-id="fa3cb-129">Remarks</span></span>  

 <span data-ttu-id="fa3cb-130">.NET Framework 4부터 [ICLRMetaHost](iclrmetahost-interface.md) 인터페이스를 사용 하 여 [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) 인터페이스에 대 한 포인터를 가져온 다음 [ICLRRuntimeInfo:: getinterface](iclrruntimeinfo-getinterface-method.md) 메서드를 호출 하 여에 대 한 포인터를 가져옵니다 `ICLRRuntimeHost` .</span><span class="sxs-lookup"><span data-stu-id="fa3cb-130">Starting with the .NET Framework 4, use the [ICLRMetaHost](iclrmetahost-interface.md) interface to get a pointer to the [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) interface, and then call the [ICLRRuntimeInfo::GetInterface](iclrruntimeinfo-getinterface-method.md) method to get a pointer to `ICLRRuntimeHost`.</span></span> <span data-ttu-id="fa3cb-131">이전 버전의 .NET Framework에서 호스트는 `ICLRRuntimeHost` [CorBindToRuntimeEx](corbindtoruntimeex-function.md) 또는 [CorBindToCurrentRuntime](corbindtocurrentruntime-function.md)를 호출 하 여 인스턴스에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="fa3cb-131">In earlier versions of the .NET Framework, the host gets a pointer to an `ICLRRuntimeHost` instance by calling [CorBindToRuntimeEx](corbindtoruntimeex-function.md) or [CorBindToCurrentRuntime](corbindtocurrentruntime-function.md).</span></span> <span data-ttu-id="fa3cb-132">.NET Framework 버전 2.0에 제공 된 기술의 구현을 제공 하려면 대신를 사용 해야 합니다 `ICLRRuntimeHost` `ICorRuntimeHost` .</span><span class="sxs-lookup"><span data-stu-id="fa3cb-132">To provide implementations of any of the technologies provided in the .NET Framework version 2.0, you must use `ICLRRuntimeHost` instead of `ICorRuntimeHost`.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="fa3cb-133">매니페스트 기반 응용 프로그램을 활성화 하기 위해 [Executeapplication](iclrruntimehost-executeapplication-method.md) 메서드를 호출 하기 전에 [Start](iclrruntimehost-start-method.md) 메서드를 호출 하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="fa3cb-133">Do not call the [Start](iclrruntimehost-start-method.md) method before calling the [ExecuteApplication](iclrruntimehost-executeapplication-method.md) method to activate a manifest-based application.</span></span> <span data-ttu-id="fa3cb-134">메서드를 `Start` 먼저 호출 하면 `ExecuteApplication` 메서드 호출이 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa3cb-134">If the `Start` method is called first, the `ExecuteApplication` method call will fail.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fa3cb-135">요구 사항</span><span class="sxs-lookup"><span data-stu-id="fa3cb-135">Requirements</span></span>  

 <span data-ttu-id="fa3cb-136">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fa3cb-136">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fa3cb-137">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="fa3cb-137">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="fa3cb-138">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fa3cb-138">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fa3cb-139">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fa3cb-139">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa3cb-140">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fa3cb-140">See also</span></span>

- [<span data-ttu-id="fa3cb-141">CorBindToCurrentRuntime 함수</span><span class="sxs-lookup"><span data-stu-id="fa3cb-141">CorBindToCurrentRuntime Function</span></span>](corbindtocurrentruntime-function.md)
- [<span data-ttu-id="fa3cb-142">CorBindToRuntimeEx 함수</span><span class="sxs-lookup"><span data-stu-id="fa3cb-142">CorBindToRuntimeEx Function</span></span>](corbindtoruntimeex-function.md)
- [<span data-ttu-id="fa3cb-143">ICLRControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fa3cb-143">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="fa3cb-144">ICorRuntimeHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fa3cb-144">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)
- [<span data-ttu-id="fa3cb-145">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fa3cb-145">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="fa3cb-146">CLRRuntimeHost Coclass</span><span class="sxs-lookup"><span data-stu-id="fa3cb-146">CLRRuntimeHost Coclass</span></span>](clrruntimehost-coclass.md)
