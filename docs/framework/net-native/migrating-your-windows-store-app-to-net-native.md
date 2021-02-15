---
description: '자세한 정보: Windows 스토어 앱을 .NET 네이티브로 마이그레이션'
title: Windows 스토어 앱을 .NET 네이티브로 마이그레이션
ms.date: 03/30/2017
ms.assetid: 4153aa18-6f56-4a0a-865b-d3da743a1d05
ms.openlocfilehash: 7a9e8f7108ca21dbbae7ca0097b15af078c8c6bb
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100464679"
---
# <a name="migrate-your-windows-store-app-to-net-native"></a><span data-ttu-id="6455b-103">.NET 네이티브로 Windows 스토어 앱 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="6455b-103">Migrate Your Windows Store App to .NET Native</span></span>

<span data-ttu-id="6455b-104">.NET 네이티브는 Windows 스토어 또는 개발자 컴퓨터에서 앱을 정적으로 컴파일하는 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="6455b-104">.NET Native provides static compilation of apps in the Windows Store or on the developer's computer.</span></span> <span data-ttu-id="6455b-105">이 기능은 디바이스의 [네이티브 이미지 생성기(Ngen.exe)](../tools/ngen-exe-native-image-generator.md) 또는 JIT(Just-In-Time) 컴파일러가 Windows 스토어 앱에 대해 수행하는 동적 컴파일과는 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="6455b-105">This differs from the dynamic compilation performed for Windows Store apps by the just-in-time (JIT) compiler or the [Native Image Generator (Ngen.exe)](../tools/ngen-exe-native-image-generator.md) on the device.</span></span> <span data-ttu-id="6455b-106">차이점에도 불구 하 고 .NET 네이티브는 [Windows 스토어 앱 용 .net과의](/previous-versions/windows/apps/br230302(v=vs.140))호환성을 유지 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="6455b-106">Despite the differences, .NET Native tries to maintain compatibility with the [.NET for Windows Store apps](/previous-versions/windows/apps/br230302(v=vs.140)).</span></span> <span data-ttu-id="6455b-107">대부분의 경우 Windows 스토어 앱 용 .NET에서 작동 하는 작업은 .NET 네이티브 에서도 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="6455b-107">For the most part, things that work on the .NET for Windows Store apps also work with .NET Native.</span></span>  <span data-ttu-id="6455b-108">그러나 동작이 변경되는 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6455b-108">However, in some cases, you may encounter behavioral changes.</span></span> <span data-ttu-id="6455b-109">이 문서에서는 다음과 같은 영역에서 Windows 스토어 앱 용 표준 .NET과 .NET 네이티브 간의 이러한 차이점에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="6455b-109">This document discusses these differences between the standard .NET for Windows Store apps and .NET Native in the following areas:</span></span>

