---
title: .NET에 대한 안전한 코딩 지침
description: 와 함께 작업할 코드 디자인 . 악의적인 코드가 데이터에 액세스하거나 다른 작업을 수행하지 못하도록 하는 NET 적용 권한 및 기타 적용 권한입니다.
ms.date: 06/28/2018
helpviewer_keywords:
- managed wrapper to native code implementation
- secure coding
- reusable components
- library code that exposes protected resources
- code, security
- code security
- secure coding, options
- components [.NET], security
- code security, options
- security-neutral code
- security [.NET], coding guidelines
ms.assetid: 4f882d94-262b-4494-b0a6-ba9ba1f5f177
ms.openlocfilehash: 05f7e039ecdc0cd33baa015872924fb9e1f078aa
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187721"
---
# <a name="secure-coding-guidelines"></a><span data-ttu-id="e45b1-103">안전한 코딩 지침</span><span class="sxs-lookup"><span data-stu-id="e45b1-103">Secure coding guidelines</span></span>

<span data-ttu-id="e45b1-104">정보 기반 보안 및 코드 액세스 보안은 보안 구현을 위한 매우 강력하고 명시적인 메커니즘을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="e45b1-104">Evidence-based security and code access security provide very powerful, explicit mechanisms to implement security.</span></span> <span data-ttu-id="e45b1-105">대부분의 응용 프로그램 코드는 .NET에서 구현한 인프라를 간단히 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e45b1-105">Most application code can simply use the infrastructure implemented by .NET.</span></span> <span data-ttu-id="e45b1-106">경우에 따라, 보안 시스템을 확장하거나 새로운 임시 메서드를 사용하여 빌드되는 추가적인 애플리케이션 관련 보안이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="e45b1-106">In some cases, additional application-specific security is required, built either by extending the security system or by using new ad hoc methods.</span></span>

<span data-ttu-id="e45b1-107">코드에서 .NET 적용 권한 및 기타 적용 권한을 사용하면 악의적인 코드가 원하지 않는 정보에 액세스하거나 다른 바람직하지 않은 작업을 수행하지 못하도록 장벽을 세워야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e45b1-107">Using .NET enforced permissions and other enforcement in your code, you should erect barriers to prevent malicious code from accessing information that you don't want it to have or performing other undesirable actions.</span></span> <span data-ttu-id="e45b1-108">또한 신뢰할 수 있는 코드를 사용하여 예상되는 모든 시나리오에서 보안과 유용성 간의 균형을 맞춰야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e45b1-108">Additionally, you must strike a balance between security and usability in all the expected scenarios using trusted code.</span></span>

<span data-ttu-id="e45b1-109">이 개요에서는 보안 시스템에서 사용하기 위해 코드를 설계하는 여러 가지 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e45b1-109">This overview describes the different ways code can be designed to work with the security system.</span></span>

## <a name="securing-resource-access"></a><span data-ttu-id="e45b1-110">리소스 액세스 보안</span><span class="sxs-lookup"><span data-stu-id="e45b1-110">Securing resource access</span></span>

<span data-ttu-id="e45b1-111">코드를 설계하고 작성하는 경우, 특히 출처를 알 수 없는 코드를 사용하거나 호출하는 경우 코드에 부여된 리소스 액세스 권한을 보호하고 제한해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e45b1-111">When designing and writing your code, you need to protect and limit the access that code has to resources, especially when using or invoking code of unknown origin.</span></span> <span data-ttu-id="e45b1-112">따라서 코드의 보안을 유지하도록 다음과 같은 기술을 염두에 둡니다.</span><span class="sxs-lookup"><span data-stu-id="e45b1-112">So, keep in mind the following techniques to ensure your code is secure:</span></span>

- <span data-ttu-id="e45b1-113">CAS(코드 액세스 보안) 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="e45b1-113">Do not use Code Access Security (CAS).</span></span>

- <span data-ttu-id="e45b1-114">부분적으로 신뢰할 수 있는 코드 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="e45b1-114">Do not use partial trusted code.</span></span>

