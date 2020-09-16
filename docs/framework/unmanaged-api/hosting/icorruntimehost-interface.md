---
title: ICorRuntimeHost 인터페이스
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost
helpviewer_keywords:
- ICorRuntimeHost interface [.NET Framework hosting]
ms.assetid: 4369533d-7834-4497-bc37-bfea0ad737b1
topic_type:
- apiref
ms.openlocfilehash: 420f22a242a20f8bdf5d5b84f47a297a2f503db0
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "90546023"
---
# <a name="icorruntimehost-interface"></a><span data-ttu-id="5a7d6-102">ICorRuntimeHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5a7d6-102">ICorRuntimeHost Interface</span></span>
<span data-ttu-id="5a7d6-103">호스트에서 CLR (공용 언어 런타임)을 명시적으로 시작 및 중지 하 고, 응용 프로그램 도메인을 만들고 구성 하 고, 기본 도메인에 액세스 하 고, 프로세스에서 실행 되는 모든 도메인을 열거 하는 데 사용할 수 있는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a7d6-103">Provides methods that enable the host to start and stop the common language runtime (CLR) explicitly, to create and configure application domains, to access the default domain, and to enumerate all domains running in the process.</span></span>  
  
 <span data-ttu-id="5a7d6-104">.NET Framework 버전 2.0에서이 인터페이스는 [ICLRRuntimeHost](iclrruntimehost-interface.md)에 의해 대체 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5a7d6-104">In the .NET Framework version 2.0, this interface is superceded by [ICLRRuntimeHost](iclrruntimehost-interface.md).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5a7d6-105">메서드</span><span class="sxs-lookup"><span data-stu-id="5a7d6-105">Methods</span></span>  
  
