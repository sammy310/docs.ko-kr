---
title: '방법: 애플리케이션 도메인에 어셈블리 로드'
description: .NET에서 애플리케이션 도메인에 어셈블리를 로드하는 방법을 알아봅니다. 권장되는 방법은 System.Reflection.Assembly에서 정적(또는 공유) Load 메서드를 사용하는 것입니다.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- application domains, loading assemblies
- loading assemblies
ms.assetid: 1432aa2d-bd83-4346-bf3b-a1b7920e2aa9
ms.openlocfilehash: c91c70625b79002e9297755dfdfac8aa6e283208
ms.sourcegitcommit: 1c37a894c923bea021a3cc38ce7cba946357bbe1
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/19/2020
ms.locfileid: "85104753"
---
# <a name="how-to-load-assemblies-into-an-application-domain"></a><span data-ttu-id="86c8d-104">방법: 애플리케이션 도메인에 어셈블리 로드</span><span class="sxs-lookup"><span data-stu-id="86c8d-104">How to: Load Assemblies into an Application Domain</span></span>
<span data-ttu-id="86c8d-105">애플리케이션 도메인에 어셈블리를 로드하는 방법에는 여러 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86c8d-105">There are several ways to load an assembly into an application domain.</span></span> <span data-ttu-id="86c8d-106"><xref:System.Reflection.Assembly?displayProperty=nameWithType> 클래스의 `static`(Visual Basic에서는 `Shared`) <xref:System.Reflection.Assembly.Load%2A> 메서드를 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="86c8d-106">The recommended way is to use the `static` (`Shared` in Visual Basic) <xref:System.Reflection.Assembly.Load%2A> method of the <xref:System.Reflection.Assembly?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="86c8d-107">어셈블리를 로드할 수 있는 다른 방법은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="86c8d-107">Other ways assemblies can be loaded include:</span></span>  
  
- <span data-ttu-id="86c8d-108"><xref:System.Reflection.Assembly> 클래스의 <xref:System.Reflection.Assembly.LoadFrom%2A> 메서드는 파일 위치가 지정된 경우 어셈블리를 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="86c8d-108">The <xref:System.Reflection.Assembly.LoadFrom%2A> method of the <xref:System.Reflection.Assembly> class loads an assembly given its file location.</span></span> <span data-ttu-id="86c8d-109">이 메서드로 어셈블리를 로드하는 경우 다른 로드 컨텍스트가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="86c8d-109">Loading assemblies with this method uses a different load context.</span></span>  
  
- <span data-ttu-id="86c8d-110"><xref:System.Reflection.Assembly.ReflectionOnlyLoad%2A> 및 <xref:System.Reflection.Assembly.ReflectionOnlyLoadFrom%2A> 메서드는 리플렉션 전용 컨텍스트에 어셈블리를 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="86c8d-110">The <xref:System.Reflection.Assembly.ReflectionOnlyLoad%2A> and <xref:System.Reflection.Assembly.ReflectionOnlyLoadFrom%2A> methods load an assembly into the reflection-only context.</span></span> <span data-ttu-id="86c8d-111">이 컨텍스트에 로드된 어셈블리는 검사할 수만 있고 실행할 수 없으므로 다른 플랫폼을 대상으로 하는 어셈블리를 검사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86c8d-111">Assemblies loaded into this context can be examined but not executed, allowing the examination of assemblies that target other platforms.</span></span> <span data-ttu-id="86c8d-112">[방법: 리플렉션 전용 컨텍스트에 어셈블리 로드](../reflection-and-codedom/how-to-load-assemblies-into-the-reflection-only-context.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="86c8d-112">See [How to: Load Assemblies into the Reflection-Only Context](../reflection-and-codedom/how-to-load-assemblies-into-the-reflection-only-context.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="86c8d-113">리플렉션 전용 컨텍스트는 .NET Framework 버전 2.0의 새로운 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="86c8d-113">The reflection-only context is new in the .NET Framework version 2.0.</span></span>  
  
- <span data-ttu-id="86c8d-114"><xref:System.AppDomain> 클래스의 <xref:System.AppDomain.CreateInstance%2A> 및 <xref:System.AppDomain.CreateInstanceAndUnwrap%2A>과 같은 메서드는 애플리케이션 도메인에 어셈블리를 로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86c8d-114">Methods such as <xref:System.AppDomain.CreateInstance%2A> and <xref:System.AppDomain.CreateInstanceAndUnwrap%2A> of the <xref:System.AppDomain> class can load assemblies into an application domain.</span></span>  
  
- <span data-ttu-id="86c8d-115"><xref:System.Type> 클래스의 <xref:System.Type.GetType%2A> 메서드는 어셈블리를 로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86c8d-115">The <xref:System.Type.GetType%2A> method of the <xref:System.Type> class can load assemblies.</span></span>  
  