- <span data-ttu-id="e45b1-115">[허용부분적으로 신뢰할 수 있는 호출자](xref:System.Security.AllowPartiallyTrustedCallersAttribute) 특성(APTCA)을 사용하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="e45b1-115">Do not use the [AllowPartiallyTrustedCaller](xref:System.Security.AllowPartiallyTrustedCallersAttribute) attribute (APTCA).</span></span>

- <span data-ttu-id="e45b1-116">.NET Remoting 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="e45b1-116">Do not use .NET Remoting.</span></span>

- <span data-ttu-id="e45b1-117">DCOM(분산 구성 요소 개체 모델) 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="e45b1-117">Do not use Distributed Component Object Model (DCOM).</span></span>

- <span data-ttu-id="e45b1-118">이진 포맷터 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="e45b1-118">Do not use binary formatters.</span></span>

<span data-ttu-id="e45b1-119">코드 액세스 보안 및 보안 투명 코드는 부분적으로 신뢰할 수 있는 코드가 있는 보안 경계로 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e45b1-119">Code Access Security and Security-Transparent Code are not supported as a security boundary with partially trusted code.</span></span> <span data-ttu-id="e45b1-120">대체 보안 조치를 적용하지 않고 출처를 알 수 없는 코드를 로드 및 실행하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="e45b1-120">We advise against loading and executing code of unknown origins without putting alternative security measures in place.</span></span> <span data-ttu-id="e45b1-121">대체 보안 조치는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e45b1-121">The alternative security measures are:</span></span>

- <span data-ttu-id="e45b1-122">가상화</span><span class="sxs-lookup"><span data-stu-id="e45b1-122">Virtualization</span></span>

- <span data-ttu-id="e45b1-123">AppContainers</span><span class="sxs-lookup"><span data-stu-id="e45b1-123">AppContainers</span></span>

- <span data-ttu-id="e45b1-124">OS(운영 체제) 사용자 및 사용 권한</span><span class="sxs-lookup"><span data-stu-id="e45b1-124">Operating system (OS) users and permissions</span></span>

- <span data-ttu-id="e45b1-125">Hyper-V 컨테이너</span><span class="sxs-lookup"><span data-stu-id="e45b1-125">Hyper-V containers</span></span>

## <a name="security-neutral-code"></a><span data-ttu-id="e45b1-126">보안 중립 코드</span><span class="sxs-lookup"><span data-stu-id="e45b1-126">Security-neutral code</span></span>

<span data-ttu-id="e45b1-127">보안 중립 코드는 보안 시스템에서 명시적인 작업을 수행하는 것이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e45b1-127">Security-neutral code does nothing explicit with the security system.</span></span> <span data-ttu-id="e45b1-128">단순히 코드에 부여되는 권한을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="e45b1-128">It runs with whatever permissions it receives.</span></span> <span data-ttu-id="e45b1-129">보호된 작업(예: 파일, 네트워킹 사용 등)과 관련된 보안 예외를 catch하지 못하는 응용 프로그램은 처리되지 않은 예외가 발생할 수 있지만 보안 중립 코드는 .NET의 보안 기술을 계속 활용합니다. .</span><span class="sxs-lookup"><span data-stu-id="e45b1-129">Although applications that fail to catch security exceptions associated with protected operations (such as using files, networking, and so on) can result in an unhandled exception, security-neutral code still takes advantage of the security technologies in .NET.</span></span>

<span data-ttu-id="e45b1-130">보안 중립 라이브러리에는 사용자가 파악해야 하는 특징이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e45b1-130">A security-neutral library has special characteristics that you should understand.</span></span> <span data-ttu-id="e45b1-131">라이브러리에서 파일을 사용하거나 관리되지 않는 코드를 호출하는 API 요소를 제공한다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="e45b1-131">Suppose your library provides API elements that use files or call unmanaged code.</span></span> <span data-ttu-id="e45b1-132">코드에 해당 권한이 없는 경우 설명된 대로 실행되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e45b1-132">If your code doesn't have the corresponding permission, it won't run as described.</span></span> <span data-ttu-id="e45b1-133">하지만 코드에 권한이 있더라도 이 코드를 호출하는 모든 애플리케이션이 작동하려면 동일한 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e45b1-133">However, even if the code has the permission, any application code that calls it must have the same permission in order to work.</span></span> <span data-ttu-id="e45b1-134">호출 코드에 올바른 권한이 없는 경우 <xref:System.Security.SecurityException> 코드 액세스 보안 스택 워크의 결과로 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="e45b1-134">If the calling code doesn't have the right permission, a <xref:System.Security.SecurityException> appears as a result of the code access security stack walk.</span></span>

