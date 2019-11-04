---
title: .NET Framework 클래스 라이브러리의 사용되지 않는 기능
ms.custom: updateeachrelease
ms.date: 04/02/2019
helpviewer_keywords:
- obsolete [.NET Framework]
- what's obsolete [.NET Framework]
- deprecated [.NET Framework]
ms.assetid: d356a43a-73df-4ae2-a457-b9628074c7cd
ms.openlocfilehash: 4de441ff55c3728f43742d6e467deeb47f400507
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140591"
---
# <a name="whats-obsolete-in-the-net-framework-class-library"></a><span data-ttu-id="a349c-102">.NET Framework 클래스 라이브러리의 사용되지 않는 기능</span><span class="sxs-lookup"><span data-stu-id="a349c-102">What's obsolete in the .NET Framework class library</span></span>

<span data-ttu-id="a349c-103">.NET Framework는 시간이 지남에 따라 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="a349c-103">The .NET Framework changes over time.</span></span> <span data-ttu-id="a349c-104">새 버전이 나올 때마다 새로운 기능을 제공하는 새로운 형식 및 형식 멤버가 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="a349c-104">Each new version adds new types and type members that provide new functionality.</span></span> <span data-ttu-id="a349c-105">기존 형식과 해당 멤버도 시간이 지남에 따라 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="a349c-105">Existing types and their members also change over time.</span></span> <span data-ttu-id="a349c-106">예를 들어 일부 형식은 지원하는 기술이 새로운 기술로 대체됨에 따라 덜 중요해지고 일부 메서드는 보다 편리하거나 보다 완전한 기능을 갖춘 최신 메서드로 대체됩니다.</span><span class="sxs-lookup"><span data-stu-id="a349c-106">For example, some types become less important as the technology they support is replaced by a new technology, and some methods are superseded by newer methods that are either more convenient or more full-featured.</span></span>

<span data-ttu-id="a349c-107">.NET Framework 및 공용 언어 런타임은 이전 버전과의 호환성(특정 .NET Framework 버전으로 개발된 애플리케이션이 다음 버전의 .NET Framework에서 실행될 수 있도록 함)을 지원하기 위해 노력합니다.</span><span class="sxs-lookup"><span data-stu-id="a349c-107">The .NET Framework and the common language runtime strive to support backward compatibility (allowing applications that were developed with one version of the .NET Framework to run on the next version of the .NET Framework).</span></span> <span data-ttu-id="a349c-108">이 때문에 형식 또는 형식 멤버를 단순히 제거하기 어렵습니다.</span><span class="sxs-lookup"><span data-stu-id="a349c-108">This makes it difficult to simply remove a type or a type member.</span></span> <span data-ttu-id="a349c-109">대신, .NET Framework는 사용되지 않음(obsolete) 또는 더 이상 사용되지 않음(deprecated)으로 표시하여 형식 또는 형식 멤버가 더 이상 사용되지 않음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a349c-109">Instead, the .NET Framework indicates that a type or a type member should no longer be used by marking it as obsolete or deprecated.</span></span> <span data-ttu-id="a349c-110">사용 중단의 일부로 형식 또는 멤버를 사용되지 않음으로 표시하면 개발자가 사용이 중단됨을 인식하고 제거에 대응할 시간을 가질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a349c-110">Deprecating a type or a member involves marking it so that developers are aware it will go away and have time to respond to its removal.</span></span> <span data-ttu-id="a349c-111">그러나 형식 또는 멤버를 사용하는 기존 코드는 새 버전의 .NET Framework에서 계속 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="a349c-111">However, existing code that uses the type or member continues to run in the new version of the .NET Framework.</span></span>

> [!NOTE]
> <span data-ttu-id="a349c-112">*사용되지 않음(obsolete)* 및 *사용되지 않음(deprecated)* 용어는 .NET Framework의 형식 및 멤버에 적용될 경우 동일한 의미를 가집니다.</span><span class="sxs-lookup"><span data-stu-id="a349c-112">The terms *obsolete* and *deprecated* have the same meaning when applied to the types and members of the .NET Framework.</span></span>

## <a name="the-obsoleteattribute-attribute"></a><span data-ttu-id="a349c-113">ObsoleteAttribute 특성</span><span class="sxs-lookup"><span data-stu-id="a349c-113">The ObsoleteAttribute attribute</span></span>