- <span data-ttu-id="86c8d-116"><xref:System.AppDomain?displayProperty=nameWithType> 클래스의 <xref:System.AppDomain.Load%2A> 메서드는 어셈블리를 로드할 수 있지만 COM 상호 운용성을 위해 주로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="86c8d-116">The <xref:System.AppDomain.Load%2A> method of the <xref:System.AppDomain?displayProperty=nameWithType> class can load assemblies, but is primarily used for COM interoperability.</span></span> <span data-ttu-id="86c8d-117">호출 시 사용된 애플리케이션 도메인 이외의 애플리케이션 도메인에 어셈블리를 로드하는 데 사용하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="86c8d-117">It should not be used to load assemblies into an application domain other than the application domain from which it is called.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="86c8d-118">.NET Framework 버전 2.0부터 런타임은 현재 로드된 런타임보다 높은 버전 번호를 가진 .NET Framework 버전으로 컴파일된 어셈블리를 로드하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="86c8d-118">Starting with the .NET Framework version 2.0, the runtime will not load an assembly that was compiled with a version of the .NET Framework that has a higher version number than the currently loaded runtime.</span></span> <span data-ttu-id="86c8d-119">이는 버전 번호의 주 버전 및 부 버전 구성 요소 조합에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="86c8d-119">This applies to the combination of the major and minor components of the version number.</span></span>  
  
 <span data-ttu-id="86c8d-120">로드된 어셈블리의 JIT(Just-In-Time) 컴파일된 코드가 애플리케이션 도메인 간에 공유되는 방식을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86c8d-120">You can specify the way the just-in-time (JIT) compiled code from loaded assemblies is shared between application domains.</span></span> <span data-ttu-id="86c8d-121">자세한 내용은 [애플리케이션 도메인 및 어셈블리](application-domains.md#application-domains-and-assemblies)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="86c8d-121">For more information, see [Application domains and assemblies](application-domains.md#application-domains-and-assemblies).</span></span>  
  
## <a name="example"></a><span data-ttu-id="86c8d-122">예제</span><span class="sxs-lookup"><span data-stu-id="86c8d-122">Example</span></span>  
 <span data-ttu-id="86c8d-123">다음 코드는 "example.exe" 또는 "example.dll"이라는 어셈블리를 로드 현재 애플리케이션 도메인에 로드하고, 어셈블리에서 `Example` 형식을 가져온 다음 해당 형식에 대한 매개 변수가 없는 `MethodA` 메서드를 가져와서 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="86c8d-123">The following code loads an assembly named "example.exe" or "example.dll" into the current application domain, gets a type named `Example` from the assembly, gets a parameterless method named `MethodA` for that type, and executes the method.</span></span> <span data-ttu-id="86c8d-124">로드된 어셈블리에서 정보를 가져오는 방법에 대한 자세한 내용은 [형식 동적 로드 및 사용](../reflection-and-codedom/dynamically-loading-and-using-types.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="86c8d-124">For a complete discussion on obtaining information from a loaded assembly, see [Dynamically Loading and Using Types](../reflection-and-codedom/dynamically-loading-and-using-types.md).</span></span>  
  
 [!code-cpp[System.AppDomain.Load#2](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.appdomain.load/cpp/source2.cpp#2)]
 [!code-csharp[System.AppDomain.Load#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.appdomain.load/cs/source2.cs#2)]
 [!code-vb[System.AppDomain.Load#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.appdomain.load/vb/source2.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="86c8d-125">참조</span><span class="sxs-lookup"><span data-stu-id="86c8d-125">See also</span></span>

- <xref:System.Reflection.Assembly.ReflectionOnlyLoad%2A>
- [<span data-ttu-id="86c8d-126">애플리케이션 도메인으로 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="86c8d-126">Programming with Application Domains</span></span>](application-domains.md#programming-with-application-domains)
- [<span data-ttu-id="86c8d-127">리플렉션</span><span class="sxs-lookup"><span data-stu-id="86c8d-127">Reflection</span></span>](../reflection-and-codedom/reflection.md)
- [<span data-ttu-id="86c8d-128">애플리케이션 도메인 사용</span><span class="sxs-lookup"><span data-stu-id="86c8d-128">Using Application Domains</span></span>](use.md)
- [<span data-ttu-id="86c8d-129">방법: 리플렉션 전용 컨텍스트에 어셈블리 로드</span><span class="sxs-lookup"><span data-stu-id="86c8d-129">How to: Load Assemblies into the Reflection-Only Context</span></span>](../reflection-and-codedom/how-to-load-assemblies-into-the-reflection-only-context.md)
- [<span data-ttu-id="86c8d-130">애플리케이션 도메인 및 어셈블리</span><span class="sxs-lookup"><span data-stu-id="86c8d-130">Application domains and assemblies</span></span>](application-domains.md#application-domains-and-assemblies)