## <a name="application-code-that-isnt-a-reusable-component"></a><span data-ttu-id="e45b1-135">재사용 가능한 구성 요소가 아닌 응용 프로그램 코드</span><span class="sxs-lookup"><span data-stu-id="e45b1-135">Application code that isn't a reusable component</span></span>

<span data-ttu-id="e45b1-136">코드가 다른 코드에서 호출되지 않는 응용 프로그램의 일부인 경우 보안은 간단하며 특별한 코딩이 필요하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e45b1-136">If your code is part of an application that won't be called by other code, security is simple and special coding might not be required.</span></span> <span data-ttu-id="e45b1-137">하지만 악성 코드는 해당 코드를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e45b1-137">However, remember that malicious code can call your code.</span></span> <span data-ttu-id="e45b1-138">코드 액세스 보안으로 악성 코드가 리소스에 액세스하는 것을 방지할 수 있지만, 이러한 코드는 중요한 정보가 들어 있을 수 있는 필드 또는 속성의 값을 판독할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e45b1-138">While code access security might stop malicious code from accessing resources, such code could still read values of your fields or properties that might contain sensitive information.</span></span>

<span data-ttu-id="e45b1-139">또한 해당 코드가 인터넷 또는 기타 신뢰할 수 없는 소스로부터의 사용자 입력을 허용하는 경우에는 악의적인 입력에 주의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e45b1-139">Additionally, if your code accepts user input from the Internet or other unreliable sources, you must be careful about malicious input.</span></span>

## <a name="managed-wrapper-to-native-code-implementation"></a><span data-ttu-id="e45b1-140">네이티브 코드 구현에 대한 관리래퍼</span><span class="sxs-lookup"><span data-stu-id="e45b1-140">Managed wrapper to native code implementation</span></span>

<span data-ttu-id="e45b1-141">일반적으로 이 시나리오에서는 네이티브 코드에서 관리 코드에 사용 가능하게 하려는 몇 가지 유용한 기능을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="e45b1-141">Typically in this scenario, some useful functionality is implemented in native code that you want to make available to managed code.</span></span> <span data-ttu-id="e45b1-142">관리되는 래퍼는 플랫폼 호출 또는 COM interop를 사용하여 쉽게 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e45b1-142">Managed wrappers are easy to write using either platform invoke or COM interop.</span></span> <span data-ttu-id="e45b1-143">하지만 이 작업을 성공적으로 수행하려면 래퍼 호출자에게 비관리 코드 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e45b1-143">However, if you do this, callers of your wrappers must have unmanaged code rights in order to succeed.</span></span> <span data-ttu-id="e45b1-144">기본 정책에 따라 인트라넷이나 인터넷에서 다운로드한 코드가 래퍼와 함께 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e45b1-144">Under default policy, this means that code downloaded from an intranet or the Internet won't work with the wrappers.</span></span>

<span data-ttu-id="e45b1-145">이러한 래퍼를 사용하는 모든 응용 프로그램에 관리되지 않는 코드 권한을 부여하는 대신 래퍼 코드에만 이러한 권한을 부여하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="e45b1-145">Instead of giving unmanaged code rights to all applications that use these wrappers, it's better to give these rights only to the wrapper code.</span></span> <span data-ttu-id="e45b1-146">기본 기능이 리소스를 노출하지 않으며 구현도 안전할 경우에는, 래퍼는 모든 코드가 이를 통해 호출할 수 있도록 해당 권한을 어셜션하기만 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e45b1-146">If the underlying functionality exposes no resources and the implementation is likewise safe, the wrapper only needs to assert its rights, which enables any code to call through it.</span></span> <span data-ttu-id="e45b1-147">리소스가 포함되어 있으면, 보안 코딩은 다음 섹션에 설명된 라이브러리 코드의 경우와 동일해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e45b1-147">When resources are involved, security coding should be the same as the library code case described in the next section.</span></span> <span data-ttu-id="e45b1-148">래퍼는 호출자를 이러한 리소스에 노출할 가능성이 있기 때문에, 네이티브 코드가 안전한지 신중하게 확인해야 하며 이는 래퍼의 책임입니다.</span><span class="sxs-lookup"><span data-stu-id="e45b1-148">Because the wrapper is potentially exposing callers to these resources, careful verification of the safety of the native code is necessary and is the wrapper's responsibility.</span></span>