- [<span data-ttu-id="6455b-110">일반 런타임 차이점</span><span class="sxs-lookup"><span data-stu-id="6455b-110">General runtime differences</span></span>](#Runtime)

- [<span data-ttu-id="6455b-111">동적 프로그래밍 차이점</span><span class="sxs-lookup"><span data-stu-id="6455b-111">Dynamic programming differences</span></span>](#Dynamic)

- [<span data-ttu-id="6455b-112">기타 리플렉션 관련 차이점</span><span class="sxs-lookup"><span data-stu-id="6455b-112">Other reflection-related differences</span></span>](#Reflection)

- [<span data-ttu-id="6455b-113">지원되지 않는 시나리오 및 API</span><span class="sxs-lookup"><span data-stu-id="6455b-113">Unsupported scenarios and APIs</span></span>](#Unsupported)

- [<span data-ttu-id="6455b-114">Visual Studio의 차이점</span><span class="sxs-lookup"><span data-stu-id="6455b-114">Visual Studio differences</span></span>](#VS)

<a name="Runtime"></a>

## <a name="general-runtime-differences"></a><span data-ttu-id="6455b-115">일반 런타임 차이점</span><span class="sxs-lookup"><span data-stu-id="6455b-115">General runtime differences</span></span>

- <span data-ttu-id="6455b-116"><xref:System.TypeLoadException>앱이 CLR (공용 언어 런타임)에서 실행 될 때 JIT 컴파일러에서 throw 되는와 같은 예외는 일반적으로 .NET 네이티브에서 처리 될 때 컴파일 시간 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="6455b-116">Exceptions, such as <xref:System.TypeLoadException>, that are thrown by the JIT compiler when an app runs on the common language runtime (CLR) generally result in compile-time errors when processed by .NET Native.</span></span>

- <span data-ttu-id="6455b-117">앱 UI 스레드에서 <xref:System.GC.WaitForPendingFinalizers%2A?displayProperty=nameWithType> 메서드를 호출해서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6455b-117">Don't call the <xref:System.GC.WaitForPendingFinalizers%2A?displayProperty=nameWithType> method from an app's UI thread.</span></span> <span data-ttu-id="6455b-118">이로 인해 .NET 네이티브에 교착 상태가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6455b-118">This can result in a deadlock on .NET Native.</span></span>

- <span data-ttu-id="6455b-119">정적 클래스 생성자 호출 순서를 따라서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6455b-119">Don't rely on static class constructor invocation ordering.</span></span> <span data-ttu-id="6455b-120">.NET 네이티브 호출 순서는 표준 런타임의 순서와 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="6455b-120">In .NET Native, the invocation order is different from the order on the standard runtime.</span></span> <span data-ttu-id="6455b-121">표준 런타임을 사용하는 경우에도 정적 클래스 생성자 실행 순서를 따라서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6455b-121">(Even with the standard runtime, you shouldn't rely on the order of execution of static class constructors.)</span></span>

- <span data-ttu-id="6455b-122">스레드에서 호출을 하지 않고 무한 루프(예: `while(true);`)를 사용하면 앱이 중지될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6455b-122">Infinite looping without making a call (for example, `while(true);`) on any thread may bring the app to a halt.</span></span> <span data-ttu-id="6455b-123">마찬가지로 대기 시간이 길어지거나 무한히 계속되어도 앱이 중지될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6455b-123">Similarly, large or infinite waits may bring the app to a halt.</span></span>

- <span data-ttu-id="6455b-124">특정 제네릭 초기화 주기는 .NET 네이티브에서 예외를 throw 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6455b-124">Certain generic initialization cycles don't throw exceptions in .NET Native.</span></span> <span data-ttu-id="6455b-125">예를 들어 다음 코드는 표준 CLR에서는 <xref:System.TypeLoadException> 예외를 throw하지만</span><span class="sxs-lookup"><span data-stu-id="6455b-125">For example, the following code throws a <xref:System.TypeLoadException> exception on the standard CLR.</span></span> <span data-ttu-id="6455b-126">.NET 네이티브는 그렇지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6455b-126">In .NET Native, it doesn't.</span></span>

  [!code-csharp[ProjectN#8](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn/cs/compat1.cs#8)]

- <span data-ttu-id="6455b-127">경우에 따라 .NET 네이티브는 .NET Framework 클래스 라이브러리의 다른 구현을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="6455b-127">In some cases, .NET Native provides different implementations of .NET Framework class libraries.</span></span> <span data-ttu-id="6455b-128">메서드에서 반환된 개체는 항상 반환된 형식의 멤버를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="6455b-128">An object returned from a method will always implement the members of the returned type.</span></span> <span data-ttu-id="6455b-129">그러나 지원 구현이 다르므로 기타 .NET Framework 플랫폼에서와 같이 해당 개체를 동일한 형식 집합으로 캐스팅하지 못할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6455b-129">However, since its backing implementation is different, you may not be able to cast it to the same set of types as you could on other .NET Framework platforms.</span></span> <span data-ttu-id="6455b-130">예를 들어 <xref:System.Collections.Generic.IEnumerable%601> , <xref:System.Reflection.TypeInfo.DeclaredMembers%2A?displayProperty=nameWithType> 등의 메서드가 반환한 <xref:System.Reflection.TypeInfo.DeclaredProperties%2A?displayProperty=nameWithType> 인터페이스 개체는 `T[]`로 캐스팅할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6455b-130">For example, in some cases, you may not be able to cast the <xref:System.Collections.Generic.IEnumerable%601> interface object returned by methods such as <xref:System.Reflection.TypeInfo.DeclaredMembers%2A?displayProperty=nameWithType> or <xref:System.Reflection.TypeInfo.DeclaredProperties%2A?displayProperty=nameWithType> to `T[]`.</span></span>

- <span data-ttu-id="6455b-131">WinInet 캐시는 Windows 스토어 앱 용 .NET에서는 기본적으로 사용 하도록 설정 되어 있지 않지만 .NET 네이티브에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6455b-131">The WinInet cache isn't enabled by default on .NET for Windows Store apps, but it is on .NET Native.</span></span> <span data-ttu-id="6455b-132">이로 인해 성능은 향상되지만 작업 집합이 영향을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="6455b-132">This improves performance but has working set implications.</span></span> <span data-ttu-id="6455b-133">개발자가 작업을 수행할 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6455b-133">No developer action is necessary.</span></span>

<a name="Dynamic"></a>

## <a name="dynamic-programming-differences"></a><span data-ttu-id="6455b-134">동적 프로그래밍 차이점</span><span class="sxs-lookup"><span data-stu-id="6455b-134">Dynamic programming differences</span></span>

<span data-ttu-id="6455b-135">.NET Framework 코드의 정적 링크를 .NET 네이티브 하 여 최대 성능을 위해 코드를 로컬 코드로 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6455b-135">.NET Native statically links in code from the .NET Framework to make the code app-local for maximum performance.</span></span> <span data-ttu-id="6455b-136">그러나 이진 크기를 작게 유지해야 하므로 전체 .NET Framework의 코드를 가져올 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6455b-136">However, binary sizes have to remain small, so the entire .NET Framework can't be brought in.</span></span> <span data-ttu-id="6455b-137">.NET 네이티브 컴파일러는 사용 되지 않는 코드에 대 한 참조를 제거 하는 종속성 리 듀 서을 사용 하 여이 제한을 해결 합니다.</span><span class="sxs-lookup"><span data-stu-id="6455b-137">The .NET Native compiler resolves this limitation by using a dependency reducer that removes references to unused code.</span></span> <span data-ttu-id="6455b-138">그러나 컴파일 타임에 정적으로 정보를 유추할 수 없지만 런타임에 동적으로 검색 하는 경우에는 .NET 네이티브에서 일부 형식 정보와 코드를 유지 관리 하거나 생성할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6455b-138">However, .NET Native might not maintain or generate some type information and code when that information can't be inferred statically at compile time, but instead is retrieved dynamically at runtime.</span></span>

<span data-ttu-id="6455b-139">.NET 네이티브은 리플렉션 및 동적 프로그래밍을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6455b-139">.NET Native does enable reflection and dynamic programming.</span></span> <span data-ttu-id="6455b-140">그러나 이로 인해 생성되는 코드 크기가 너무 커지며 특히 .NET Framework에서는 공용 API에 대한 리플렉션이 지원되지 않기 때문에 일부 형식만 리플렉션하도록 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6455b-140">However, not all types can be marked for reflection, because this would make the generated code size too large (especially because reflecting on public APIs in the .NET Framework is supported).</span></span> <span data-ttu-id="6455b-141">.NET 네이티브 컴파일러는 리플렉션을 지원 해야 하는 형식을 현명 하 게 선택 하 고 메타 데이터를 유지 하 고 해당 형식에 대 한 코드만 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="6455b-141">The .NET Native compiler makes smart choices about which types should support reflection, and it keeps the metadata and generates code only for those types.</span></span>

<span data-ttu-id="6455b-142">예를 들어 데이터 바인딩을 사용하려면 앱이 속성 이름을 함수에 매핑할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6455b-142">For example, data binding requires an app to be able to map property names to functions.</span></span> <span data-ttu-id="6455b-143">Windows 스토어 앱용 .NET에서는 공용 언어 런타임이 리플렉션을 자동으로 사용하여 관리되는 형식 및 공개적으로 사용 가능한 네이티브 형식에 대해 이 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="6455b-143">In .NET for Windows Store apps, the common language runtime automatically uses reflection to provide this capability for managed types and publicly available native types.</span></span> <span data-ttu-id="6455b-144">.NET 네이티브에서 컴파일러는 데이터를 바인딩할 형식에 대 한 메타 데이터를 자동으로 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="6455b-144">In .NET Native, the compiler automatically includes metadata for types to which you bind data.</span></span>

<span data-ttu-id="6455b-145">.NET 네이티브 컴파일러는 <xref:System.Collections.Generic.List%601> <xref:System.Collections.Generic.Dictionary%602> 힌트 또는 지시문을 요구 하지 않고 작동 하는 및와 같은 일반적으로 사용 되는 제네릭 형식을 처리할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6455b-145">The .NET Native compiler can also handle commonly used generic types such as <xref:System.Collections.Generic.List%601> and <xref:System.Collections.Generic.Dictionary%602>, which work without requiring any hints or directives.</span></span> <span data-ttu-id="6455b-146">[동적](../../csharp/language-reference/builtin-types/reference-types.md#the-dynamic-type) 키워드도 일정한 제한 내에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="6455b-146">The [dynamic](../../csharp/language-reference/builtin-types/reference-types.md#the-dynamic-type) keyword is also supported within certain limits.</span></span>

> [!NOTE]
> <span data-ttu-id="6455b-147">앱을 .NET 네이티브로 이식할 때 모든 동적 코드 경로를 철저 하 게 테스트 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6455b-147">You should test all dynamic code paths thoroughly when porting your app to .NET Native.</span></span>

<span data-ttu-id="6455b-148">.NET 네이티브에 대 한 기본 구성은 대부분의 개발자에 게 충분 하지만, 일부 개발자는 .rd.xml (런타임 지시문) 파일을 사용 하 여 해당 구성을 미세 조정 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="6455b-148">The default configuration for .NET Native is sufficient for most developers, but some developers might want to fine- tune their configurations by using a runtime directives (.rd.xml) file.</span></span> <span data-ttu-id="6455b-149">또한 경우에 따라 .NET 네이티브 컴파일러는 리플렉션에 사용할 수 있어야 하는 메타 데이터를 확인할 수 없으며, 특히 다음과 같은 경우에 힌트를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6455b-149">In addition, in some cases, the .NET Native compiler is unable to determine which metadata must be available for reflection and relies on hints, particularly in the following cases:</span></span>

- <span data-ttu-id="6455b-150"><xref:System.Type.MakeGenericType%2A?displayProperty=nameWithType> , <xref:System.Reflection.MethodInfo.MakeGenericMethod%2A?displayProperty=nameWithType> 등의 일부 구문은 정적으로 확인할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6455b-150">Some constructs like <xref:System.Type.MakeGenericType%2A?displayProperty=nameWithType> and <xref:System.Reflection.MethodInfo.MakeGenericMethod%2A?displayProperty=nameWithType> can't be determined statically.</span></span>

- <span data-ttu-id="6455b-151">컴파일러는 인스턴스화를 확인할 수 없으므로 런타임 지시문을 사용하여 리플렉션을 수행하려는 제네릭 형식을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6455b-151">Because the compiler can't determine the instantiations, a generic type that you want to reflect on has to be specified by runtime directives.</span></span> <span data-ttu-id="6455b-152">이는 단순히 모든 코드를 포함해야 하기 때문이 아니라, 제네릭 형식에 대해 리플렉션을 수행하면 무한 주기가 생성될 수 있기 때문입니다(예: 제네릭 형식에 대해 제네릭 메서드를 호출하는 경우).</span><span class="sxs-lookup"><span data-stu-id="6455b-152">This isn't just because all code must be included, but because reflection on generic types can form an infinite cycle (for example, when a generic method is invoked on a generic type).</span></span>

> [!NOTE]
> <span data-ttu-id="6455b-153">런타임 지시문은 런타임 지시문(.rd.xml) 파일에서 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="6455b-153">Runtime directives are defined in a runtime directives (.rd.xml) file.</span></span> <span data-ttu-id="6455b-154">이 파일의 사용 방법에 대한 일반 정보는 [시작](getting-started-with-net-native.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6455b-154">For general information about using this file, see [Getting Started](getting-started-with-net-native.md).</span></span> <span data-ttu-id="6455b-155">런타임 지시문에 대한 자세한 내용은 [Runtime Directives (rd.xml) Configuration File Reference](runtime-directives-rd-xml-configuration-file-reference.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6455b-155">For information about the runtime directives, see [Runtime Directives (rd.xml) Configuration File Reference](runtime-directives-rd-xml-configuration-file-reference.md).</span></span>

<span data-ttu-id="6455b-156">또한 .NET 네이티브에는 개발자가 기본 집합 외부에서 리플렉션을 지원 해야 하는 형식을 결정 하는 데 도움이 되는 프로 파일링 도구도 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6455b-156">.NET Native also includes profiling tools that help the developer determine which types outside the default set should support reflection.</span></span>

<a name="Reflection"></a>

## <a name="other-reflection-related-differences"></a><span data-ttu-id="6455b-157">기타 리플렉션 관련 차이점</span><span class="sxs-lookup"><span data-stu-id="6455b-157">Other reflection-related differences</span></span>

<span data-ttu-id="6455b-158">Windows 스토어 앱 용 .NET과 .NET 네이티브 간의 동작에는 다양 한 개별 리플렉션 관련 차이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6455b-158">There are a number of other individual reflection-related differences in behavior between the .NET for Windows Store apps and .NET Native.</span></span>

<span data-ttu-id="6455b-159">.NET 네이티브:</span><span class="sxs-lookup"><span data-stu-id="6455b-159">In .NET Native:</span></span>

- <span data-ttu-id="6455b-160">.NET Framework 클래스 라이브러리의 형식 및 멤버에 대한 개인 리플렉션은 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6455b-160">Private reflection over types and members in the .NET Framework class library is not supported.</span></span> <span data-ttu-id="6455b-161">그러나 고유한 개인 형식과 멤버 및 타사 라이브러리의 형식과 멤버에 대해서는 리플렉션을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6455b-161">You can, however, reflect over your own private types and members, as well as types and members in third-party libraries.</span></span>

- <span data-ttu-id="6455b-162"><xref:System.Reflection.ParameterInfo.HasDefaultValue%2A?displayProperty=nameWithType> 속성은 반환 값을 나타내는 `false` 개체에 대해 <xref:System.Reflection.ParameterInfo> 를 올바르게 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="6455b-162">The <xref:System.Reflection.ParameterInfo.HasDefaultValue%2A?displayProperty=nameWithType> property correctly returns `false` for a <xref:System.Reflection.ParameterInfo> object that represents a return value.</span></span> <span data-ttu-id="6455b-163">그러나 Windows 스토어 앱용 .NET에서는 `true`가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="6455b-163">In the .NET for Windows Store apps, it returns `true`.</span></span> <span data-ttu-id="6455b-164">IL (중간 언어)은이를 직접 지원 하지 않으며 해석은 언어를 그대로 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="6455b-164">Intermediate language (IL) doesn't support this directly, and interpretation is left to the language.</span></span>

- <span data-ttu-id="6455b-165"><xref:System.RuntimeFieldHandle> 및 <xref:System.RuntimeMethodHandle> 구조체에서는 public 멤버를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6455b-165">Public members on the <xref:System.RuntimeFieldHandle> and <xref:System.RuntimeMethodHandle> structures aren't supported.</span></span> <span data-ttu-id="6455b-166">이러한 형식은 LINQ, 식 트리 및 정적 배열 초기화에서만 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="6455b-166">These types are supported only for LINQ, expression trees, and static array initialization.</span></span>

- <span data-ttu-id="6455b-167"><xref:System.Reflection.RuntimeReflectionExtensions.GetRuntimeProperties%2A?displayProperty=nameWithType> 및 <xref:System.Reflection.RuntimeReflectionExtensions.GetRuntimeEvents%2A?displayProperty=nameWithType> 의 기본 클래스는 숨겨진 멤버를 포함하므로 명시적으로 재정의하지 않아도 재정의될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6455b-167"><xref:System.Reflection.RuntimeReflectionExtensions.GetRuntimeProperties%2A?displayProperty=nameWithType> and <xref:System.Reflection.RuntimeReflectionExtensions.GetRuntimeEvents%2A?displayProperty=nameWithType> include hidden members in base classes and thus may be overridden without explicit overrides.</span></span> <span data-ttu-id="6455b-168">이는 다른 [RuntimeReflectionExtensions.GetRuntime\*](xref:System.Reflection.RuntimeReflectionExtensions) 메서드에서도 마찬가지입니다.</span><span class="sxs-lookup"><span data-stu-id="6455b-168">This is also true of other [RuntimeReflectionExtensions.GetRuntime\*](xref:System.Reflection.RuntimeReflectionExtensions) methods.</span></span>

- <span data-ttu-id="6455b-169"><xref:System.Type.MakeArrayType%2A?displayProperty=nameWithType><xref:System.Type.MakeByRefType%2A?displayProperty=nameWithType>특정 조합 (예: 개체의 배열)을 만들려고 하면 오류가 발생 하지 않습니다 `byref` .</span><span class="sxs-lookup"><span data-stu-id="6455b-169"><xref:System.Type.MakeArrayType%2A?displayProperty=nameWithType> and <xref:System.Type.MakeByRefType%2A?displayProperty=nameWithType> don't fail when you try to create certain combinations (for example, an array of `byref` objects).</span></span>

- <span data-ttu-id="6455b-170">리플렉션을 사용하여 포인터 매개 변수가 있는 멤버를 호출할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6455b-170">You can't use reflection to invoke members that have pointer parameters.</span></span>

- <span data-ttu-id="6455b-171">리플렉션을 사용하여 포인터 필드를 가져오거나 설정할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6455b-171">You can't use reflection to get or set a pointer field.</span></span>

- <span data-ttu-id="6455b-172">인수 개수가 잘못 되 고 인수 중 하나의 형식이 잘못 된 경우 .NET 네이티브 <xref:System.ArgumentException> 는 대신을 throw <xref:System.Reflection.TargetParameterCountException> 합니다.</span><span class="sxs-lookup"><span data-stu-id="6455b-172">When the argument count is wrong and the type of one of the arguments is incorrect, .NET Native throws an <xref:System.ArgumentException> instead of a <xref:System.Reflection.TargetParameterCountException>.</span></span>

- <span data-ttu-id="6455b-173">예외의 이진 serialization은 일반적으로 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6455b-173">Binary serialization of exceptions is generally not supported.</span></span> <span data-ttu-id="6455b-174">그러므로 serialize할 수 없는 개체를 <xref:System.Exception.Data%2A?displayProperty=nameWithType> 사전에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6455b-174">As a result, non-serializable objects can be added to the <xref:System.Exception.Data%2A?displayProperty=nameWithType> dictionary.</span></span>

<a name="Unsupported"></a>

## <a name="unsupported-scenarios-and-apis"></a><span data-ttu-id="6455b-175">지원되지 않는 시나리오 및 API</span><span class="sxs-lookup"><span data-stu-id="6455b-175">Unsupported scenarios and APIs</span></span>

<span data-ttu-id="6455b-176">다음 섹션에서는 일반 개발, interop 및 HTTPClient, WCF(Windows Communication Foundation) 등의 기술에 대해 지원되지 않는 시나리오와 API에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="6455b-176">The following sections list unsupported scenarios and APIs for general development, interop, and technologies such as HTTPClient and Windows Communication Foundation (WCF):</span></span>

- [<span data-ttu-id="6455b-177">일반 개발</span><span class="sxs-lookup"><span data-stu-id="6455b-177">General development</span></span>](#General)

- [<span data-ttu-id="6455b-178">HttpClient</span><span class="sxs-lookup"><span data-stu-id="6455b-178">HttpClient</span></span>](#HttpClient)

- [<span data-ttu-id="6455b-179">Interop</span><span class="sxs-lookup"><span data-stu-id="6455b-179">Interop</span></span>](#Interop)

- [<span data-ttu-id="6455b-180">지원되지 않는 API</span><span class="sxs-lookup"><span data-stu-id="6455b-180">Unsupported APIs</span></span>](#APIs)

<a name="General"></a>

### <a name="general-development-differences"></a><span data-ttu-id="6455b-181">일반 개발 관련 차이점</span><span class="sxs-lookup"><span data-stu-id="6455b-181">General development differences</span></span>

<span data-ttu-id="6455b-182">**값 형식**</span><span class="sxs-lookup"><span data-stu-id="6455b-182">**Value types**</span></span>

- <span data-ttu-id="6455b-183">값 형식에 대해 <xref:System.ValueType.Equals%2A?displayProperty=nameWithType> 및 <xref:System.ValueType.GetHashCode%2A?displayProperty=nameWithType> 메서드를 재정의하는 경우 기본 클래스 구현을 호출하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="6455b-183">If you override the <xref:System.ValueType.Equals%2A?displayProperty=nameWithType> and <xref:System.ValueType.GetHashCode%2A?displayProperty=nameWithType> methods for a value type, don't call the base class implementations.</span></span> <span data-ttu-id="6455b-184">Windows 스토어 앱용 .NET에서 이러한 메서드는 리플렉션을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6455b-184">In .NET for Windows Store apps, these methods rely on reflection.</span></span> <span data-ttu-id="6455b-185">컴파일 시간에 .NET 네이티브는 런타임 리플렉션을 사용 하지 않는 구현을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="6455b-185">At compile time, .NET Native generates an implementation that doesn't rely on runtime reflection.</span></span> <span data-ttu-id="6455b-186">즉, 이러한 두 메서드를 재정의 하지 않으면 .NET 네이티브 컴파일 시간에 구현을 생성 하기 때문에 예상 대로 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="6455b-186">This means that if you don't override these two methods, they will work as expected, because .NET Native generates the implementation at compile time.</span></span> <span data-ttu-id="6455b-187">그러나 이러한 메서드를 재정의하고 기본 클래스 구현을 호출하면 예외가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="6455b-187">However, overriding these methods but calling the base class implementation results in an exception.</span></span>

- <span data-ttu-id="6455b-188">1mb 보다 큰 값 형식은 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6455b-188">Value types larger than 1 megabyte aren't supported.</span></span>

- <span data-ttu-id="6455b-189">값 형식은 .NET 네이티브에서 매개 변수가 없는 생성자를 가질 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6455b-189">Value types can't have a parameterless constructor in .NET Native.</span></span> <span data-ttu-id="6455b-190">(C # 및 Visual Basic는 값 형식에 대해 매개 변수가 없는 생성자를 금지 합니다.</span><span class="sxs-lookup"><span data-stu-id="6455b-190">(C# and Visual Basic prohibit parameterless constructors on value types.</span></span> <span data-ttu-id="6455b-191">IL에서는 기본 생성자를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6455b-191">However, these can be created in IL.)</span></span>

<span data-ttu-id="6455b-192">**배열**</span><span class="sxs-lookup"><span data-stu-id="6455b-192">**Arrays**</span></span>

- <span data-ttu-id="6455b-193">하한이 0이 아닌 배열은 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6455b-193">Arrays with a lower bound other than zero aren't supported.</span></span> <span data-ttu-id="6455b-194">이러한 배열은 대개 <xref:System.Array.CreateInstance%28System.Type%2CSystem.Int32%5B%5D%2CSystem.Int32%5B%5D%29?displayProperty=nameWithType> 오버로드를 호출하여 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6455b-194">Typically, these arrays are created by calling the <xref:System.Array.CreateInstance%28System.Type%2CSystem.Int32%5B%5D%2CSystem.Int32%5B%5D%29?displayProperty=nameWithType> overload.</span></span>

- <span data-ttu-id="6455b-195">동적으로 다차원 배열을 만들 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6455b-195">Dynamic creation of multidimensional arrays isn't supported.</span></span> <span data-ttu-id="6455b-196">이러한 배열은 대개 <xref:System.Array.CreateInstance%2A?displayProperty=nameWithType> 매개 변수를 포함하는 `lengths` 메서드의 오버로드 또는 <xref:System.Type.MakeArrayType%28System.Int32%29?displayProperty=nameWithType> 메서드를 호출하여 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6455b-196">Such arrays are typically created by calling an overload of the <xref:System.Array.CreateInstance%2A?displayProperty=nameWithType> method that includes a `lengths` parameter, or by calling the <xref:System.Type.MakeArrayType%28System.Int32%29?displayProperty=nameWithType> method.</span></span>

- <span data-ttu-id="6455b-197">차원이 4개 이상(해당 <xref:System.Array.Rank%2A?displayProperty=nameWithType> 속성 값이 4 이상)인 다차원 배열은 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6455b-197">Multidimensional arrays that have four or more dimensions aren't supported; that is, their <xref:System.Array.Rank%2A?displayProperty=nameWithType> property value is four or greater.</span></span> <span data-ttu-id="6455b-198">이러한 경우에는 [가변 배열](../../csharp/programming-guide/arrays/jagged-arrays.md) (배열의 배열)을 대신 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6455b-198">Use [jagged arrays](../../csharp/programming-guide/arrays/jagged-arrays.md) (an array of arrays) instead.</span></span> <span data-ttu-id="6455b-199">예를 들어 `array[x,y,z]` 는 유효하지 않지만 `array[x][y][z]` 는 유효합니다.</span><span class="sxs-lookup"><span data-stu-id="6455b-199">For example, `array[x,y,z]` is invalid, but `array[x][y][z]` isn't.</span></span>

- <span data-ttu-id="6455b-200">다차원 배열에는 가변성(variance)이 지원되지 않으며, 가변성(variance)을 적용하는 경우 런타임에 <xref:System.InvalidCastException> 예외가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="6455b-200">Variance for multidimensional arrays isn't supported and causes an <xref:System.InvalidCastException> exception at run time.</span></span>

<span data-ttu-id="6455b-201">**제네릭**</span><span class="sxs-lookup"><span data-stu-id="6455b-201">**Generics**</span></span>

- <span data-ttu-id="6455b-202">무한 제네릭 형식을 확장하면 컴파일러 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="6455b-202">Infinite generic type expansion results in a compiler error.</span></span> <span data-ttu-id="6455b-203">예를 들어 다음 코드는 컴파일되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6455b-203">For example, this code fails to compile:</span></span>

  [!code-csharp[ProjectN#9](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn/cs/compat2.cs#9)]

<span data-ttu-id="6455b-204">**포인터**</span><span class="sxs-lookup"><span data-stu-id="6455b-204">**Pointers**</span></span>

- <span data-ttu-id="6455b-205">포인터 배열은 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6455b-205">Arrays of pointers aren't supported.</span></span>

- <span data-ttu-id="6455b-206">리플렉션을 사용하여 포인터 필드를 가져오거나 설정할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6455b-206">You can't use reflection to get or set a pointer field.</span></span>

<span data-ttu-id="6455b-207">**serialization**</span><span class="sxs-lookup"><span data-stu-id="6455b-207">**Serialization**</span></span>

<span data-ttu-id="6455b-208"><xref:System.Runtime.Serialization.KnownTypeAttribute.%23ctor%28System.String%29> 특성은 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6455b-208">The <xref:System.Runtime.Serialization.KnownTypeAttribute.%23ctor%28System.String%29> attribute isn't supported.</span></span> <span data-ttu-id="6455b-209">대신 <xref:System.Runtime.Serialization.KnownTypeAttribute.%23ctor%28System.Type%29> 특성을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="6455b-209">Use the <xref:System.Runtime.Serialization.KnownTypeAttribute.%23ctor%28System.Type%29> attribute instead.</span></span>

<span data-ttu-id="6455b-210">**리소스**</span><span class="sxs-lookup"><span data-stu-id="6455b-210">**Resources**</span></span>

<span data-ttu-id="6455b-211"><xref:System.Diagnostics.Tracing.EventSource> 클래스에는 지역화된 리소스를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6455b-211">The use of localized resources with the <xref:System.Diagnostics.Tracing.EventSource> class isn't supported.</span></span> <span data-ttu-id="6455b-212"><xref:System.Diagnostics.Tracing.EventSourceAttribute.LocalizationResources%2A?displayProperty=nameWithType> 속성은 지역화된 리소스를 정의하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6455b-212">The <xref:System.Diagnostics.Tracing.EventSourceAttribute.LocalizationResources%2A?displayProperty=nameWithType> property doesn't define localized resources.</span></span>

<span data-ttu-id="6455b-213">**대리자**</span><span class="sxs-lookup"><span data-stu-id="6455b-213">**Delegates**</span></span>

<span data-ttu-id="6455b-214">`Delegate.BeginInvoke` 및 `Delegate.EndInvoke` 는 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6455b-214">`Delegate.BeginInvoke` and `Delegate.EndInvoke` aren't supported.</span></span>

<span data-ttu-id="6455b-215">**기타 API**</span><span class="sxs-lookup"><span data-stu-id="6455b-215">**Miscellaneous APIs**</span></span>

- <span data-ttu-id="6455b-216">[](xref:System.Type.GUID) <xref:System.PlatformNotSupportedException> <xref:System.Runtime.InteropServices.GuidAttribute> 특성이 형식에 적용 되지 않으면 TypeInfo 속성이 예외를 throw 합니다.</span><span class="sxs-lookup"><span data-stu-id="6455b-216">The [TypeInfo.GUID](xref:System.Type.GUID) property throws a <xref:System.PlatformNotSupportedException> exception if a <xref:System.Runtime.InteropServices.GuidAttribute> attribute isn't applied to the type.</span></span> <span data-ttu-id="6455b-217">GUID는 주로 COM 지원을 위해 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="6455b-217">The GUID is used primarily for COM support.</span></span>

- <span data-ttu-id="6455b-218"><xref:System.DateTime.Parse%2A?displayProperty=nameWithType>메서드는 .NET 네이티브에서 짧은 날짜를 포함 하는 문자열을 올바르게 구문 분석 합니다.</span><span class="sxs-lookup"><span data-stu-id="6455b-218">The <xref:System.DateTime.Parse%2A?displayProperty=nameWithType> method correctly parses strings that contain short dates in .NET Native.</span></span> <span data-ttu-id="6455b-219">그러나 날짜 및 시간 구문 분석의 특정 변경 내용과의 호환성은 유지 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6455b-219">However, it doesn't maintain compatibility with certain changes in date and time parsing.</span></span>

- <span data-ttu-id="6455b-220"><xref:System.Numerics.BigInteger.ToString%2A?displayProperty=nameWithType>`("E")`.NET 네이티브에서 올바르게 반올림 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6455b-220"><xref:System.Numerics.BigInteger.ToString%2A?displayProperty=nameWithType> `("E")` is correctly rounded in .NET Native.</span></span> <span data-ttu-id="6455b-221">일부 CLR 버전에서는 결과 문자열이 반올림되는 대신 잘립니다.</span><span class="sxs-lookup"><span data-stu-id="6455b-221">In some versions of the CLR, the result string is truncated instead of rounded.</span></span>

<a name="HttpClient"></a>

### <a name="httpclient-differences"></a><span data-ttu-id="6455b-222">HttpClient의 차이점</span><span class="sxs-lookup"><span data-stu-id="6455b-222">HttpClient differences</span></span>

<span data-ttu-id="6455b-223">.NET 네이티브에서 클래스는 <xref:System.Net.Http.HttpClientHandler> <xref:Windows.Web.Http.Filters.HttpBaseProtocolFilter> <xref:System.Net.WebRequest> <xref:System.Net.WebResponse> Windows 스토어 앱 용 표준 .net에서 사용 되는 및 클래스 대신 클래스를 통해 내부적으로 WinINet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="6455b-223">In .NET Native, the <xref:System.Net.Http.HttpClientHandler> class internally uses WinINet (through the <xref:Windows.Web.Http.Filters.HttpBaseProtocolFilter> class) instead of the <xref:System.Net.WebRequest> and <xref:System.Net.WebResponse> classes used in the standard .NET for Windows Store apps.</span></span>  <span data-ttu-id="6455b-224">WinINet은 <xref:System.Net.Http.HttpClientHandler> 클래스에서 지원하는 구성 옵션 중 일부만 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="6455b-224">WinINet doesn't support all the configuration options that the <xref:System.Net.Http.HttpClientHandler> class supports.</span></span>  <span data-ttu-id="6455b-225">결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="6455b-225">As a result:</span></span>

- <span data-ttu-id="6455b-226">의 일부 기능 속성은 <xref:System.Net.Http.HttpClientHandler> `false` .NET 네이티브에서 반환 하는 반면 `true` Windows 스토어 앱 용 표준 .net에서는를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="6455b-226">Some of the capability properties on <xref:System.Net.Http.HttpClientHandler> return `false` on .NET Native, whereas they return `true` in the standard .NET for Windows Store apps.</span></span>

- <span data-ttu-id="6455b-227">일부 구성 속성 접근자는 `get` Windows 스토어 앱 용 .net의 기본 구성 가능한 값과 다른 .NET 네이티브의 고정 값을 항상 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="6455b-227">Some of the configuration property `get` accessors always return a fixed value on .NET Native that is different than the default configurable value in .NET for Windows Store apps.</span></span>

<span data-ttu-id="6455b-228">다음 하위 섹션에서 몇 가지 추가적인 동작 차이점에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="6455b-228">Some additional behavior differences are covered in the following subsections.</span></span>

<span data-ttu-id="6455b-229">**프록시**</span><span class="sxs-lookup"><span data-stu-id="6455b-229">**Proxy**</span></span>

<span data-ttu-id="6455b-230"><xref:Windows.Web.Http.Filters.HttpBaseProtocolFilter>클래스는 요청 별로 프록시 구성 또는 재정의를 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6455b-230">The <xref:Windows.Web.Http.Filters.HttpBaseProtocolFilter> class doesn't support configuring or overriding the proxy on a per-request basis.</span></span>  <span data-ttu-id="6455b-231">즉, .NET 네이티브의 모든 요청은 속성의 값에 따라 시스템에서 구성 된 프록시 서버를 사용 하거나 프록시 서버를 사용 하지 않습니다 <xref:System.Net.Http.HttpClientHandler.UseProxy%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="6455b-231">This means that all requests on .NET Native use the system-configured proxy server or no proxy server, depending on the value of the <xref:System.Net.Http.HttpClientHandler.UseProxy%2A?displayProperty=nameWithType> property.</span></span>  <span data-ttu-id="6455b-232">Windows 스토어 앱용 .NET에서는 <xref:System.Net.Http.HttpClientHandler.Proxy%2A?displayProperty=nameWithType> 속성을 통해 프록시 서버가 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="6455b-232">In .NET for Windows Store apps, the proxy server is defined by the <xref:System.Net.Http.HttpClientHandler.Proxy%2A?displayProperty=nameWithType> property.</span></span>  <span data-ttu-id="6455b-233">.NET 네이티브에서를 이외의 <xref:System.Net.Http.HttpClientHandler.Proxy%2A?displayProperty=nameWithType> 값으로 설정 하면 `null` <xref:System.PlatformNotSupportedException> 예외가 throw 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6455b-233">On .NET Native, setting the <xref:System.Net.Http.HttpClientHandler.Proxy%2A?displayProperty=nameWithType> to a value other than `null` throws a <xref:System.PlatformNotSupportedException> exception.</span></span>  <span data-ttu-id="6455b-234"><xref:System.Net.Http.HttpClientHandler.SupportsProxy%2A?displayProperty=nameWithType>속성은 .NET 네이티브에 대해를 반환 하는 `false` 반면 `true` Windows 스토어 앱에 대 한 표준 .NET Framework을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="6455b-234">The <xref:System.Net.Http.HttpClientHandler.SupportsProxy%2A?displayProperty=nameWithType> property returns `false` on .NET Native, whereas it returns `true` in the standard .NET Framework for Windows Store apps.</span></span>

<span data-ttu-id="6455b-235">**자동 리디렉션**</span><span class="sxs-lookup"><span data-stu-id="6455b-235">**Automatic redirection**</span></span>

<span data-ttu-id="6455b-236"><xref:Windows.Web.Http.Filters.HttpBaseProtocolFilter>클래스는 최대 자동 리디렉션 수를 구성할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6455b-236">The <xref:Windows.Web.Http.Filters.HttpBaseProtocolFilter> class doesn't allow the maximum number of automatic redirections to be configured.</span></span>  <span data-ttu-id="6455b-237">Windows 스토어 앱용 표준 .NET에서는 <xref:System.Net.Http.HttpClientHandler.MaxAutomaticRedirections%2A?displayProperty=nameWithType> 속성의 기본값이 50이며, 이 값은 수정 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="6455b-237">The value of the <xref:System.Net.Http.HttpClientHandler.MaxAutomaticRedirections%2A?displayProperty=nameWithType> property is 50 by default in the standard .NET for Windows Store apps and can be modified.</span></span> <span data-ttu-id="6455b-238">.NET 네이티브에서이 속성의 값은 10이 고 수정 하려고 하면 예외가 throw 됩니다 <xref:System.PlatformNotSupportedException> .</span><span class="sxs-lookup"><span data-stu-id="6455b-238">On .NET Native, the value of this property is 10, and trying to modify it throws a <xref:System.PlatformNotSupportedException> exception.</span></span>  <span data-ttu-id="6455b-239"><xref:System.Net.Http.HttpClientHandler.SupportsRedirectConfiguration%2A?displayProperty=nameWithType>속성은 .NET 네이티브에 대해를 반환 하는 `false` 반면 `true` Windows 스토어 앱 용 .net에서는를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="6455b-239">The <xref:System.Net.Http.HttpClientHandler.SupportsRedirectConfiguration%2A?displayProperty=nameWithType> property returns `false` on .NET Native, whereas it returns `true` in .NET for Windows Store apps.</span></span>

<span data-ttu-id="6455b-240">**자동 압축 풀기**</span><span class="sxs-lookup"><span data-stu-id="6455b-240">**Automatic decompression**</span></span>

<span data-ttu-id="6455b-241">Windows 스토어 앱용 .NET에서는 <xref:System.Net.Http.HttpClientHandler.AutomaticDecompression%2A?displayProperty=nameWithType> 속성을 <xref:System.Net.DecompressionMethods.Deflate>또는 <xref:System.Net.DecompressionMethods.GZip>중 하나로 설정하거나, <xref:System.Net.DecompressionMethods.Deflate> 및 <xref:System.Net.DecompressionMethods.GZip>둘 다로 설정하거나, <xref:System.Net.DecompressionMethods.None>으로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6455b-241">.NET for Windows Store apps allows you to set the <xref:System.Net.Http.HttpClientHandler.AutomaticDecompression%2A?displayProperty=nameWithType> property to <xref:System.Net.DecompressionMethods.Deflate>, <xref:System.Net.DecompressionMethods.GZip>, both <xref:System.Net.DecompressionMethods.Deflate> and <xref:System.Net.DecompressionMethods.GZip>, or <xref:System.Net.DecompressionMethods.None>.</span></span>  <span data-ttu-id="6455b-242">.NET 네이티브 <xref:System.Net.DecompressionMethods.Deflate> <xref:System.Net.DecompressionMethods.GZip> 는, 또는와 함께 지원 <xref:System.Net.DecompressionMethods.None> 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6455b-242">.NET Native only supports <xref:System.Net.DecompressionMethods.Deflate> together with <xref:System.Net.DecompressionMethods.GZip>, or <xref:System.Net.DecompressionMethods.None>.</span></span>  <span data-ttu-id="6455b-243"><xref:System.Net.Http.HttpClientHandler.AutomaticDecompression%2A> 속성을 <xref:System.Net.DecompressionMethods.Deflate> 또는 <xref:System.Net.DecompressionMethods.GZip> 중 하나만으로 설정하면 <xref:System.Net.DecompressionMethods.Deflate> 및 <xref:System.Net.DecompressionMethods.GZip>둘 다로 자동 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="6455b-243">Trying to set the <xref:System.Net.Http.HttpClientHandler.AutomaticDecompression%2A> property to either <xref:System.Net.DecompressionMethods.Deflate> or <xref:System.Net.DecompressionMethods.GZip> alone silently sets it to both <xref:System.Net.DecompressionMethods.Deflate> and <xref:System.Net.DecompressionMethods.GZip>.</span></span>

<span data-ttu-id="6455b-244">**쿠키**</span><span class="sxs-lookup"><span data-stu-id="6455b-244">**Cookies**</span></span>

<span data-ttu-id="6455b-245">쿠키 처리는 <xref:System.Net.Http.HttpClient> 및 WinINet에서 동시에 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="6455b-245">Cookie handling is performed simultaneously by <xref:System.Net.Http.HttpClient> and WinINet.</span></span>  <span data-ttu-id="6455b-246"><xref:System.Net.CookieContainer> 의 쿠키는 WinINet 쿠키 캐시의 쿠키와 결합됩니다.</span><span class="sxs-lookup"><span data-stu-id="6455b-246">Cookies from the <xref:System.Net.CookieContainer> are combined with cookies in the WinINet cookie cache.</span></span>  <span data-ttu-id="6455b-247"><xref:System.Net.CookieContainer> 에서 쿠키를 제거하면 <xref:System.Net.Http.HttpClient> 가 쿠키를 보낼 수 없습니다. 그러나 WinINet에서 쿠키를 이미 확인했으며 사용자가 쿠키를 삭제하지 않은 경우에는 WinINet이 쿠키를 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="6455b-247">Removing a cookie from <xref:System.Net.CookieContainer> prevents <xref:System.Net.Http.HttpClient> from sending the cookie, but if the cookie was already seen by WinINet, and cookies weren't deleted by the user, WinINet sends it.</span></span>  <span data-ttu-id="6455b-248"><xref:System.Net.Http.HttpClient>, <xref:System.Net.Http.HttpClientHandler>또는 <xref:System.Net.CookieContainer> API를 사용하여 WinINet에서 프로그래밍 방식으로 쿠키를 제거할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6455b-248">It isn't possible to programmatically remove a cookie from WinINet by using the <xref:System.Net.Http.HttpClient>, <xref:System.Net.Http.HttpClientHandler>, or <xref:System.Net.CookieContainer> API.</span></span>  <span data-ttu-id="6455b-249"><xref:System.Net.Http.HttpClientHandler.UseCookies%2A?displayProperty=nameWithType> 속성을 `false` 로 설정하면 <xref:System.Net.Http.HttpClient> 만 쿠키 보내기를 중지하며 WinINet은 요청에 쿠키를 계속 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6455b-249">Setting the <xref:System.Net.Http.HttpClientHandler.UseCookies%2A?displayProperty=nameWithType> property to `false` causes only <xref:System.Net.Http.HttpClient> to stop sending cookies; WinINet might still include its cookies in the request.</span></span>

<span data-ttu-id="6455b-250">**자격 증명**</span><span class="sxs-lookup"><span data-stu-id="6455b-250">**Credentials**</span></span>

<span data-ttu-id="6455b-251">Windows 스토어 앱용 .NET에서는 <xref:System.Net.Http.HttpClientHandler.UseDefaultCredentials%2A?displayProperty=nameWithType> 및 <xref:System.Net.Http.HttpClientHandler.Credentials%2A?displayProperty=nameWithType> 속성이 독립적으로 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="6455b-251">In .NET for Windows Store apps, the <xref:System.Net.Http.HttpClientHandler.UseDefaultCredentials%2A?displayProperty=nameWithType> and <xref:System.Net.Http.HttpClientHandler.Credentials%2A?displayProperty=nameWithType> properties work independently.</span></span>  <span data-ttu-id="6455b-252">또한 <xref:System.Net.Http.HttpClientHandler.Credentials%2A> 속성은 <xref:System.Net.ICredentials> 인터페이스를 구현하는 모든 개체를 수락합니다.</span><span class="sxs-lookup"><span data-stu-id="6455b-252">Additionally, the <xref:System.Net.Http.HttpClientHandler.Credentials%2A> property accepts any object that implements the <xref:System.Net.ICredentials> interface.</span></span>  <span data-ttu-id="6455b-253">.NET 네이티브에서 속성을로 설정 하면 속성이로 설정 <xref:System.Net.Http.HttpClientHandler.UseDefaultCredentials%2A> `true` <xref:System.Net.Http.HttpClientHandler.Credentials%2A> `null` 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6455b-253">In .NET Native, setting the <xref:System.Net.Http.HttpClientHandler.UseDefaultCredentials%2A> property to `true` causes the <xref:System.Net.Http.HttpClientHandler.Credentials%2A> property to become `null`.</span></span>  <span data-ttu-id="6455b-254">또한 <xref:System.Net.Http.HttpClientHandler.Credentials%2A> 속성은 `null`, <xref:System.Net.CredentialCache.DefaultCredentials%2A>또는 <xref:System.Net.NetworkCredential>형식 개체로만 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6455b-254">In addition, the <xref:System.Net.Http.HttpClientHandler.Credentials%2A> property can be set only to `null`, <xref:System.Net.CredentialCache.DefaultCredentials%2A>, or an object of type <xref:System.Net.NetworkCredential>.</span></span>  <span data-ttu-id="6455b-255">다른 <xref:System.Net.ICredentials> 개체(가장 널리 사용되는 항목은 <xref:System.Net.CredentialCache>)를 <xref:System.Net.Http.HttpClientHandler.Credentials%2A> 속성에 할당하면 <xref:System.PlatformNotSupportedException>이 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="6455b-255">Assigning any other <xref:System.Net.ICredentials> object, the most popular of which is <xref:System.Net.CredentialCache>, to the <xref:System.Net.Http.HttpClientHandler.Credentials%2A> property throws a <xref:System.PlatformNotSupportedException>.</span></span>

<span data-ttu-id="6455b-256">**기타 지원되지 않거나 구성할 수 없는 기능**</span><span class="sxs-lookup"><span data-stu-id="6455b-256">**Other unsupported or unconfigurable features**</span></span>

<span data-ttu-id="6455b-257">.NET 네이티브:</span><span class="sxs-lookup"><span data-stu-id="6455b-257">In .NET Native:</span></span>

- <span data-ttu-id="6455b-258"><xref:System.Net.Http.HttpClientHandler.ClientCertificateOptions%2A?displayProperty=nameWithType> 속성의 값은 항상 <xref:System.Net.Http.ClientCertificateOption.Automatic>입니다.</span><span class="sxs-lookup"><span data-stu-id="6455b-258">The value of the <xref:System.Net.Http.HttpClientHandler.ClientCertificateOptions%2A?displayProperty=nameWithType> property is always <xref:System.Net.Http.ClientCertificateOption.Automatic>.</span></span>  <span data-ttu-id="6455b-259">Windows 스토어 앱용 .NET에서는 기본값이 <xref:System.Net.Http.ClientCertificateOption.Manual>입니다.</span><span class="sxs-lookup"><span data-stu-id="6455b-259">In .NET for Windows Store apps, the default is <xref:System.Net.Http.ClientCertificateOption.Manual>.</span></span>

- <span data-ttu-id="6455b-260"><xref:System.Net.Http.HttpClientHandler.MaxRequestContentBufferSize%2A?displayProperty=nameWithType> 속성은 구성할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6455b-260">The <xref:System.Net.Http.HttpClientHandler.MaxRequestContentBufferSize%2A?displayProperty=nameWithType> property isn't configurable.</span></span>

- <span data-ttu-id="6455b-261"><xref:System.Net.Http.HttpClientHandler.PreAuthenticate%2A?displayProperty=nameWithType> 속성은 항상 `true`입니다.</span><span class="sxs-lookup"><span data-stu-id="6455b-261">The <xref:System.Net.Http.HttpClientHandler.PreAuthenticate%2A?displayProperty=nameWithType> property is always `true`.</span></span>  <span data-ttu-id="6455b-262">Windows 스토어 앱용 .NET에서는 기본값이 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="6455b-262">In .NET for Windows Store apps, the default is `false`.</span></span>

- <span data-ttu-id="6455b-263">응답의 `SetCookie2` 헤더는 사용되지 않는 항목으로 간주되어 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6455b-263">The `SetCookie2` header in responses is ignored as obsolete.</span></span>

<a name="Interop"></a>

### <a name="interop-differences"></a><span data-ttu-id="6455b-264">interop 차이점</span><span class="sxs-lookup"><span data-stu-id="6455b-264">Interop differences</span></span>

 <span data-ttu-id="6455b-265">**사용되지 않는 API**</span><span class="sxs-lookup"><span data-stu-id="6455b-265">**Deprecated APIs**</span></span>

 <span data-ttu-id="6455b-266">관리되는 코드와의 상호 운용성을 위해 제공되었던 사용 빈도가 낮은 여러 API가 더 이상 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6455b-266">A number of infrequently used APIs for interoperability with managed code have been deprecated.</span></span> <span data-ttu-id="6455b-267">.NET 네이티브와 함께 사용 하는 경우 이러한 Api는 <xref:System.NotImplementedException> 또는 <xref:System.PlatformNotSupportedException> 예외를 throw 하거나 컴파일러 오류가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6455b-267">When used with .NET Native, these APIs may throw a <xref:System.NotImplementedException> or <xref:System.PlatformNotSupportedException> exception, or result in a compiler error.</span></span> <span data-ttu-id="6455b-268">Windows 스토어 앱용 .NET에서는 이러한 API가 사용되지 않는 것으로 표시되지만 호출해도 컴파일러 오류가 아닌 컴파일러 경고가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="6455b-268">In .NET for Windows Store apps, these APIs are marked as obsolete, although calling them generates a compiler warning rather than a compiler error.</span></span>

 <span data-ttu-id="6455b-269">마샬링에 사용 되지 않는 Api `VARIANT` 는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="6455b-269">Deprecated APIs for `VARIANT` marshaling include:</span></span>

- <xref:System.Runtime.InteropServices.BStrWrapper?displayProperty=nameWithType>
- <xref:System.Runtime.InteropServices.CurrencyWrapper?displayProperty=nameWithType>
- <xref:System.Runtime.InteropServices.DispatchWrapper?displayProperty=nameWithType>
- <xref:System.Runtime.InteropServices.ErrorWrapper?displayProperty=nameWithType>
- <xref:System.Runtime.InteropServices.UnknownWrapper?displayProperty=nameWithType>
- <xref:System.Runtime.InteropServices.VariantWrapper?displayProperty=nameWithType>
- <xref:System.Runtime.InteropServices.UnmanagedType.IDispatch?displayProperty=nameWithType>
- <xref:System.Runtime.InteropServices.UnmanagedType.SafeArray?displayProperty=nameWithType>
- <xref:System.Runtime.InteropServices.VarEnum?displayProperty=nameWithType>

 <span data-ttu-id="6455b-270"><xref:System.Runtime.InteropServices.UnmanagedType.Struct?displayProperty=nameWithType> 는 지원 되지만 [IDispatch](/previous-versions/windows/desktop/api/oaidl/nn-oaidl-idispatch) 또는 variant와 함께 사용 하는 경우와 같은 일부 시나리오에서는 예외를 throw `byref` 합니다.</span><span class="sxs-lookup"><span data-stu-id="6455b-270"><xref:System.Runtime.InteropServices.UnmanagedType.Struct?displayProperty=nameWithType> is supported, but it throws an exception in some scenarios, such as when it is used with [IDispatch](/previous-versions/windows/desktop/api/oaidl/nn-oaidl-idispatch) or `byref` variants.</span></span>

 <span data-ttu-id="6455b-271">[IDispatch](/previous-versions/windows/desktop/api/oaidl/nn-oaidl-idispatch) 지원에 대해 사용 되지 않는 api는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="6455b-271">Deprecated APIs for [IDispatch](/previous-versions/windows/desktop/api/oaidl/nn-oaidl-idispatch) support include:</span></span>

- <xref:System.Runtime.InteropServices.ClassInterfaceType.AutoDispatch?displayProperty=fullName>
- <xref:System.Runtime.InteropServices.ClassInterfaceType.AutoDual?displayProperty=fullName>
- <xref:System.Runtime.InteropServices.ComDefaultInterfaceAttribute?displayProperty=nameWithType>

<span data-ttu-id="6455b-272">기존 COM 이벤트에 대해 사용 되지 않는 Api는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="6455b-272">Deprecated APIs for classic COM events include:</span></span>

- <xref:System.Runtime.InteropServices.ComEventsHelper?displayProperty=nameWithType>
- <xref:System.Runtime.InteropServices.ComSourceInterfacesAttribute>

<span data-ttu-id="6455b-273">.NET 네이티브에서 지원 되지 않는 인터페이스에서 사용 되지 않는 Api는 <xref:System.Runtime.InteropServices.ICustomQueryInterface?displayProperty=nameWithType> 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="6455b-273">Deprecated APIs in the <xref:System.Runtime.InteropServices.ICustomQueryInterface?displayProperty=nameWithType> interface, which isn't supported in .NET Native, include:</span></span>

- <span data-ttu-id="6455b-274"><xref:System.Runtime.InteropServices.ICustomQueryInterface?displayProperty=nameWithType>(모든 멤버)</span><span class="sxs-lookup"><span data-stu-id="6455b-274"><xref:System.Runtime.InteropServices.ICustomQueryInterface?displayProperty=nameWithType> (all members)</span></span>
- <span data-ttu-id="6455b-275"><xref:System.Runtime.InteropServices.CustomQueryInterfaceMode?displayProperty=nameWithType>(모든 멤버)</span><span class="sxs-lookup"><span data-stu-id="6455b-275"><xref:System.Runtime.InteropServices.CustomQueryInterfaceMode?displayProperty=nameWithType> (all members)</span></span>
- <span data-ttu-id="6455b-276"><xref:System.Runtime.InteropServices.CustomQueryInterfaceResult?displayProperty=nameWithType>(모든 멤버)</span><span class="sxs-lookup"><span data-stu-id="6455b-276"><xref:System.Runtime.InteropServices.CustomQueryInterfaceResult?displayProperty=nameWithType> (all members)</span></span>
- <xref:System.Runtime.InteropServices.Marshal.GetComInterfaceForObject%28System.Object%2CSystem.Type%2CSystem.Runtime.InteropServices.CustomQueryInterfaceMode%29?displayProperty=fullName>

<span data-ttu-id="6455b-277">기타 지원 되지 않는 interop 기능은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="6455b-277">Other unsupported interop features include:</span></span>

- <span data-ttu-id="6455b-278"><xref:System.Runtime.InteropServices.ICustomAdapter?displayProperty=nameWithType>(모든 멤버)</span><span class="sxs-lookup"><span data-stu-id="6455b-278"><xref:System.Runtime.InteropServices.ICustomAdapter?displayProperty=nameWithType> (all members)</span></span>
- <span data-ttu-id="6455b-279"><xref:System.Runtime.InteropServices.SafeBuffer?displayProperty=nameWithType>(모든 멤버)</span><span class="sxs-lookup"><span data-stu-id="6455b-279"><xref:System.Runtime.InteropServices.SafeBuffer?displayProperty=nameWithType> (all members)</span></span>
- <xref:System.Runtime.InteropServices.UnmanagedType.Currency?displayProperty=fullName>
- <xref:System.Runtime.InteropServices.UnmanagedType.VBByRefStr?displayProperty=fullName>
- <xref:System.Runtime.InteropServices.UnmanagedType.AnsiBStr?displayProperty=fullName>
- <xref:System.Runtime.InteropServices.UnmanagedType.AsAny?displayProperty=fullName>
- <xref:System.Runtime.InteropServices.UnmanagedType.CustomMarshaler?displayProperty=fullName>

 <span data-ttu-id="6455b-280">거의 사용 되지 않는 마샬링 Api:</span><span class="sxs-lookup"><span data-stu-id="6455b-280">Rarely used marshaling APIs:</span></span>

- <xref:System.Runtime.InteropServices.Marshal.ReadByte%28System.Object%2CSystem.Int32%29?displayProperty=fullName>
- <xref:System.Runtime.InteropServices.Marshal.ReadInt16%28System.Object%2CSystem.Int32%29?displayProperty=fullName>
- <xref:System.Runtime.InteropServices.Marshal.ReadInt32%28System.Object%2CSystem.Int32%29?displayProperty=fullName>
- <xref:System.Runtime.InteropServices.Marshal.ReadInt64%28System.Object%2CSystem.Int32%29?displayProperty=fullName>
- <xref:System.Runtime.InteropServices.Marshal.ReadIntPtr%28System.Object%2CSystem.Int32%29?displayProperty=fullName>
- <xref:System.Runtime.InteropServices.Marshal.WriteByte%28System.Object%2CSystem.Int32%2CSystem.Byte%29?displayProperty=fullName>
- <xref:System.Runtime.InteropServices.Marshal.WriteInt16%28System.Object%2CSystem.Int32%2CSystem.Int16%29?displayProperty=fullName>
- <xref:System.Runtime.InteropServices.Marshal.WriteInt32%28System.Object%2CSystem.Int32%2CSystem.Int32%29?displayProperty=fullName>
- <xref:System.Runtime.InteropServices.Marshal.WriteInt64%28System.Object%2CSystem.Int32%2CSystem.Int64%29?displayProperty=fullName>
- <xref:System.Runtime.InteropServices.Marshal.WriteIntPtr%28System.Object%2CSystem.Int32%2CSystem.IntPtr%29?displayProperty=fullName>

 <span data-ttu-id="6455b-281">**플랫폼 호출 및 COM interop 호환성**</span><span class="sxs-lookup"><span data-stu-id="6455b-281">**Platform invoke and COM interop compatibility**</span></span>

 <span data-ttu-id="6455b-282">대부분의 플랫폼 호출 및 COM interop 시나리오는 .NET 네이티브에서 계속 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6455b-282">Most platform invoke and COM interop scenarios are still supported in .NET Native.</span></span> <span data-ttu-id="6455b-283">특히 WinRT(Windows 런타임) API와의 모든 상호 운용성 및 Windows 런타임에 필요한 모든 마샬링은 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="6455b-283">In particular, all interoperability with Windows Runtime (WinRT) APIs and all marshaling required for the Windows Runtime is supported.</span></span> <span data-ttu-id="6455b-284">여기에는 다음에 대한 마샬링 지원이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="6455b-284">This includes marshaling support for:</span></span>

- <span data-ttu-id="6455b-285">배열( <xref:System.Runtime.InteropServices.UnmanagedType.ByValArray?displayProperty=nameWithType>포함)</span><span class="sxs-lookup"><span data-stu-id="6455b-285">Arrays (including <xref:System.Runtime.InteropServices.UnmanagedType.ByValArray?displayProperty=nameWithType>)</span></span>

- `BStr`

- <span data-ttu-id="6455b-286">대리자</span><span class="sxs-lookup"><span data-stu-id="6455b-286">Delegates</span></span>

- <span data-ttu-id="6455b-287">문자열 (유니코드, ANSI 및 HSTRING)</span><span class="sxs-lookup"><span data-stu-id="6455b-287">Strings (Unicode, ANSI, and HSTRING)</span></span>

- <span data-ttu-id="6455b-288">구조체(`byref` 및 `byval`)</span><span class="sxs-lookup"><span data-stu-id="6455b-288">Structs (`byref` and `byval`)</span></span>

- <span data-ttu-id="6455b-289">Unions</span><span class="sxs-lookup"><span data-stu-id="6455b-289">Unions</span></span>

- <span data-ttu-id="6455b-290">Win32 핸들</span><span class="sxs-lookup"><span data-stu-id="6455b-290">Win32 handles</span></span>

- <span data-ttu-id="6455b-291">모든 WinRT 구문</span><span class="sxs-lookup"><span data-stu-id="6455b-291">All WinRT constructs</span></span>

- <span data-ttu-id="6455b-292">Variant 형식 마샬링에 대한 부분 지원.</span><span class="sxs-lookup"><span data-stu-id="6455b-292">Partial support for marshaling variant types.</span></span> <span data-ttu-id="6455b-293">다음 항목이 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="6455b-293">The following are supported:</span></span>

  - <xref:System.Boolean>

  - <xref:System.Byte>

  - <xref:System.Decimal>

  - <xref:System.Double>

  - <xref:System.Int16>

  - <xref:System.Int32>

  - <xref:System.Int64>

  - <xref:System.SByte>

  - <xref:System.Single>

  - <xref:System.UInt16>

  - <xref:System.UInt32>

  - <xref:System.UInt64>

  - `BStr`

  - [<span data-ttu-id="6455b-294">IUnknown</span><span class="sxs-lookup"><span data-stu-id="6455b-294">IUnknown</span></span>](/windows/desktop/api/unknwn/nn-unknwn-iunknown)

<span data-ttu-id="6455b-295">그러나 .NET 네이티브는 다음을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6455b-295">However, .NET Native doesn't support the following:</span></span>

- <span data-ttu-id="6455b-296">기본 COM 이벤트 사용</span><span class="sxs-lookup"><span data-stu-id="6455b-296">Using classic COM events</span></span>

- <span data-ttu-id="6455b-297">관리되는 형식에서 <xref:System.Runtime.InteropServices.ICustomQueryInterface?displayProperty=nameWithType> 인터페이스 구현</span><span class="sxs-lookup"><span data-stu-id="6455b-297">Implementing the <xref:System.Runtime.InteropServices.ICustomQueryInterface?displayProperty=nameWithType> interface on a managed type</span></span>

- <span data-ttu-id="6455b-298">[특성을 통해 관리되는 형식에서](/previous-versions/windows/desktop/api/oaidl/nn-oaidl-idispatch) IDispatch <xref:System.Runtime.InteropServices.ComDefaultInterfaceAttribute?displayProperty=nameWithType> 인터페이스 구현.</span><span class="sxs-lookup"><span data-stu-id="6455b-298">Implementing the [IDispatch](/previous-versions/windows/desktop/api/oaidl/nn-oaidl-idispatch) interface on a managed type through the <xref:System.Runtime.InteropServices.ComDefaultInterfaceAttribute?displayProperty=nameWithType> attribute.</span></span> <span data-ttu-id="6455b-299">그러나를 통해 COM 개체를 호출할 수 없으며 `IDispatch` 관리 되는 개체는를 구현할 수 없습니다 `IDispatch` .</span><span class="sxs-lookup"><span data-stu-id="6455b-299">However, you can't call COM objects through `IDispatch`, and your managed object can't implement `IDispatch`.</span></span>

<span data-ttu-id="6455b-300">리플렉션을 사용하여 플랫폼 호출 메서드를 호출할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6455b-300">Using reflection to invoke a platform invoke method isn't supported.</span></span> <span data-ttu-id="6455b-301">대신 다른 메서드에서 메서드 호출을 래핑하고 리플렉션을 사용해 래퍼를 호출하여 이 제한을 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6455b-301">You can work around this limitation by wrapping the method call in another method and using reflection to call the wrapper instead.</span></span>

<a name="APIs"></a>

### <a name="other-differences-from-net-apis-for-windows-store-apps"></a><span data-ttu-id="6455b-302">Windows 스토어 앱용 .NET API의 기타 차이점</span><span class="sxs-lookup"><span data-stu-id="6455b-302">Other differences from .NET APIs for Windows Store apps</span></span>

<span data-ttu-id="6455b-303">이 섹션에서는 .NET 네이티브에서 지원 되지 않는 나머지 Api를 나열 합니다.</span><span class="sxs-lookup"><span data-stu-id="6455b-303">This section lists the remaining APIs that aren't supported in .NET Native.</span></span> <span data-ttu-id="6455b-304">지원 되지 않는 Api의 가장 큰 집합은 WCF (Windows Communication Foundation) Api입니다.</span><span class="sxs-lookup"><span data-stu-id="6455b-304">The largest set of the unsupported APIs is the Windows Communication Foundation (WCF) APIs.</span></span>

<span data-ttu-id="6455b-305">**DataAnnotations(System.ComponentModel.DataAnnotations)**</span><span class="sxs-lookup"><span data-stu-id="6455b-305">**DataAnnotations (System.ComponentModel.DataAnnotations)**</span></span>

<span data-ttu-id="6455b-306"><xref:System.ComponentModel.DataAnnotations>및 네임 스페이스의 형식은 <xref:System.ComponentModel.DataAnnotations.Schema> .NET 네이티브에서 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6455b-306">The types in the <xref:System.ComponentModel.DataAnnotations> and <xref:System.ComponentModel.DataAnnotations.Schema> namespaces aren't supported in .NET Native.</span></span> <span data-ttu-id="6455b-307">여기에는 windows 8 용 Windows 스토어 앱 용 .NET에서 제공 되는 다음과 같은 형식이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6455b-307">These include the following types that are present in .NET for Windows Store apps for Windows 8:</span></span>

- <xref:System.ComponentModel.DataAnnotations.AssociationAttribute?displayProperty=nameWithType>
- <xref:System.ComponentModel.DataAnnotations.ConcurrencyCheckAttribute?displayProperty=nameWithType>
- <xref:System.ComponentModel.DataAnnotations.CustomValidationAttribute?displayProperty=nameWithType>
- <xref:System.ComponentModel.DataAnnotations.DataType?displayProperty=nameWithType>
- <xref:System.ComponentModel.DataAnnotations.DataTypeAttribute?displayProperty=nameWithType>
- <xref:System.ComponentModel.DataAnnotations.DisplayAttribute?displayProperty=nameWithType>
- <xref:System.ComponentModel.DataAnnotations.DisplayColumnAttribute?displayProperty=nameWithType>
- <xref:System.ComponentModel.DataAnnotations.DisplayFormatAttribute>
- <xref:System.ComponentModel.DataAnnotations.EditableAttribute>
- <xref:System.ComponentModel.DataAnnotations.EnumDataTypeAttribute>
- <xref:System.ComponentModel.DataAnnotations.FilterUIHintAttribute?displayProperty=nameWithType>
- <xref:System.ComponentModel.DataAnnotations.KeyAttribute?displayProperty=nameWithType>
- <xref:System.ComponentModel.DataAnnotations.RangeAttribute?displayProperty=nameWithType>
- <xref:System.ComponentModel.DataAnnotations.RegularExpressionAttribute?displayProperty=nameWithType>
- <xref:System.ComponentModel.DataAnnotations.RequiredAttribute?displayProperty=nameWithType>
- <xref:System.ComponentModel.DataAnnotations.StringLengthAttribute?displayProperty=nameWithType>
- <xref:System.ComponentModel.DataAnnotations.TimestampAttribute?displayProperty=nameWithType>
- <xref:System.ComponentModel.DataAnnotations.UIHintAttribute?displayProperty=nameWithType>
- <xref:System.ComponentModel.DataAnnotations.ValidationAttribute?displayProperty=nameWithType>
- <xref:System.ComponentModel.DataAnnotations.ValidationContext?displayProperty=nameWithType>
- <xref:System.ComponentModel.DataAnnotations.ValidationException?displayProperty=nameWithType>
- <xref:System.ComponentModel.DataAnnotations.ValidationResult?displayProperty=nameWithType>
- <xref:System.ComponentModel.DataAnnotations.Validator?displayProperty=nameWithType>
- <xref:System.ComponentModel.DataAnnotations.Schema.DatabaseGeneratedAttribute?displayProperty=nameWithType>
- <xref:System.ComponentModel.DataAnnotations.Schema.DatabaseGeneratedOption?displayProperty=nameWithType>

 <span data-ttu-id="6455b-308">**Visual Basic**</span><span class="sxs-lookup"><span data-stu-id="6455b-308">**Visual Basic**</span></span>

<span data-ttu-id="6455b-309">Visual Basic 현재 .NET 네이티브에서 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6455b-309">Visual Basic isn't currently supported in .NET Native.</span></span> <span data-ttu-id="6455b-310"><xref:Microsoft.VisualBasic>및 네임 스페이스의 다음 형식은 <xref:Microsoft.VisualBasic.CompilerServices> .NET 네이티브 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6455b-310">The following types in the <xref:Microsoft.VisualBasic> and <xref:Microsoft.VisualBasic.CompilerServices> namespaces aren't available in .NET Native:</span></span>

- <xref:Microsoft.VisualBasic.CallType?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Constants?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.HideModuleNameAttribute?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Strings?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.CompilerServices.Conversions?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.CompilerServices.DesignerGeneratedAttribute?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.CompilerServices.IncompleteInitialization?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.CompilerServices.NewLateBinding?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.CompilerServices.ObjectFlowControl?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.CompilerServices.ObjectFlowControl.ForLoopControl?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.CompilerServices.Operators?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.CompilerServices.OptionCompareAttribute?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.CompilerServices.OptionTextAttribute?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.CompilerServices.ProjectData?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.CompilerServices.StandardModuleAttribute?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.CompilerServices.StaticLocalInitFlag?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.CompilerServices.Utils?displayProperty=nameWithType>

<span data-ttu-id="6455b-311">**리플렉션 컨텍스트(System.Reflection.Context 네임스페이스)**</span><span class="sxs-lookup"><span data-stu-id="6455b-311">**Reflection Context (System.Reflection.Context namespace)**</span></span>

<span data-ttu-id="6455b-312"><xref:System.Reflection.Context.CustomReflectionContext?displayProperty=nameWithType>클래스는 .NET 네이티브에서 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6455b-312">The <xref:System.Reflection.Context.CustomReflectionContext?displayProperty=nameWithType> class isn't supported in .NET Native.</span></span>

<span data-ttu-id="6455b-313">**RTC(System.Net.Http.Rtc)**</span><span class="sxs-lookup"><span data-stu-id="6455b-313">**RTC (System.Net.Http.Rtc)**</span></span>

<span data-ttu-id="6455b-314">`System.Net.Http.RtcRequestFactory`클래스는 .NET 네이티브에서 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6455b-314">The `System.Net.Http.RtcRequestFactory` class isn't supported in .NET Native.</span></span>

<span data-ttu-id="6455b-315">**Windows Communication Foundation (WCF) (System.ServiceModel.\*)**</span><span class="sxs-lookup"><span data-stu-id="6455b-315">**Windows Communication Foundation (WCF) (System.ServiceModel.\*)**</span></span>

<span data-ttu-id="6455b-316">[System.servicemodel. \* 네임 스페이스](xref:System.ServiceModel) 의 형식은 .NET 네이티브 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6455b-316">The types in the [System.ServiceModel.\* namespaces](xref:System.ServiceModel) aren't supported in .NET Native.</span></span> <span data-ttu-id="6455b-317">여기에는 다음과 같은 형식이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6455b-317">These include the following types:</span></span>

- <xref:System.ServiceModel.ActionNotSupportedException?displayProperty=nameWithType>
- <xref:System.ServiceModel.BasicHttpBinding?displayProperty=nameWithType>
- <xref:System.ServiceModel.BasicHttpMessageCredentialType?displayProperty=nameWithType>
- <xref:System.ServiceModel.BasicHttpSecurity?displayProperty=nameWithType>
- <xref:System.ServiceModel.BasicHttpSecurityMode?displayProperty=nameWithType>
- <xref:System.ServiceModel.CallbackBehaviorAttribute?displayProperty=nameWithType>
- <xref:System.ServiceModel.ChannelFactory?displayProperty=nameWithType>
- <xref:System.ServiceModel.ChannelFactory%601?displayProperty=nameWithType>
- <xref:System.ServiceModel.ClientBase%601?displayProperty=nameWithType>
- <xref:System.ServiceModel.ClientBase%601.BeginOperationDelegate?displayProperty=nameWithType>
- <xref:System.ServiceModel.ClientBase%601.ChannelBase%601?displayProperty=nameWithType>
- <xref:System.ServiceModel.ClientBase%601.EndOperationDelegate?displayProperty=nameWithType>
- <xref:System.ServiceModel.ClientBase%601.InvokeAsyncCompletedEventArgs?displayProperty=nameWithType>
- <xref:System.ServiceModel.CommunicationException?displayProperty=nameWithType>
- <xref:System.ServiceModel.CommunicationObjectAbortedException?displayProperty=nameWithType>
- <xref:System.ServiceModel.CommunicationObjectFaultedException?displayProperty=nameWithType>
- <xref:System.ServiceModel.CommunicationState?displayProperty=nameWithType>
- <xref:System.ServiceModel.DataContractFormatAttribute?displayProperty=nameWithType>
- <xref:System.ServiceModel.DnsEndpointIdentity?displayProperty=nameWithType>
- <xref:System.ServiceModel.DuplexChannelFactory%601?displayProperty=nameWithType>
- <xref:System.ServiceModel.DuplexClientBase%601?displayProperty=nameWithType>
- <xref:System.ServiceModel.EndpointAddress?displayProperty=nameWithType>
- <xref:System.ServiceModel.EndpointAddressBuilder?displayProperty=nameWithType>
- <xref:System.ServiceModel.EndpointIdentity?displayProperty=nameWithType>
- <xref:System.ServiceModel.EndpointNotFoundException?displayProperty=nameWithType>
- <xref:System.ServiceModel.EnvelopeVersion?displayProperty=nameWithType>
- <xref:System.ServiceModel.ExceptionDetail?displayProperty=nameWithType>
- <xref:System.ServiceModel.FaultCode?displayProperty=nameWithType>
- <xref:System.ServiceModel.FaultContractAttribute?displayProperty=nameWithType>
- <xref:System.ServiceModel.FaultException?displayProperty=nameWithType>
- <xref:System.ServiceModel.FaultException%601?displayProperty=nameWithType>
- <xref:System.ServiceModel.FaultReason?displayProperty=nameWithType>
- <xref:System.ServiceModel.FaultReasonText?displayProperty=nameWithType>
- <xref:System.ServiceModel.HttpBindingBase?displayProperty=nameWithType>
- <xref:System.ServiceModel.HttpClientCredentialType?displayProperty=nameWithType>
- <xref:System.ServiceModel.HttpTransportSecurity?displayProperty=nameWithType>
- <xref:System.ServiceModel.IClientChannel?displayProperty=nameWithType>
- <xref:System.ServiceModel.ICommunicationObject?displayProperty=nameWithType>
- <xref:System.ServiceModel.IContextChannel?displayProperty=nameWithType>
- <xref:System.ServiceModel.IDefaultCommunicationTimeouts?displayProperty=nameWithType>
- <xref:System.ServiceModel.IExtensibleObject%601?displayProperty=nameWithType>
- <xref:System.ServiceModel.IExtension%601?displayProperty=nameWithType>
- <xref:System.ServiceModel.IExtensionCollection%601?displayProperty=nameWithType>
- <xref:System.ServiceModel.InstanceContext?displayProperty=nameWithType>
- <xref:System.ServiceModel.InvalidMessageContractException?displayProperty=nameWithType>
- <xref:System.ServiceModel.MessageBodyMemberAttribute?displayProperty=nameWithType>
- <xref:System.ServiceModel.MessageContractAttribute?displayProperty=nameWithType>
- <xref:System.ServiceModel.MessageContractMemberAttribute?displayProperty=nameWithType>
- <xref:System.ServiceModel.MessageCredentialType?displayProperty=nameWithType>
- <xref:System.ServiceModel.MessageHeader%601?displayProperty=nameWithType>
- <xref:System.ServiceModel.MessageHeaderException?displayProperty=nameWithType>
- <xref:System.ServiceModel.MessageParameterAttribute?displayProperty=nameWithType>
- <xref:System.ServiceModel.MessageSecurityOverTcp?displayProperty=nameWithType>
- <xref:System.ServiceModel.MessageSecurityVersion?displayProperty=nameWithType>
- <xref:System.ServiceModel.NetHttpBinding?displayProperty=nameWithType>
- <xref:System.ServiceModel.NetHttpMessageEncoding?displayProperty=nameWithType>
- <xref:System.ServiceModel.NetTcpBinding?displayProperty=nameWithType>
- <xref:System.ServiceModel.NetTcpSecurity?displayProperty=nameWithType>
- <xref:System.ServiceModel.OperationContext?displayProperty=nameWithType>
- <xref:System.ServiceModel.OperationContextScope?displayProperty=nameWithType>
- <xref:System.ServiceModel.OperationContractAttribute?displayProperty=nameWithType>
- <xref:System.ServiceModel.OperationFormatStyle?displayProperty=nameWithType>
- <xref:System.ServiceModel.ProtocolException?displayProperty=nameWithType>
- <xref:System.ServiceModel.QuotaExceededException?displayProperty=nameWithType>
- <xref:System.ServiceModel.SecurityMode?displayProperty=nameWithType>
- <xref:System.ServiceModel.ServerTooBusyException?displayProperty=nameWithType>
- <xref:System.ServiceModel.ServiceActivationException?displayProperty=nameWithType>
- <xref:System.ServiceModel.ServiceContractAttribute?displayProperty=nameWithType>
- <xref:System.ServiceModel.ServiceKnownTypeAttribute?displayProperty=nameWithType>
- <xref:System.ServiceModel.SpnEndpointIdentity?displayProperty=nameWithType>
- <xref:System.ServiceModel.TcpClientCredentialType?displayProperty=nameWithType>
- <xref:System.ServiceModel.TcpTransportSecurity?displayProperty=nameWithType>
- <xref:System.ServiceModel.TransferMode?displayProperty=nameWithType>
- <xref:System.ServiceModel.UnknownMessageReceivedEventArgs?displayProperty=nameWithType>
- <xref:System.ServiceModel.UpnEndpointIdentity?displayProperty=nameWithType>
- <xref:System.ServiceModel.XmlSerializerFormatAttribute?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.AddressHeader?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.AddressHeaderCollection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.AddressingVersion?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.ChannelManagerBase?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.ChannelParameterCollection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.CommunicationObject?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.CompressionFormat?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.ConnectionOrientedTransportBindingElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.CustomBinding?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.FaultConverter?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.HttpRequestMessageProperty?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.HttpResponseMessageProperty?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.HttpsTransportBindingElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.HttpTransportBindingElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.IChannel?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.IChannelFactory?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.IChannelFactory%601?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.IDuplexChannel?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.IDuplexSession?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.IDuplexSessionChannel?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.IHttpCookieContainerManager?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.IInputChannel?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.IInputSession?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.IInputSessionChannel?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.IMessageProperty?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.IOutputChannel?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.IOutputSession?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.IOutputSessionChannel?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.IRequestChannel?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.IRequestSessionChannel?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.ISession?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.ISessionChannel%601?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.LocalClientSecuritySettings?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.Message?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.MessageBuffer?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.MessageEncoder?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.MessageEncoderFactory?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.MessageEncodingBindingElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.MessageFault?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.MessageHeader?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.MessageHeaderInfo?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.MessageHeaders?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.MessageProperties?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.MessageState?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.MessageVersion?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.RequestContext?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.SecurityBindingElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.SecurityHeaderLayout?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.TcpConnectionPoolSettings?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.TcpTransportBindingElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.TransportBindingElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.TransportSecurityBindingElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.WebSocketTransportSettings?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.WebSocketTransportUsage?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.WindowsStreamSecurityBindingElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Description.ClientCredentials?displayProperty=nameWithType>
- <xref:System.ServiceModel.Description.ContractDescription?displayProperty=nameWithType>
- <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior?displayProperty=nameWithType>
- <xref:System.ServiceModel.Description.FaultDescription?displayProperty=nameWithType>
- <xref:System.ServiceModel.Description.FaultDescriptionCollection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Description.IContractBehavior?displayProperty=nameWithType>
- <xref:System.ServiceModel.Description.IEndpointBehavior?displayProperty=nameWithType>
- <xref:System.ServiceModel.Description.IOperationBehavior?displayProperty=nameWithType>
- <xref:System.ServiceModel.Description.MessageBodyDescription?displayProperty=nameWithType>
- <xref:System.ServiceModel.Description.MessageDescription?displayProperty=nameWithType>
- <xref:System.ServiceModel.Description.MessageDescriptionCollection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Description.MessageDirection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Description.MessageHeaderDescription?displayProperty=nameWithType>
- <xref:System.ServiceModel.Description.MessageHeaderDescriptionCollection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Description.MessagePartDescription?displayProperty=nameWithType>
- <xref:System.ServiceModel.Description.MessagePartDescriptionCollection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Description.MessagePropertyDescription?displayProperty=nameWithType>
- <xref:System.ServiceModel.Description.MessagePropertyDescriptionCollection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Description.OperationDescription?displayProperty=nameWithType>
- <xref:System.ServiceModel.Description.OperationDescriptionCollection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Description.ServiceEndpoint?displayProperty=nameWithType>
- <xref:System.ServiceModel.Dispatcher.ClientOperation?displayProperty=nameWithType>
- <xref:System.ServiceModel.Dispatcher.ClientRuntime?displayProperty=nameWithType>
- <xref:System.ServiceModel.Dispatcher.DispatchOperation?displayProperty=nameWithType>
- <xref:System.ServiceModel.Dispatcher.DispatchRuntime?displayProperty=nameWithType>
- <xref:System.ServiceModel.Dispatcher.EndpointDispatcher?displayProperty=nameWithType>
- <xref:System.ServiceModel.Dispatcher.IClientMessageFormatter?displayProperty=nameWithType>
- <xref:System.ServiceModel.Dispatcher.IClientMessageInspector?displayProperty=nameWithType>
- <xref:System.ServiceModel.Dispatcher.IClientOperationSelector?displayProperty=nameWithType>
- <xref:System.ServiceModel.Dispatcher.IParameterInspector?displayProperty=nameWithType>
- <xref:System.ServiceModel.Security.BasicSecurityProfileVersion?displayProperty=nameWithType>
- <xref:System.ServiceModel.Security.HttpDigestClientCredential?displayProperty=nameWithType>
- <xref:System.ServiceModel.Security.MessageSecurityException?displayProperty=nameWithType>
- <xref:System.ServiceModel.Security.SecureConversationVersion?displayProperty=nameWithType>
- <xref:System.ServiceModel.Security.SecurityAccessDeniedException?displayProperty=nameWithType>
- <xref:System.ServiceModel.Security.SecurityPolicyVersion?displayProperty=nameWithType>
- <xref:System.ServiceModel.Security.SecurityVersion?displayProperty=nameWithType>
- <xref:System.ServiceModel.Security.TrustVersion?displayProperty=nameWithType>
- <xref:System.ServiceModel.Security.UserNamePasswordClientCredential?displayProperty=nameWithType>
- <xref:System.ServiceModel.Security.WindowsClientCredential?displayProperty=nameWithType>
- <xref:System.ServiceModel.Security.Tokens.SecureConversationSecurityTokenParameters?displayProperty=nameWithType>
- <xref:System.ServiceModel.Security.Tokens.SecurityTokenParameters?displayProperty=nameWithType>
- <xref:System.ServiceModel.Security.Tokens.SupportingTokenParameters?displayProperty=nameWithType>
- <xref:System.ServiceModel.Security.Tokens.UserNameSecurityTokenParameters?displayProperty=nameWithType>

### <a name="differences-in-serializers"></a><span data-ttu-id="6455b-318">serializer의 차이점</span><span class="sxs-lookup"><span data-stu-id="6455b-318">Differences in serializers</span></span>

<span data-ttu-id="6455b-319"><xref:System.Runtime.Serialization.DataContractSerializer>, <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>및 <xref:System.Xml.Serialization.XmlSerializer> 클래스의 serialization 및 deserialization에는 다음과 같은 차이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6455b-319">The following differences concern serialization and deserialization with the <xref:System.Runtime.Serialization.DataContractSerializer>, <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>, and <xref:System.Xml.Serialization.XmlSerializer> classes:</span></span>

- <span data-ttu-id="6455b-320">.NET 네이티브에서 <xref:System.Runtime.Serialization.DataContractSerializer> 및는 <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> 해당 형식이 루트 serialization 형식이 아닌 기본 클래스 멤버를 포함 하는 파생 클래스를 serialize 또는 deserialize 할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6455b-320">In .NET Native, <xref:System.Runtime.Serialization.DataContractSerializer> and <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> fail to serialize or deserialize a derived class that has a base class member whose type isn't a root serialization type.</span></span> <span data-ttu-id="6455b-321">예를 들어 다음 코드에서 `Y` 를 직렬화 또는 역직렬화하려고 하면 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="6455b-321">For example, in the following code, trying to serialize or deserialize `Y` results in an error:</span></span>

  [!code-csharp[ProjectN#10](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn/cs/compat3.cs#10)]

  <span data-ttu-id="6455b-322">기본 클래스의 멤버가 serialization 중에 트래버스되지 않으므로 serializer가 `InnerType` 형식을 인식하지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="6455b-322">Type `InnerType` isn't known to the serializer, because the members of the base class aren't traversed during serialization.</span></span>

- <span data-ttu-id="6455b-323"><xref:System.Runtime.Serialization.DataContractSerializer> 및 <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> 가 <xref:System.Collections.Generic.IEnumerable%601> 인터페이스를 구현하는 클래스나 구조체를 serialize하지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="6455b-323"><xref:System.Runtime.Serialization.DataContractSerializer> and <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> fail to serialize a class or structure that implements the <xref:System.Collections.Generic.IEnumerable%601> interface.</span></span> <span data-ttu-id="6455b-324">예를 들어 다음과 같은 형식은 직렬화 또는 역직렬화할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6455b-324">For example, the following types fail to serialize or deserialize:</span></span>

- <span data-ttu-id="6455b-325"><xref:System.Xml.Serialization.XmlSerializer> 가 다음 개체 값을 serialize하지 못합니다. serialize할 정확한 개체 형식을 알 수 없기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="6455b-325"><xref:System.Xml.Serialization.XmlSerializer> fails to serialize the following object value, because it doesn't know the exact type of the object to be serialized:</span></span>

- <span data-ttu-id="6455b-326"><xref:System.Xml.Serialization.XmlSerializer> 는 직렬화된 개체의 형식이 <xref:System.Xml.XmlQualifiedName>이면 해당 개체를 직렬화 또는 역직렬화할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6455b-326"><xref:System.Xml.Serialization.XmlSerializer> fails to serialize or deserialize if the type of the serialized object is <xref:System.Xml.XmlQualifiedName>.</span></span>

- <span data-ttu-id="6455b-327">모든 serializer(<xref:System.Runtime.Serialization.DataContractSerializer>, <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>및 <xref:System.Xml.Serialization.XmlSerializer>)는 <xref:System.Xml.Linq.XElement?displayProperty=nameWithType> 를 포함하는 형식 또는 <xref:System.Xml.Linq.XElement>형식에 대해 serialization 코드를 생성하지 못하며,</span><span class="sxs-lookup"><span data-stu-id="6455b-327">All serializers (<xref:System.Runtime.Serialization.DataContractSerializer>, <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>, and <xref:System.Xml.Serialization.XmlSerializer>) fail to generate serialization code for type <xref:System.Xml.Linq.XElement?displayProperty=nameWithType> or for a type that contains <xref:System.Xml.Linq.XElement>.</span></span> <span data-ttu-id="6455b-328">대신 빌드 시간 오류가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6455b-328">They display build-time errors instead.</span></span>

- <span data-ttu-id="6455b-329">serialization 형식의 다음 생성자에 대해서는 정상적인 작동이 보장되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6455b-329">The following constructors of the serialization types aren't guaranteed to work as expected:</span></span>

  - <xref:System.Runtime.Serialization.DataContractSerializer.%23ctor%28System.Type%2CSystem.Collections.Generic.IEnumerable%7BSystem.Type%7D%29>

  - <xref:System.Runtime.Serialization.DataContractSerializer.%23ctor%28System.Type%2CSystem.Runtime.Serialization.DataContractSerializerSettings%29>

  - <xref:System.Runtime.Serialization.DataContractSerializer.%23ctor%28System.Type%2CSystem.String%2CSystem.String%2CSystem.Collections.Generic.IEnumerable%7BSystem.Type%7D%29>

  - <xref:System.Runtime.Serialization.DataContractSerializer.%23ctor%28System.Type%2CSystem.Xml.XmlDictionaryString%2CSystem.Xml.XmlDictionaryString%2CSystem.Collections.Generic.IEnumerable%7BSystem.Type%7D%29>

  - <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.%23ctor%28System.Type%2CSystem.Runtime.Serialization.Json.DataContractJsonSerializerSettings%29>

  - <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.%23ctor%28System.Type%2CSystem.Collections.Generic.IEnumerable%7BSystem.Type%7D%29>

  - <xref:System.Xml.Serialization.XmlSerializer.%23ctor%28System.Type%2CSystem.String%29>

  - <xref:System.Xml.Serialization.XmlSerializer.%23ctor%28System.Type%2CSystem.Type%5B%5D%29>

  - <xref:System.Xml.Serialization.XmlSerializer.%23ctor%28System.Type%2CSystem.Xml.Serialization.XmlAttributeOverrides%29>

  - <xref:System.Xml.Serialization.XmlSerializer.%23ctor%28System.Type%2CSystem.Xml.Serialization.XmlRootAttribute%29>

  - <xref:System.Xml.Serialization.XmlSerializer.%23ctor%28System.Type%2CSystem.Xml.Serialization.XmlAttributeOverrides%2CSystem.Type%5B%5D%2CSystem.Xml.Serialization.XmlRootAttribute%2CSystem.String%29>

- <span data-ttu-id="6455b-330"><xref:System.Xml.Serialization.XmlSerializer> 는 메서드에 다음 특성이 포함된 형식에 대해 코드를 생성하지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="6455b-330"><xref:System.Xml.Serialization.XmlSerializer> fails to generate code for a type that has methods attributed with any of the following attributes:</span></span>

  - <xref:System.Runtime.Serialization.OnSerializingAttribute>

  - <xref:System.Runtime.Serialization.OnSerializedAttribute>

  - <xref:System.Runtime.Serialization.OnDeserializingAttribute>

  - <xref:System.Runtime.Serialization.OnDeserializedAttribute>

- <span data-ttu-id="6455b-331"><xref:System.Xml.Serialization.XmlSerializer> 는 <xref:System.Xml.Serialization.IXmlSerializable> 사용자 지정 serialization 인터페이스를 따르지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6455b-331"><xref:System.Xml.Serialization.XmlSerializer> doesn't honor the <xref:System.Xml.Serialization.IXmlSerializable> custom serialization interface.</span></span> <span data-ttu-id="6455b-332">이 인터페이스를 구현하는 클래스가 있는 경우 <xref:System.Xml.Serialization.XmlSerializer> 는 해당 형식을 POCO(Plain Old CLR 개체) 형식으로 간주하여 public 속성만 serialize합니다.</span><span class="sxs-lookup"><span data-stu-id="6455b-332">If you have a class that implements this interface, <xref:System.Xml.Serialization.XmlSerializer> considers the type a plain old CLR object (POCO) type and serializes only its public properties.</span></span>

- <span data-ttu-id="6455b-333">일반 개체 직렬화는 <xref:System.Exception> 및에서 잘 작동 하지 않습니다 <xref:System.Runtime.Serialization.DataContractSerializer> <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> .</span><span class="sxs-lookup"><span data-stu-id="6455b-333">Serializing a plain <xref:System.Exception> object doesn't work well with <xref:System.Runtime.Serialization.DataContractSerializer> and <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>.</span></span>

<a name="VS"></a>

## <a name="visual-studio-differences"></a><span data-ttu-id="6455b-334">Visual Studio의 차이점</span><span class="sxs-lookup"><span data-stu-id="6455b-334">Visual Studio differences</span></span>

<span data-ttu-id="6455b-335">**예외 및 디버깅**</span><span class="sxs-lookup"><span data-stu-id="6455b-335">**Exceptions and debugging**</span></span>

<span data-ttu-id="6455b-336">디버거에서 .NET 네이티브를 사용 하 여 컴파일된 응용 프로그램을 실행 하는 경우 다음 예외 형식에 대해 첫 번째 예외를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6455b-336">When you're running apps compiled by using .NET Native in the debugger, first-chance exceptions are enabled for the following exception types:</span></span>

- <xref:System.MemberAccessException>

- <xref:System.TypeAccessException>

<span data-ttu-id="6455b-337">**앱 빌드**</span><span class="sxs-lookup"><span data-stu-id="6455b-337">**Building apps**</span></span>

<span data-ttu-id="6455b-338">Visual Studio에서 기본적으로 사용되는 x86 빌드 도구를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6455b-338">Use the x86 build tools that are used by default by Visual Studio.</span></span> <span data-ttu-id="6455b-339">C:\Program Files (x86)\MSBuild\12.0\bin\amd64에 있는 AMD64 MSBuild 도구를 사용하는 경우 빌드 문제가 발생할 수 있으므로 사용하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="6455b-339">We don't recommend using the AMD64 MSBuild tools, which are found in C:\Program Files (x86)\MSBuild\12.0\bin\amd64; these may create build problems.</span></span>

<span data-ttu-id="6455b-340">**프로파일러**</span><span class="sxs-lookup"><span data-stu-id="6455b-340">**Profilers**</span></span>

- <span data-ttu-id="6455b-341">Visual Studio CPU 프로파일러 및 XAML 메모리 프로파일러에 내 코드만 옵션이 올바르게 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6455b-341">The Visual Studio CPU Profiler and XAML Memory Profiler don't display Just-My-Code correctly.</span></span>

- <span data-ttu-id="6455b-342">XAML 메모리 프로파일러에 관리되는 힙 데이터가 정확하게 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6455b-342">The XAML Memory Profiler doesn't accurately display managed heap data.</span></span>

- <span data-ttu-id="6455b-343">CPU 프로파일러가 모듈을 올바르게 식별하지 않으며 접두사가 붙은 함수 이름을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="6455b-343">The CPU Profiler doesn't correctly identify modules, and displays prefixed function names.</span></span>

<span data-ttu-id="6455b-344">**단위 테스트 라이브러리 프로젝트**</span><span class="sxs-lookup"><span data-stu-id="6455b-344">**Unit Test Library projects**</span></span>

<span data-ttu-id="6455b-345">Windows 스토어 앱 프로젝트에 대 한 단위 테스트 라이브러리에서 .NET 네이티브를 사용 하도록 설정 하는 것은 지원 되지 않으며 프로젝트 빌드에 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="6455b-345">Enabling .NET Native on a Unit Test Library for a Windows Store apps project isn't supported and causes the project to fail to build.</span></span>

## <a name="see-also"></a><span data-ttu-id="6455b-346">추가 정보</span><span class="sxs-lookup"><span data-stu-id="6455b-346">See also</span></span>

- [<span data-ttu-id="6455b-347">시작</span><span class="sxs-lookup"><span data-stu-id="6455b-347">Getting Started</span></span>](getting-started-with-net-native.md)
- [<span data-ttu-id="6455b-348">런타임 지시문(rd.xml) 구성 파일 참조</span><span class="sxs-lookup"><span data-stu-id="6455b-348">Runtime Directives (rd.xml) Configuration File Reference</span></span>](runtime-directives-rd-xml-configuration-file-reference.md)
- <span data-ttu-id="6455b-349">[Windows 스토어 앱 용 .NET 개요](/previous-versions/windows/apps/br230302(v=vs.140))</span><span class="sxs-lookup"><span data-stu-id="6455b-349">[.NET For Windows Store apps overview](/previous-versions/windows/apps/br230302(v=vs.140))</span></span>
- [<span data-ttu-id="6455b-350">Windows 스토어 앱 및 Windows 런타임에 대한 .NET Framework 지원</span><span class="sxs-lookup"><span data-stu-id="6455b-350">.NET Framework Support for Windows Store Apps and Windows Runtime</span></span>](../cross-platform/support-for-windows-store-apps-and-windows-runtime.md)
