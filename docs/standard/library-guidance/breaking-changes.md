---
title: 호환성이 손상되는 변경 및 .NET 라이브러리
description: .NET 라이브러리를 만들 때 호환성이 손상되는 변경 탐색을 위한 모범 사례 권장 사항.
ms.date: 10/02/2018
ms.openlocfilehash: 2cbd9e0a818b52aede6c9b1f60fdf52dcbd7b96f
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76731472"
---
# <a name="breaking-changes"></a><span data-ttu-id="54cd9-103">호환성이 손상되는 변경</span><span class="sxs-lookup"><span data-stu-id="54cd9-103">Breaking changes</span></span>

<span data-ttu-id="54cd9-104">.NET 라이브러리에서 기존 사용자를 위한 안정성과 미래를 위한 혁신 간에 균형을 맞추는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="54cd9-104">It's important for a .NET library to find a balance between stability for existing users and innovation for the future.</span></span> <span data-ttu-id="54cd9-105">라이브러리 작성자는 코드가 완벽해질 때까지 리팩터링 및 재고하는 경향이 있지만, 특히 낮은 수준의 라이브러리의 경우에는 기존 사용자의 업무 중단에 부정적인 영향을 미칩니다.</span><span class="sxs-lookup"><span data-stu-id="54cd9-105">Library authors lean towards refactoring and rethinking code until it's perfect, but breaking your existing users has a negative impact, especially for low-level libraries.</span></span>

## <a name="project-types-and-breaking-changes"></a><span data-ttu-id="54cd9-106">프로젝트 형식 및 호환성이 손상되는 변경</span><span class="sxs-lookup"><span data-stu-id="54cd9-106">Project types and breaking changes</span></span>

<span data-ttu-id="54cd9-107">.NET 커뮤니티에서 라이브러리를 사용하는 방법은 최종 사용자 개발자에서 호환성이 손상되는 변경의 효과를 변화시킵니다.</span><span class="sxs-lookup"><span data-stu-id="54cd9-107">How a library is used by the .NET community changes the effect of breaking changes on end-user developers.</span></span>

- <span data-ttu-id="54cd9-108">직렬 변환기, HTML 파서, 데이터베이스 개체 관계형 매퍼 또는 웹 프레임워크와 같은 **낮음 및 중간 수준의 라이브러리**는 호환성이 손상되는 변경의 영향을 가장 많이 받습니다.</span><span class="sxs-lookup"><span data-stu-id="54cd9-108">**Low and middle-level libraries** like a serializer, HTML parser, database object-relational mapper, or web framework are the most affected by breaking changes.</span></span>

  <span data-ttu-id="54cd9-109">빌딩 블록 패키지는 최종 사용자 개발자가 애플리케이션을 빌드하는 데 사용하고 다른 라이브러리는 NuGet 종속성으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="54cd9-109">Building block packages are used by end-user developers to build applications, and by other libraries as NuGet dependencies.</span></span> <span data-ttu-id="54cd9-110">예를 들어 애플리케이션을 빌드하고 있고 오픈 소스 클라이언트를 사용하여 웹 서비스를 호출하는 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="54cd9-110">For example, you're building an application and are using an open-source client to call a web service.</span></span> <span data-ttu-id="54cd9-111">클라이언트가 사용하는 종속성에 대한 중요 업데이트는 수정할 수 있는 것이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="54cd9-111">A breaking update to a dependency the client uses isn't something you can fix.</span></span> <span data-ttu-id="54cd9-112">이는 변경해야 하는 오픈 소스 클라이언트이므로 제어할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="54cd9-112">It's the open-source client that needs to be changed and you have no control over it.</span></span> <span data-ttu-id="54cd9-113">호환 가능한 버전의 라이브러리를 찾거나 수정 사항을 클라이언트 라이브러리에 제출하고 새 버전을 기다려야 합니다.</span><span class="sxs-lookup"><span data-stu-id="54cd9-113">You have to find compatible versions of the libraries or submit a fix to the client library and wait for a new version.</span></span> <span data-ttu-id="54cd9-114">최악의 상황은 서로 호환되지 않는 세 번째 버전의 라이브러리에 종속된 두 개의 라이브러리를 사용하려는 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="54cd9-114">The worst-case situation is if you want to use two libraries that depend on mutually incompatible versions of a third library.</span></span>