## <a name="library-code-that-exposes-protected-resources"></a><span data-ttu-id="e45b1-149">보호된 리소스를 노출하는 라이브러리 코드</span><span class="sxs-lookup"><span data-stu-id="e45b1-149">Library code that exposes protected resources</span></span>

<span data-ttu-id="e45b1-150">다음 방법은 보안 코딩에 대해 가장 강력하고 잠재적으로 위험할 수 있습니다. 사용 하는 리소스에 대 한 사용 권한이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e45b1-150">The following approach is the most powerful and hence potentially dangerous (if done incorrectly) for security coding: your library serves as an interface for other code to access certain resources that aren't otherwise available, just as the .NET classes enforce permissions for the resources they use.</span></span> <span data-ttu-id="e45b1-151">리소스를 노출할 경우, 먼저 코드는 리소스에 적절한 권한을 요구해야 합니다(즉, 보안 검사를 수행해야 함). 그런 다음 실제 작업을 수행할 수 있도록 해당 권한을 어설션합니다.</span><span class="sxs-lookup"><span data-stu-id="e45b1-151">Wherever you expose a resource, your code must first demand the permission appropriate to the resource (that is, it must perform a security check) and then typically assert its rights to perform the actual operation.</span></span>

## <a name="related-topics"></a><span data-ttu-id="e45b1-152">관련 항목</span><span class="sxs-lookup"><span data-stu-id="e45b1-152">Related topics</span></span>

|<span data-ttu-id="e45b1-153">제목</span><span class="sxs-lookup"><span data-stu-id="e45b1-153">Title</span></span>|<span data-ttu-id="e45b1-154">Description</span><span class="sxs-lookup"><span data-stu-id="e45b1-154">Description</span></span>|
|-----------|-----------------|
|[<span data-ttu-id="e45b1-155">상태 데이터 보안</span><span class="sxs-lookup"><span data-stu-id="e45b1-155">Securing State Data</span></span>](securing-state-data.md)|<span data-ttu-id="e45b1-156">전용 멤버를 보호하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e45b1-156">Describes how to protect private members.</span></span>|
|[<span data-ttu-id="e45b1-157">보안 및 사용자 입력</span><span class="sxs-lookup"><span data-stu-id="e45b1-157">Security and User Input</span></span>](security-and-user-input.md)|<span data-ttu-id="e45b1-158">사용자 입력을 허용하는 애플리케이션에 대한 보안 문제를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e45b1-158">Describes security concerns for applications that accept user input.</span></span>|
|[<span data-ttu-id="e45b1-159">보안 및 경합 상태</span><span class="sxs-lookup"><span data-stu-id="e45b1-159">Security and Race Conditions</span></span>](security-and-race-conditions.md)|<span data-ttu-id="e45b1-160">코드에서 경합 상태를 방지하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e45b1-160">Describes how to avoid race conditions in your code.</span></span>|
|[<span data-ttu-id="e45b1-161">보안 및 빠른 코드 생성</span><span class="sxs-lookup"><span data-stu-id="e45b1-161">Security and On-the-Fly Code Generation</span></span>](security-and-on-the-fly-code-generation.md)|<span data-ttu-id="e45b1-162">동적 코드를 생성하는 애플리케이션에 대한 보안 문제를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e45b1-162">Describes security concerns for applications that generate dynamic code.</span></span>|
|[<span data-ttu-id="e45b1-163">역할 기반 보안</span><span class="sxs-lookup"><span data-stu-id="e45b1-163">Role-Based Security</span></span>](role-based-security.md)|<span data-ttu-id="e45b1-164">.NET 역할 기반 보안을 자세히 설명하고 코드에서 사용할 수 있는 지침을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="e45b1-164">Describes .NET role-based security in detail and provides instructions for using it in your code.</span></span>|