<span data-ttu-id="a349c-114">.NET Framework는 <xref:System.ObsoleteAttribute> 특성으로 표시하여 형식 또는 형식 멤버가 사용되지 않음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a349c-114">The .NET Framework indicates that a type or type member is obsolete by marking it with the <xref:System.ObsoleteAttribute> attribute.</span></span> <span data-ttu-id="a349c-115">형식 또는 멤버에 이 특성을 적용하면 .NET Framework의 이후 버전에서 형식 또는 멤버가 해당 멤버를 사용하는 컴파일된 코드의 손상 없이 제거됨을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a349c-115">Applying the attribute to a type or member indicates that type or member will be removed in some future version of the .NET Framework without breaking compiled code that uses that member.</span></span>

<span data-ttu-id="a349c-116">형식 또는 형식 멤버가 사용되지 않음을 나타낼 뿐 아니라 <xref:System.ObsoleteAttribute>는 컴파일러에서 해당 형식 또는 멤버를 포함하는 소스 코드를 처리하는 방법을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="a349c-116">In addition to indicating that a type or a type member is obsolete, <xref:System.ObsoleteAttribute> defines how the compiler handles source code that includes that type or member.</span></span> <span data-ttu-id="a349c-117">컴파일러는 코드를 컴파일하지만 경고 메시지를 표시하거나, 형식 또는 멤버 사용을 오류로 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a349c-117">The compiler can compile the code but emit a warning message, or it can treat the use of the type or member as an error.</span></span> <span data-ttu-id="a349c-118">첫 번째 경우에는 코드가 성공적으로 컴파일되지만 형식 또는 멤버가 사용되지 않는다는 경고 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="a349c-118">In the first case, the code can successfully compile, but a warning message indicates that the type or member is obsolete.</span></span> <span data-ttu-id="a349c-119">두 번째 경우에는 컴파일이 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="a349c-119">In the second case, compilation fails.</span></span>

<span data-ttu-id="a349c-120">컴파일 시 경고 메시지 대신 오류가 생성되는 경우에도 <xref:System.ObsoleteAttribute>는 런타임 동작에 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a349c-120">Even if compilation produces an error instead of a warning message, <xref:System.ObsoleteAttribute> does not affect run-time behavior.</span></span> <span data-ttu-id="a349c-121">즉, 형식 또는 멤버를 사용하며 성공적으로 컴파일된 애플리케이션은 항상 성공적으로 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="a349c-121">That is, applications that use the type or member and that have compiled successfully will always run successfully.</span></span> <span data-ttu-id="a349c-122">형식 또는 멤버를 사용하는 애플리케이션을 다시 컴파일하려는 시도만 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="a349c-122">Only the attempt to recompile an application that uses the type or member fails.</span></span>

## <a name="how-to-handle-obsolete-types-and-members"></a><span data-ttu-id="a349c-123">사용되지 않는 형식 및 멤버를 처리하는 방법</span><span class="sxs-lookup"><span data-stu-id="a349c-123">How to handle obsolete types and members</span></span>

<span data-ttu-id="a349c-124">기존 코드를 업그레이드하고 다시 컴파일할 때 애플리케이션에서 컴파일러 경고를 생성하는 사용되지 않는 형식 또는 멤버를 사용하는 것은 완벽하게 허용됩니다.</span><span class="sxs-lookup"><span data-stu-id="a349c-124">When you upgrade and recompile existing code, using an obsolete type or member that produces a compiler warning in your application is perfectly acceptable.</span></span> <span data-ttu-id="a349c-125">그러나 컴파일러 경고 메시지를 검토하여 애플리케이션 코드를 변경해야 하는지 여부를 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a349c-125">However, you should review the compiler warning message to determine whether you should change your application code.</span></span> <span data-ttu-id="a349c-126">메시지에서 적절한 대안을 가리키지 않는 경우 다음 중 하나를 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a349c-126">If the message does not point to a suitable alternative, you should do either of the following:</span></span>

- <span data-ttu-id="a349c-127">가능한 경우 형식 또는 멤버 사용을 제거하여 코드를 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="a349c-127">Change your code by removing the use of the type or member, if possible.</span></span>

     <span data-ttu-id="a349c-128">또는</span><span class="sxs-lookup"><span data-stu-id="a349c-128">-or-</span></span>