- <span data-ttu-id="54cd9-115">UI의 도구 모음과 같은 **고급 라이브러리**는 호환성이 손상되는 변경에 덜 민감합니다.</span><span class="sxs-lookup"><span data-stu-id="54cd9-115">**High-level libraries** like a suite of UI controls are less sensitive to breaking changes.</span></span>

  <span data-ttu-id="54cd9-116">고급 라이브러리는 최종 사용자 애플리케이션에서 직접 참조됩니다.</span><span class="sxs-lookup"><span data-stu-id="54cd9-116">High-level libraries are directly referenced in an end-user application.</span></span> <span data-ttu-id="54cd9-117">호환성이 손상되는 변경이 발생한 경우 개발자는 최신 버전으로 업데이트하도록 선택하거나 호환성이 손상되는 변경에 맞게 해당 애플리케이션을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54cd9-117">If breaking changes occur, the developer can choose to update to the latest version, or can modify their application to work with the breaking change.</span></span>

<span data-ttu-id="54cd9-118">✔️ 라이브러리 사용 방법에 대해 생각해 보세요.</span><span class="sxs-lookup"><span data-stu-id="54cd9-118">✔️ DO think about how your library will be used.</span></span> <span data-ttu-id="54cd9-119">호환성이 손상되는 변경은 이를 사용하는 애플리케이션과 라이브러리에 어떤 영향을 주나요?</span><span class="sxs-lookup"><span data-stu-id="54cd9-119">What effect will breaking changes have on applications and libraries that use it?</span></span>

<span data-ttu-id="54cd9-120">✔️ 낮은 수준의 .NET 라이브러리를 개발할 때 호환성이 손상되는 변경을 최소화합니다.</span><span class="sxs-lookup"><span data-stu-id="54cd9-120">✔️ DO minimize breaking changes when developing a low-level .NET library.</span></span>

<span data-ttu-id="54cd9-121">✔️ 새 NuGet 패키지로 라이브러리의 주 버전 재작성을 게시하는 것을 고려하세요.</span><span class="sxs-lookup"><span data-stu-id="54cd9-121">✔️ CONSIDER publishing a major rewrite of a library as a new NuGet package.</span></span>

## <a name="types-of-breaking-changes"></a><span data-ttu-id="54cd9-122">호환성이 손상되는 변경의 형식</span><span class="sxs-lookup"><span data-stu-id="54cd9-122">Types of breaking changes</span></span>

<span data-ttu-id="54cd9-123">호환성이 손상되는 변경은 다른 범주로 분류되고 동일하게 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="54cd9-123">Breaking changes fall into different categories and aren't equally impactful.</span></span>

### <a name="source-breaking-change"></a><span data-ttu-id="54cd9-124">소스 주요 변경 내용</span><span class="sxs-lookup"><span data-stu-id="54cd9-124">Source breaking change</span></span>

<span data-ttu-id="54cd9-125">소스 주요 변경 내용은 프로그램 실행에 영향을 주지 않지만 다음에 애플리케이션을 다시 컴파일할 때 컴파일 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="54cd9-125">A source breaking change doesn't affect program execution but will cause compilation errors the next time the application is recompiled.</span></span> <span data-ttu-id="54cd9-126">예를 들어 새 오버로드는 이전에 모호하지 않은 메서드 호출에 모호함을 만들거나 이름이 바뀐 매개 변수는 명명된 매개 변수를 사용하는 호출자의 연결을 끊을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54cd9-126">For example, a new overload can create an ambiguity in method calls that were unambiguous previously, or a renamed parameter will break callers that use named parameters.</span></span>