|<span data-ttu-id="5a7d6-106">메서드</span><span class="sxs-lookup"><span data-stu-id="5a7d6-106">Method</span></span>|<span data-ttu-id="5a7d6-107">Description</span><span class="sxs-lookup"><span data-stu-id="5a7d6-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5a7d6-108">CloseEnum 메서드</span><span class="sxs-lookup"><span data-stu-id="5a7d6-108">CloseEnum Method</span></span>](icorruntimehost-closeenum-method.md)|<span data-ttu-id="5a7d6-109">도메인 열거자를 도메인 목록의 시작 부분으로 다시 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a7d6-109">Resets a domain enumerator back to the beginning of the domain list.</span></span>|  
|[<span data-ttu-id="5a7d6-110">CreateDomain 메서드</span><span class="sxs-lookup"><span data-stu-id="5a7d6-110">CreateDomain Method</span></span>](icorruntimehost-createdomain-method.md)|<span data-ttu-id="5a7d6-111">응용 프로그램 도메인을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="5a7d6-111">Creates an application domain.</span></span> <span data-ttu-id="5a7d6-112">호출자는 형식의 인스턴스에 대 한 인터페이스 포인터 <xref:System._AppDomain> 를 받습니다 <xref:System.AppDomain?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="5a7d6-112">The caller receives an interface pointer of type <xref:System._AppDomain> to an instance of type <xref:System.AppDomain?displayProperty=nameWithType>.</span></span>|  
|[<span data-ttu-id="5a7d6-113">CreateDomainEx 메서드</span><span class="sxs-lookup"><span data-stu-id="5a7d6-113">CreateDomainEx Method</span></span>](icorruntimehost-createdomainex-method.md)|<span data-ttu-id="5a7d6-114">응용 프로그램 도메인을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="5a7d6-114">Creates an application domain.</span></span> <span data-ttu-id="5a7d6-115">이 메서드를 사용 하면 호출자가 IAppDomainSetup 인스턴스를 전달 하 여 반환 된 인스턴스의 추가 기능을 구성할 수 있습니다 <xref:System._AppDomain> .</span><span class="sxs-lookup"><span data-stu-id="5a7d6-115">This method allows the caller to pass an IAppDomainSetup instance to configure additional features of the returned <xref:System._AppDomain> instance.</span></span>|  
|[<span data-ttu-id="5a7d6-116">CreateDomainSetup 메서드</span><span class="sxs-lookup"><span data-stu-id="5a7d6-116">CreateDomainSetup Method</span></span>](icorruntimehost-createdomainsetup-method.md)|<span data-ttu-id="5a7d6-117">인스턴스에 대 한 형식의 인터페이스 포인터를 가져옵니다 `IAppDomainSetup` <xref:System.AppDomainSetup> .</span><span class="sxs-lookup"><span data-stu-id="5a7d6-117">Gets an interface pointer of type `IAppDomainSetup` to an <xref:System.AppDomainSetup> instance.</span></span> <span data-ttu-id="5a7d6-118">`IAppDomainSetup` 응용 프로그램 도메인을 만들기 전에 요소를 구성 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a7d6-118">`IAppDomainSetup` provides methods to configure aspects of an application domain before it is created.</span></span>|  
|[<span data-ttu-id="5a7d6-119">CreateEvidence 메서드</span><span class="sxs-lookup"><span data-stu-id="5a7d6-119">CreateEvidence Method</span></span>](icorruntimehost-createevidence-method.md)|<span data-ttu-id="5a7d6-120"><xref:System.Security.Principal.IIdentity>호스트가 [createdomain](icorruntimehost-createdomain-method.md) 또는 [createdomainex](icorruntimehost-createdomainex-method.md)에 전달할 보안 증명 정보를 만들 수 있도록 하는 형식의 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="5a7d6-120">Gets an interface pointer of type <xref:System.Security.Principal.IIdentity>, which allows the host to create security evidence to pass to [CreateDomain](icorruntimehost-createdomain-method.md) or [CreateDomainEx](icorruntimehost-createdomainex-method.md).</span></span>|  
|[<span data-ttu-id="5a7d6-121">CreateLogicalThreadState 메서드</span><span class="sxs-lookup"><span data-stu-id="5a7d6-121">CreateLogicalThreadState Method</span></span>](icorruntimehost-createlogicalthreadstate-method.md)|<span data-ttu-id="5a7d6-122">사용하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="5a7d6-122">Do not use.</span></span>|  
|[<span data-ttu-id="5a7d6-123">CurrentDomain 메서드</span><span class="sxs-lookup"><span data-stu-id="5a7d6-123">CurrentDomain Method</span></span>](icorruntimehost-currentdomain-method.md)|<span data-ttu-id="5a7d6-124"><xref:System._AppDomain>현재 스레드에 로드 된 도메인을 나타내는 형식의 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="5a7d6-124">Gets an interface pointer of type <xref:System._AppDomain> that represents the domain loaded on the current thread.</span></span>|  
|[<span data-ttu-id="5a7d6-125">DeleteLogicalThreadState 메서드</span><span class="sxs-lookup"><span data-stu-id="5a7d6-125">DeleteLogicalThreadState Method</span></span>](icorruntimehost-deletelogicalthreadstate-method.md)|<span data-ttu-id="5a7d6-126">사용하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="5a7d6-126">Do not use.</span></span>|  
|[<span data-ttu-id="5a7d6-127">EnumDomains 메서드</span><span class="sxs-lookup"><span data-stu-id="5a7d6-127">EnumDomains Method</span></span>](icorruntimehost-enumdomains-method.md)|<span data-ttu-id="5a7d6-128">현재 프로세스의 도메인에 대 한 열거자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="5a7d6-128">Gets an enumerator for the domains in the current process.</span></span>|  
|[<span data-ttu-id="5a7d6-129">GetConfiguration 메서드</span><span class="sxs-lookup"><span data-stu-id="5a7d6-129">GetConfiguration Method</span></span>](icorruntimehost-getconfiguration-method.md)|<span data-ttu-id="5a7d6-130">호스트가 CLR의 콜백 구성을 지정할 수 있도록 하는 개체를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="5a7d6-130">Gets an object that allows the host to specify the callback configuration of the CLR.</span></span>|  
|[<span data-ttu-id="5a7d6-131">GetDefaultDomain 메서드</span><span class="sxs-lookup"><span data-stu-id="5a7d6-131">GetDefaultDomain Method</span></span>](icorruntimehost-getdefaultdomain-method.md)|<span data-ttu-id="5a7d6-132"><xref:System._AppDomain>현재 프로세스에 대 한 기본 도메인을 나타내는 형식의 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="5a7d6-132">Gets an interface pointer of type <xref:System._AppDomain> that represents the default domain for the current process.</span></span>|  
|[<span data-ttu-id="5a7d6-133">LocksHeldByLogicalThread 메서드</span><span class="sxs-lookup"><span data-stu-id="5a7d6-133">LocksHeldByLogicalThread Method</span></span>](icorruntimehost-locksheldbylogicalthread-method.md)|<span data-ttu-id="5a7d6-134">사용하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="5a7d6-134">Do not use.</span></span>|  
|[<span data-ttu-id="5a7d6-135">MapFile 메서드</span><span class="sxs-lookup"><span data-stu-id="5a7d6-135">MapFile Method</span></span>](icorruntimehost-mapfile-method.md)|<span data-ttu-id="5a7d6-136">지정 된 파일을 메모리에 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="5a7d6-136">Maps the specified file into memory.</span></span> <span data-ttu-id="5a7d6-137">이 메서드는 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5a7d6-137">This method is obsolete.</span></span>|  
|[<span data-ttu-id="5a7d6-138">NextDomain 메서드</span><span class="sxs-lookup"><span data-stu-id="5a7d6-138">NextDomain Method</span></span>](icorruntimehost-nextdomain-method.md)|<span data-ttu-id="5a7d6-139">열거형의 다음 도메인에 대 한 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="5a7d6-139">Gets an interface pointer to the next domain in the enumeration.</span></span>|  
|[<span data-ttu-id="5a7d6-140">Start 메서드</span><span class="sxs-lookup"><span data-stu-id="5a7d6-140">Start Method</span></span>](icorruntimehost-start-method.md)|<span data-ttu-id="5a7d6-141">CLR을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a7d6-141">Starts the CLR.</span></span>|  
|[<span data-ttu-id="5a7d6-142">Stop 메서드</span><span class="sxs-lookup"><span data-stu-id="5a7d6-142">Stop Method</span></span>](icorruntimehost-stop-method.md)|<span data-ttu-id="5a7d6-143">런타임에 현재 프로세스에 대 한 코드의 실행을 중지 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a7d6-143">Stops the execution of code in the runtime for the current process.</span></span>|  
|[<span data-ttu-id="5a7d6-144">SwitchInLogicalThreadState 메서드</span><span class="sxs-lookup"><span data-stu-id="5a7d6-144">SwitchInLogicalThreadState Method</span></span>](icorruntimehost-switchinlogicalthreadstate-method.md)|<span data-ttu-id="5a7d6-145">사용하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="5a7d6-145">Do not use.</span></span>|  
|[<span data-ttu-id="5a7d6-146">SwitchOutLogicalThreadState 메서드</span><span class="sxs-lookup"><span data-stu-id="5a7d6-146">SwitchOutLogicalThreadState Method</span></span>](icorruntimehost-switchoutlogicalthreadstate-method.md)|<span data-ttu-id="5a7d6-147">사용하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="5a7d6-147">Do not use.</span></span>|  
|[<span data-ttu-id="5a7d6-148">UnloadDomain 메서드</span><span class="sxs-lookup"><span data-stu-id="5a7d6-148">UnloadDomain Method</span></span>](icorruntimehost-unloaddomain-method.md)|<span data-ttu-id="5a7d6-149">현재 프로세스에서 지정 된 응용 프로그램 도메인을 언로드합니다.</span><span class="sxs-lookup"><span data-stu-id="5a7d6-149">Unloads the specified application domain from the current process.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5a7d6-150">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5a7d6-150">Requirements</span></span>  
 <span data-ttu-id="5a7d6-151">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5a7d6-151">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5a7d6-152">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="5a7d6-152">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5a7d6-153">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5a7d6-153">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5a7d6-154">**.NET Framework 버전:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="5a7d6-154">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a7d6-155">참조</span><span class="sxs-lookup"><span data-stu-id="5a7d6-155">See also</span></span>

- <xref:System.AppDomain>
- [<span data-ttu-id="5a7d6-156">호스팅</span><span class="sxs-lookup"><span data-stu-id="5a7d6-156">Hosting</span></span>](index.md)
- [<span data-ttu-id="5a7d6-157">ICLRRuntimeHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5a7d6-157">ICLRRuntimeHost Interface</span></span>](iclrruntimehost-interface.md)
- <span data-ttu-id="5a7d6-158">[런타임 호스트](/previous-versions/dotnet/netframework-4.0/a51xd4ze(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="5a7d6-158">[Runtime Hosts](/previous-versions/dotnet/netframework-4.0/a51xd4ze(v=vs.100))</span></span>
- [<span data-ttu-id="5a7d6-159">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5a7d6-159">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="5a7d6-160">CorRuntimeHost Coclass</span><span class="sxs-lookup"><span data-stu-id="5a7d6-160">CorRuntimeHost Coclass</span></span>](corruntimehost-coclass.md)