- <span data-ttu-id="a349c-129">이 기술 영역에 대한 설명서를 검토하여 사용 중단에 대응하는 방법을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="a349c-129">Review the documentation for this technology area to determine how to respond to the deprecation.</span></span>

<span data-ttu-id="a349c-130">이후 버전의 .NET Framework에 대해 기존 코드를 다시 컴파일하지 않도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a349c-130">You may choose not to recompile existing code against a later version of the .NET Framework.</span></span> <span data-ttu-id="a349c-131">대신, 기존의 컴파일된 코드가 실행되는 .NET Framework 버전을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a349c-131">Instead, you can specify the version of the .NET Framework against which your existing compiled code runs.</span></span> <span data-ttu-id="a349c-132">예를 들어 .NET Framework 3.5에 대해 컴파일된 app1.exe라는 애플리케이션이 있지만 .NET Framework 4.5에 대해 애플리케이션을 실행하려 한다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="a349c-132">For example, suppose that you have an application named app1.exe that was compiled against the .NET Framework 3.5, but you want the application to run against the .NET Framework 4.5.</span></span> <span data-ttu-id="a349c-133">이 경우 다음 단계를 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a349c-133">This requires the following steps:</span></span>

1. <span data-ttu-id="a349c-134">주 실행 파일에 대한 구성 파일을 만들고 이름을 *appName*.exe.config로 지정합니다. 여기서 *appName*은 애플리케이션 실행 파일의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="a349c-134">Create a configuration file for your main executable and name it *appName*.exe.config, where *appName* is the name of the application executable.</span></span> <span data-ttu-id="a349c-135">예제에서는 app1.exe라는 애플리케이션에 대해 app1.exe.config라는 구성 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a349c-135">For the application named app1.exe in our example, you would create a configuration file named app1.exe.config.</span></span>

2. <span data-ttu-id="a349c-136">구성 파일에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a349c-136">Add the following to the configuration file.</span></span>

    ```xml
    <configuration>
       <startup> 
          <supportedRuntime version="v4.0" />
       </startup>
    </configuration>
    ```

<span data-ttu-id="a349c-137">다음 표에서는 특정 버전의 .NET Framework를 대상으로 지정하기 위해 `version` 특성에 할당할 수 있는 문자열 값을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a349c-137">The following table lists the string values that you can assign to the `version` attribute to target a specific version of the .NET Framework:</span></span>

|<span data-ttu-id="a349c-138">.NET Framework 버전</span><span class="sxs-lookup"><span data-stu-id="a349c-138">.NET Framework version</span></span>|<span data-ttu-id="a349c-139">`version` 문자열</span><span class="sxs-lookup"><span data-stu-id="a349c-139">`version` string</span></span>|
|-|-|
|<span data-ttu-id="a349c-140">4.8</span><span class="sxs-lookup"><span data-stu-id="a349c-140">4.8</span></span>|<span data-ttu-id="a349c-141">v4.0</span><span class="sxs-lookup"><span data-stu-id="a349c-141">v4.0</span></span>|
|<span data-ttu-id="a349c-142">4.7(4.7.1 및 4.7.2 포함)</span><span class="sxs-lookup"><span data-stu-id="a349c-142">4.7 (including 4.7.1 and 4.7.2)</span></span>|<span data-ttu-id="a349c-143">v4.0</span><span class="sxs-lookup"><span data-stu-id="a349c-143">v4.0</span></span>|
|<span data-ttu-id="a349c-144">4.6(4.6.1 및 4.6.2 포함)</span><span class="sxs-lookup"><span data-stu-id="a349c-144">4.6 (including 4.6.1 and 4.6.2)</span></span>|<span data-ttu-id="a349c-145">v4.0</span><span class="sxs-lookup"><span data-stu-id="a349c-145">v4.0</span></span>|
|<span data-ttu-id="a349c-146">4.5(4.5.1 및 4.5.2 포함)</span><span class="sxs-lookup"><span data-stu-id="a349c-146">4.5 (including 4.5.1 and 4.5.2)</span></span>|<span data-ttu-id="a349c-147">v4.0</span><span class="sxs-lookup"><span data-stu-id="a349c-147">v4.0</span></span>|
|<span data-ttu-id="a349c-148">4</span><span class="sxs-lookup"><span data-stu-id="a349c-148">4</span></span>|<span data-ttu-id="a349c-149">v4.0</span><span class="sxs-lookup"><span data-stu-id="a349c-149">v4.0</span></span>|
|<span data-ttu-id="a349c-150">3.5</span><span class="sxs-lookup"><span data-stu-id="a349c-150">3.5</span></span>|<span data-ttu-id="a349c-151">v2.0.50727</span><span class="sxs-lookup"><span data-stu-id="a349c-151">v2.0.50727</span></span>|
|<span data-ttu-id="a349c-152">2.0</span><span class="sxs-lookup"><span data-stu-id="a349c-152">2.0</span></span>|<span data-ttu-id="a349c-153">v2.0.50727</span><span class="sxs-lookup"><span data-stu-id="a349c-153">v2.0.50727</span></span>|
|<span data-ttu-id="a349c-154">1.1</span><span class="sxs-lookup"><span data-stu-id="a349c-154">1.1</span></span>|<span data-ttu-id="a349c-155">v1.1.4322</span><span class="sxs-lookup"><span data-stu-id="a349c-155">v1.1.4322</span></span>|
|<span data-ttu-id="a349c-156">1.0</span><span class="sxs-lookup"><span data-stu-id="a349c-156">1.0</span></span>|<span data-ttu-id="a349c-157">v1.0.3705</span><span class="sxs-lookup"><span data-stu-id="a349c-157">v1.0.3705</span></span>|