```csharp
public class Task
{
    // Adding a type called Task could conflict with System.Threading.Tasks.Task at compilation
}
```

<span data-ttu-id="54cd9-127">소스 주요 변경 내용은 개발자가 애플리케이션을 다시 컴파일할 때만 해로울 수 있으므로 가장 방해가 적은 주요 변경 내용입니다.</span><span class="sxs-lookup"><span data-stu-id="54cd9-127">Because a source breaking change is only harmful when developers recompile their applications, it's the least disruptive breaking change.</span></span> <span data-ttu-id="54cd9-128">개발자는 자신의 손상된 소스 코드를 쉽게 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54cd9-128">Developers can fix their own broken source code easily.</span></span>

### <a name="behavior-breaking-change"></a><span data-ttu-id="54cd9-129">동작 주요 변경 내용</span><span class="sxs-lookup"><span data-stu-id="54cd9-129">Behavior breaking change</span></span>

<span data-ttu-id="54cd9-130">동작 변경 내용은 가장 일반적인 주요 변경 내용의 유형입니다. 동작의 거의 모든 변경 내용은 사용자를 손상시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54cd9-130">Behavior changes are the most common type of breaking change: almost any change in behavior could break someone.</span></span> <span data-ttu-id="54cd9-131">메서드 서명, throw된 예외, 입력 또는 출력 데이터 형식과 같은 라이브러리 변경 내용은 모두 라이브러리 소비자에게 부정적인 영향을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54cd9-131">Changes to your library, such as method signatures, exceptions thrown or input or output data formats, could all negatively impact your library consumers.</span></span> <span data-ttu-id="54cd9-132">사용자가 이전에 손상된 동작을 사용하는 경우 버그 수정도 주요 변경 내용으로 한정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54cd9-132">Even a bug fix can qualify as a breaking change if users relied on the previously broken behavior.</span></span>

<span data-ttu-id="54cd9-133">기능을 추가하고 잘못된 동작을 개선하는 것은 좋은 것이지만, 주의하지 않으면 기존 사용자가 업그레이드하기가 매우 어려울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54cd9-133">Adding features and improving bad behaviors is a good thing, but without care it can make it very hard for existing users to upgrade.</span></span> <span data-ttu-id="54cd9-134">개발자가 동작 주요 변경 내용을 처리하는 데 도움이 되는 한 가지 방법은 설정 뒤에 숨기는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="54cd9-134">One approach to helping developers deal with behavior breaking changes is to hide them behind settings.</span></span> <span data-ttu-id="54cd9-135">설정을 통해 개발자가 최신 버전의 라이브러리로 업데이트하는 동시에 주요 변경 내용을 옵트인하거나 옵트아웃하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54cd9-135">Settings let developers update to the latest version of your library while at the same time choosing to opt in or opt out of breaking changes.</span></span> <span data-ttu-id="54cd9-136">이 전략을 사용하면 개발자는 소비 코드를 시간 경과에 따라 조정하면서 최신 상태로 유지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54cd9-136">This strategy lets developers stay up to date while letting their consuming code adapt over time.</span></span>

<span data-ttu-id="54cd9-137">예를 들어 ASP.NET Core MVC는 `MvcOptions`에서 활성화 및 비활성화 기능을 수정하는 [호환성 버전](/aspnet/core/mvc/compatibility-version)의 개념을 가지고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54cd9-137">For example, ASP.NET Core MVC has the concept of a [compatibility version](/aspnet/core/mvc/compatibility-version) that modifies the features enabled and disabled on `MvcOptions`.</span></span>