## <a name="obsolete-lists-for-the-net-framework-45-and-later-versions"></a><span data-ttu-id="a349c-158">.NET Framework 4.5 이상 버전에서 사용되지 않는 항목 목록</span><span class="sxs-lookup"><span data-stu-id="a349c-158">Obsolete lists for the .NET Framework 4.5 and later versions</span></span>

- [<span data-ttu-id="a349c-159">사용되지 않는 형식</span><span class="sxs-lookup"><span data-stu-id="a349c-159">Obsolete Types</span></span>](obsolete-types.md)
- [<span data-ttu-id="a349c-160">사용되지 않는 멤버</span><span class="sxs-lookup"><span data-stu-id="a349c-160">Obsolete Members</span></span>](obsolete-members.md)

## <a name="obsolete-lists-for-previous-versions"></a><span data-ttu-id="a349c-161">이전 버전에서 사용되지 않는 항목 목록</span><span class="sxs-lookup"><span data-stu-id="a349c-161">Obsolete lists for previous versions</span></span>

- <span data-ttu-id="a349c-162">[.NET Framework 4에서 사용되지 않는 형식](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ee461503(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="a349c-162">[Obsolete Types in the .NET Framework 4](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ee461503(v=vs.100))</span></span>

- <span data-ttu-id="a349c-163">[.NET Framework 4에서 사용되지 않는 멤버](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ee471421(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="a349c-163">[Obsolete Members in the .NET Framework 4](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ee471421(v=vs.100))</span></span>

- <span data-ttu-id="a349c-164">[.NET Framework 3.5에서 사용되지 않는 항목 목록](https://docs.microsoft.com/previous-versions/cc835481(v=msdn.10))</span><span class="sxs-lookup"><span data-stu-id="a349c-164">[.NET Framework 3.5 Obsolete List](https://docs.microsoft.com/previous-versions/cc835481(v=msdn.10))</span></span>

- <span data-ttu-id="a349c-165">[.NET Framework 2.0에서 사용되지 않는 항목 목록](https://docs.microsoft.com/previous-versions/aa497286(v=msdn.10))</span><span class="sxs-lookup"><span data-stu-id="a349c-165">[.NET Framework 2.0 Obsolete List](https://docs.microsoft.com/previous-versions/aa497286(v=msdn.10))</span></span>

## <a name="see-also"></a><span data-ttu-id="a349c-166">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a349c-166">See also</span></span>

- [<span data-ttu-id="a349c-167">\<supportedRuntime> 요소</span><span class="sxs-lookup"><span data-stu-id="a349c-167">\<supportedRuntime> Element</span></span>](../configure-apps/file-schema/startup/supportedruntime-element.md)