<span data-ttu-id="54cd9-138">✔️ 기존 사용자에게 영향을 줄 경우 기본적으로 새 기능을 사용하지 않고 개발자가 설정을 사용하여 기능을 옵트인하도록 허용하는 것을 고려하세요.</span><span class="sxs-lookup"><span data-stu-id="54cd9-138">✔️ CONSIDER leaving new features off by default, if they affect existing users, and let developers opt in to the feature with a setting.</span></span>

### <a name="binary-breaking-change"></a><span data-ttu-id="54cd9-139">이진 주요 변경 내용</span><span class="sxs-lookup"><span data-stu-id="54cd9-139">Binary breaking change</span></span>

<span data-ttu-id="54cd9-140">라이브러리의 공용 API를 변경할 때 이진 주요 변경 내용이 발생하므로, 라이브러리의 이전 버전에 대해 컴파일된 어셈블리는 더 이상 API를 호출할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="54cd9-140">A binary breaking change happens when you change the public API of your library, so assemblies compiled against older versions of your library are no longer able to call the API.</span></span> <span data-ttu-id="54cd9-141">예를 들어 새 매개 변수를 추가하여 메서드의 서명을 변경하면 이전 버전의 라이브러리에 대해 컴파일된 어셈블리가 <xref:System.MissingMethodException>을 throw할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54cd9-141">For example, changing a method's signature by adding a new parameter will cause assemblies compiled against the older version of the library to throw a <xref:System.MissingMethodException>.</span></span>

<span data-ttu-id="54cd9-142">이진 주요 변경 내용으로 인해 **전체 어셈블리**도 손상될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54cd9-142">A binary breaking change can also break an **entire assembly**.</span></span> <span data-ttu-id="54cd9-143">`AssemblyName`을 사용하여 어셈블리 이름을 바꾸면 어셈블리의 강력한 이름 지정 키가 추가, 제거 또는 변경되므로 어셈블리의 ID가 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="54cd9-143">Renaming an assembly with `AssemblyName` will change the assembly's identity, as will adding, removing, or changing the assembly's strong naming key.</span></span> <span data-ttu-id="54cd9-144">어셈블리 ID가 변경되면 이를 사용하는 모든 컴파일된 코드가 중단됩니다.</span><span class="sxs-lookup"><span data-stu-id="54cd9-144">A change of an assembly's identity will break all compiled code that uses it.</span></span>

<span data-ttu-id="54cd9-145">❌ 어셈블리 이름을 변경하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="54cd9-145">❌ DO NOT change an assembly name.</span></span>

<span data-ttu-id="54cd9-146">❌ 강력한 이름 지정 키를 추가, 제거 또는 변경하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="54cd9-146">❌ DO NOT add, remove, or change the strong naming key.</span></span>

<span data-ttu-id="54cd9-147">✔️ 인터페이스 대신 추상 기본 클래스를 사용하는 것을 고려하세요.</span><span class="sxs-lookup"><span data-stu-id="54cd9-147">✔️ CONSIDER using abstract base classes instead of interfaces.</span></span>

> <span data-ttu-id="54cd9-148">인터페이스에 어떤 것도 추가하면 이를 구현하는 기존 유형이 실패하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="54cd9-148">Adding anything to an interface will cause existing types that implement it to fail.</span></span> <span data-ttu-id="54cd9-149">추상 기본 클래스를 사용하면 기본 가상 구현을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54cd9-149">An abstract base class allows you to add a default virtual implementation.</span></span>

<span data-ttu-id="54cd9-150">제거하려는 형식 및 멤버에 <xref:System.ObsoleteAttribute>를 배치하는 것을 고려하세요.</span><span class="sxs-lookup"><span data-stu-id="54cd9-150">✔️ CONSIDER placing the <xref:System.ObsoleteAttribute> on types and members that you intend to remove.</span></span> <span data-ttu-id="54cd9-151">이 특성에는 더 이상 사용되지 않는 API를 사용하지 않도록 코드를 업데이트하는 지침이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="54cd9-151">The attribute should have instructions for updating code to no longer use the obsolete API.</span></span>

> <span data-ttu-id="54cd9-152"><xref:System.ObsoleteAttribute>로 형식 및 메서드를 호출하는 코드는 특성에 제공된 메시지로 빌드 경고를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="54cd9-152">Code that calls types and methods with the <xref:System.ObsoleteAttribute> will generate a build warning with the message supplied to the attribute.</span></span> <span data-ttu-id="54cd9-153">이 경고는 사용되지 않는 API 노출 시간을 사용하는 사용자에게 마이그레이션을 허용하므로 사용되지 않는 API를 제거하면 대부분 더 이상 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="54cd9-153">The warnings give people who use the obsolete API surface time to migrate so that when the obsolete API is removed, most are no longer using it.</span></span>

```csharp
public class Document
{
    [Obsolete("LoadDocument(string) is obsolete. Use LoadDocument(Uri) instead.")]
    public static Document LoadDocument(string uri)
    {
        return LoadDocument(new Uri(uri));
    }

    public static Document LoadDocument(Uri uri)
    {
        // Load the document
    }
}
```

<span data-ttu-id="54cd9-154">✔️ 낮은 수준 및 중간 수준 라이브러리에서 <xref:System.ObsoleteAttribute>를 무기한으로 형식 및 메서드를 유지하는 것을 고려하세요.</span><span class="sxs-lookup"><span data-stu-id="54cd9-154">✔️ CONSIDER keeping types and methods with the <xref:System.ObsoleteAttribute> indefinitely in low and middle-level libraries.</span></span>

> <span data-ttu-id="54cd9-155">API를 제거하는 것은 이진 호환성이 손상되는 변경입니다.</span><span class="sxs-lookup"><span data-stu-id="54cd9-155">Removing APIs is a binary breaking change.</span></span> <span data-ttu-id="54cd9-156">사용되지 않는 형식 및 메서드를 유지 관리하는 것이 비용이 저렴하고 라이브러리에 많은 기술적 문제가 추가되지 않은 경우 이를 유지하는 것을 고려해 보세요.</span><span class="sxs-lookup"><span data-stu-id="54cd9-156">Considering keeping obsolete types and methods if maintaining them is low cost and doesn't add lot of technical debt to your library.</span></span> <span data-ttu-id="54cd9-157">형식 및 메서드를 제거하지 않으면 위에서 언급한 최악의 시나리오를 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54cd9-157">Not removing types and methods can help avoid the worst-case scenarios mentioned above.</span></span>

## <a name="see-also"></a><span data-ttu-id="54cd9-158">참조</span><span class="sxs-lookup"><span data-stu-id="54cd9-158">See also</span></span>

- [<span data-ttu-id="54cd9-159">C# 개발자를 위한 버전 및 업데이트 고려 사항</span><span class="sxs-lookup"><span data-stu-id="54cd9-159">Version and update considerations for C# developers</span></span>](../../csharp/whats-new/version-update-considerations.md)
- [<span data-ttu-id="54cd9-160">.NET에서의 API 주요 변경 내용에 대한 명확한 지침</span><span class="sxs-lookup"><span data-stu-id="54cd9-160">A definitive guide to API-breaking changes in .NET</span></span>](https://stackoverflow.com/questions/1456785/a-definitive-guide-to-api-breaking-changes-in-net)
- [<span data-ttu-id="54cd9-161">.NET 주요 변경 내용 규칙</span><span class="sxs-lookup"><span data-stu-id="54cd9-161">.NET breaking change rules</span></span>](https://github.com/dotnet/runtime/blob/master/docs/coding-guidelines/breaking-change-rules.md)

>[!div class="step-by-step"]
>[<span data-ttu-id="54cd9-162">이전</span><span class="sxs-lookup"><span data-stu-id="54cd9-162">Previous</span></span>](versioning.md)
