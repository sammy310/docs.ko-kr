---
title: '자습서: 특성 사용 - C#'
description: C#에서 특성이 작동하는 방식을 알아봅니다.
author: mgroves
ms.technology: csharp-fundamentals
ms.date: 03/06/2017
ms.assetid: b152cf36-76e4-43a5-b805-1a1952e53b79
ms.openlocfilehash: 24cb7d35a89fda78511dc4ba725b69c5d601a008
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "75937467"
---
# <a name="use-attributes-in-c"></a><span data-ttu-id="ba43c-103">C\#에서 특성 사용</span><span class="sxs-lookup"><span data-stu-id="ba43c-103">Use Attributes in C\#</span></span>

<span data-ttu-id="ba43c-104">특성은 선언적으로 정보를 코드와 연결하는 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ba43c-104">Attributes provide a way of associating information with code in a declarative way.</span></span> <span data-ttu-id="ba43c-105">다양한 대상에 적용할 수 있는 재사용 가능 요소를 제공할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba43c-105">They can also provide a reusable element that can be applied to a variety of targets.</span></span>

<span data-ttu-id="ba43c-106">`[Obsolete]` 특성을 고려하세요.</span><span class="sxs-lookup"><span data-stu-id="ba43c-106">Consider the `[Obsolete]` attribute.</span></span> <span data-ttu-id="ba43c-107">이 특성은 클래스, 구조체, 메서드, 생성자 등에 적용될 수 있으며</span><span class="sxs-lookup"><span data-stu-id="ba43c-107">It can be applied to classes, structs, methods, constructors, and more.</span></span> <span data-ttu-id="ba43c-108">요소가 더 이상 필요하지 않다는 사실을 _선언_합니다.</span><span class="sxs-lookup"><span data-stu-id="ba43c-108">It _declares_ that the element is obsolete.</span></span> <span data-ttu-id="ba43c-109">이 특성을 찾고 응답으로 특정 작업을 수행하는 것은 모두 C# 컴파일러가 진행합니다.</span><span class="sxs-lookup"><span data-stu-id="ba43c-109">It's then up to the C# compiler to look for this attribute, and do some action in response.</span></span>

<span data-ttu-id="ba43c-110">이 자습서에서는 코드에 특성을 추가하는 방법, 사용자 지정 특성을 만들고 사용하는 방법, .NET Core로 빌드되는 일부 특성을 사용하는 방법을 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="ba43c-110">In this tutorial, you'll be introduced to how to add attributes to your code, how to create and use your own attributes, and how to use some attributes that are built into .NET Core.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="ba43c-111">사전 요구 사항</span><span class="sxs-lookup"><span data-stu-id="ba43c-111">Prerequisites</span></span>
<span data-ttu-id="ba43c-112">.NET Core를 실행하려면 컴퓨터에 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba43c-112">You’ll need to set up your machine to run .NET core.</span></span> <span data-ttu-id="ba43c-113">[.NET Core 다운로드](https://dotnet.microsoft.com/download) 페이지에서 설치 지침을 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba43c-113">You can find the installation instructions on the [.NET Core Downloads](https://dotnet.microsoft.com/download) page.</span></span>
<span data-ttu-id="ba43c-114">Windows, Ubuntu Linux, macOS 또는 Docker 컨테이너에서 이 애플리케이션을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba43c-114">You can run this application on Windows, Ubuntu Linux, macOS or in a Docker container.</span></span>
<span data-ttu-id="ba43c-115">선호하는 코드 편집기를 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba43c-115">You’ll need to install your favorite code editor.</span></span> <span data-ttu-id="ba43c-116">아래 설명에서는 오픈 소스 플랫폼 간 편집기인 [Visual Studio Code](https://code.visualstudio.com/)를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ba43c-116">The descriptions below use [Visual Studio Code](https://code.visualstudio.com/) which is an open source, cross platform editor.</span></span> <span data-ttu-id="ba43c-117">그러나 익숙한 어떤 도구도 사용 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="ba43c-117">However, you can use whatever tools you are comfortable with.</span></span>

## <a name="create-the-application"></a><span data-ttu-id="ba43c-118">애플리케이션 만들기</span><span class="sxs-lookup"><span data-stu-id="ba43c-118">Create the Application</span></span>

<span data-ttu-id="ba43c-119">이제 모든 도구를 설치했으므로 새로운 .NET Core 애플리케이션을 만들어 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="ba43c-119">Now that you've installed all the tools, create a new .NET Core application.</span></span> <span data-ttu-id="ba43c-120">명령줄 생성기를 사용하려면 즐겨 사용하는 셸에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="ba43c-120">To use the command line generator, execute the following command in your favorite shell:</span></span>

`dotnet new console`

<span data-ttu-id="ba43c-121">이 명령은 기본 .NET Core 프로젝트 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ba43c-121">This command will create bare-bones .NET core project files.</span></span> <span data-ttu-id="ba43c-122">`dotnet restore`를 실행하여 이 프로젝트를 컴파일하는 데 필요한 종속성을 복원해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba43c-122">You will need to execute `dotnet restore` to restore the dependencies needed to compile this project.</span></span>

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

<span data-ttu-id="ba43c-123">이 프로그램을 실행하려면 `dotnet run`을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ba43c-123">To execute the program, use `dotnet run`.</span></span> <span data-ttu-id="ba43c-124">콘솔에 "Hello, World" 출력이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ba43c-124">You should see "Hello, World" output to the console.</span></span>

## <a name="how-to-add-attributes-to-code"></a><span data-ttu-id="ba43c-125">코드에 특성을 추가하는 방법</span><span class="sxs-lookup"><span data-stu-id="ba43c-125">How to add attributes to code</span></span>

<span data-ttu-id="ba43c-126">C#에서 특성은 `Attribute` 기본 클래스에서 상속되는 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="ba43c-126">In C#, attributes are classes that inherit from the `Attribute` base class.</span></span> <span data-ttu-id="ba43c-127">`Attribute`에서 상속되는 모든 클래스는 코드의 다른 부분에서 일종의 "태그"로 사용될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba43c-127">Any class that inherits from `Attribute` can be used as a sort of "tag" on other pieces of code.</span></span>
<span data-ttu-id="ba43c-128">예를 들어 `ObsoleteAttribute`라는 특성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba43c-128">For instance, there is an attribute called `ObsoleteAttribute`.</span></span> <span data-ttu-id="ba43c-129">이 특성은 코드가 더 이상 사용되지 않으며 더 이상 사용할 수 없음을 알리기 위해 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ba43c-129">This is used to signal that code is obsolete and shouldn't be used anymore.</span></span> <span data-ttu-id="ba43c-130">예를 들어 대괄호를 사용하여 클래스에 이 특성을 배치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba43c-130">You can place this attribute on a class, for instance, by using square brackets.</span></span>

[!code-csharp[Obsolete attribute example](../../../samples/snippets/csharp/tutorials/attributes/Program.cs#ObsoleteExample1)]

<span data-ttu-id="ba43c-131">이 클래스는 `ObsoleteAttribute`로 지칭되지만 코드에서 `[Obsolete]`를 사용하는 데만 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="ba43c-131">Note that while the class is called `ObsoleteAttribute`, it's only necessary to use `[Obsolete]` in the code.</span></span> <span data-ttu-id="ba43c-132">이것이 C#에서 준수하는 규칙입니다.</span><span class="sxs-lookup"><span data-stu-id="ba43c-132">This is a convention that C# follows.</span></span>
<span data-ttu-id="ba43c-133">원할 경우 전체 이름 `[ObsoleteAttribute]`를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba43c-133">You can use the full name `[ObsoleteAttribute]` if you choose.</span></span>

<span data-ttu-id="ba43c-134">클래스를 더 이상 사용되지 않는 것으로 표시할 경우 더 이상 사용되지 않는 *이유* 및/또는 대싱 사용할 *항목*에 대한 정보를 제공하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="ba43c-134">When marking a class obsolete, it's a good idea to provide some information as to *why* it's obsolete, and/or *what* to use instead.</span></span> <span data-ttu-id="ba43c-135">이 작업을 위해 Obsolete 특성에 문자열 매개 변수를 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="ba43c-135">Do this by passing a string parameter to the Obsolete attribute.</span></span>

[!code-csharp[Obsolete attribute example with parameters](../../../samples/snippets/csharp/tutorials/attributes/Program.cs#ObsoleteExample2)]

<span data-ttu-id="ba43c-136">이 문자열은 `var attr = new ObsoleteAttribute("some string")`를 작성하는 것처럼 `ObsoleteAttribute` 생성자에 인수로 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="ba43c-136">The string is being passed as an argument to an `ObsoleteAttribute` constructor, just as if you were writing `var attr = new ObsoleteAttribute("some string")`.</span></span>

<span data-ttu-id="ba43c-137">특성 생성자에 대한 매개 변수는 단순 형식/리터럴인 `bool, int, double, string, Type, enums, etc` 및 해당 형식의 배열로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="ba43c-137">Parameters to an attribute constructor are limited to simple types/literals: `bool, int, double, string, Type, enums, etc` and arrays of those types.</span></span>
<span data-ttu-id="ba43c-138">식 또는 변수는 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ba43c-138">You can not use an expression or a variable.</span></span> <span data-ttu-id="ba43c-139">위치 또는 명명된 매개 변수는 얼마든지 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba43c-139">You are free to use positional or named parameters.</span></span>

## <a name="how-to-create-your-own-attribute"></a><span data-ttu-id="ba43c-140">고유한 특성을 만드는 방법</span><span class="sxs-lookup"><span data-stu-id="ba43c-140">How to create your own attribute</span></span>

<span data-ttu-id="ba43c-141">특성을 만드는 과정은 `Attribute` 기본 클래스에서 상속하는 것만큼 간단합니다.</span><span class="sxs-lookup"><span data-stu-id="ba43c-141">Creating an attribute is as simple as inheriting from the `Attribute` base class.</span></span>

[!code-csharp[Create your own attribute](../../../samples/snippets/csharp/tutorials/attributes/Program.cs#CreateAttributeExample1)]

<span data-ttu-id="ba43c-142">위에 따라, 이제 코드베이스의 어디에서든지 `[MySpecial]`(또는 `[MySpecialAttribute]`)을 특성으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba43c-142">With the above, I can now use `[MySpecial]` (or `[MySpecialAttribute]`) as an attribute elsewhere in the code base.</span></span>

[!code-csharp[Using your own attribute](../../../samples/snippets/csharp/tutorials/attributes/Program.cs#CreateAttributeExample2)]

<span data-ttu-id="ba43c-143">`ObsoleteAttribute` 트리거 같은 .NET 기본 클래스 라이브러리의 특성은 컴파일러 내에 특정 동작을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="ba43c-143">Attributes in the .NET base class library like `ObsoleteAttribute` trigger certain behaviors within the compiler.</span></span> <span data-ttu-id="ba43c-144">그러나 만드는 특성은 메타데이터의 역할만 수행하며 특성 클래스 내의 코드는 실행되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ba43c-144">However, any attribute you create acts only as metadata, and doesn't result in any code within the attribute class being executed.</span></span> <span data-ttu-id="ba43c-145">코드의 임의 위치에서 해당 메타데이터에 대해 작업을 수행할 수 있습니다(이 자습서의 뒷부분에 좀 더 자세히 설명되어 있음).</span><span class="sxs-lookup"><span data-stu-id="ba43c-145">It's up to you to act on that metadata elsewhere in your code (more on that later in the tutorial).</span></span>

<span data-ttu-id="ba43c-146">여기에는 확인해 볼만한 '과제'가 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="ba43c-146">There is a 'gotcha' here to watch out for.</span></span> <span data-ttu-id="ba43c-147">위에서 설명한 것처럼 특성을 사용할 때는 특정 형식만 인수로 전달되도록 허용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ba43c-147">As mentioned above, only certain types are allowed to be passed as arguments when using attributes.</span></span> <span data-ttu-id="ba43c-148">그러나 특성 유형을 만들 때 C# 컴파일러는 사용자가 해당 매개 변수를 만들지 못하게 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ba43c-148">However, when creating an attribute type, the C# compiler won't stop you from creating those parameters.</span></span> <span data-ttu-id="ba43c-149">아래 예제에서는 적절히 컴파일을 수행하는 생성자로 특성을 만들었습니다.</span><span class="sxs-lookup"><span data-stu-id="ba43c-149">In the below example, I've created an attribute with a constructor that compiles just fine.</span></span>

[!code-csharp[Valid constructor used in an attribute](../../../samples/snippets/csharp/tutorials/attributes/Program.cs#AttributeGothca1)]

<span data-ttu-id="ba43c-150">그러나 이 생성자를 특성 구문에서 사용할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ba43c-150">However, you will be unable to use this constructor with attribute syntax.</span></span>

[!code-csharp[Invalid attempt to use the attribute constructor](../../../samples/snippets/csharp/tutorials/attributes/Program.cs#AttributeGotcha2)]

<span data-ttu-id="ba43c-151">위에서는 `Attribute constructor parameter 'myClass' has type 'Foo', which is not a valid attribute parameter type`과 같은 컴파일러 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="ba43c-151">The above will cause a compiler error like `Attribute constructor parameter 'myClass' has type 'Foo', which is not a valid attribute parameter type`</span></span>

## <a name="how-to-restrict-attribute-usage"></a><span data-ttu-id="ba43c-152">특성 사용을 제한하는 방법</span><span class="sxs-lookup"><span data-stu-id="ba43c-152">How to restrict attribute usage</span></span>

<span data-ttu-id="ba43c-153">특성은 다양한 "대상"에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba43c-153">Attributes can be used on a number of "targets".</span></span> <span data-ttu-id="ba43c-154">위의 예제에서는 클래스에 대한 특성만 표시하지만 다음에도 사용될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba43c-154">The above examples show them on classes, but they can also be used on:</span></span>

* <span data-ttu-id="ba43c-155">Assembly</span><span class="sxs-lookup"><span data-stu-id="ba43c-155">Assembly</span></span>
* <span data-ttu-id="ba43c-156">클래스</span><span class="sxs-lookup"><span data-stu-id="ba43c-156">Class</span></span>
* <span data-ttu-id="ba43c-157">생성자</span><span class="sxs-lookup"><span data-stu-id="ba43c-157">Constructor</span></span>
* <span data-ttu-id="ba43c-158">대리자</span><span class="sxs-lookup"><span data-stu-id="ba43c-158">Delegate</span></span>
* <span data-ttu-id="ba43c-159">Enum</span><span class="sxs-lookup"><span data-stu-id="ba43c-159">Enum</span></span>
* <span data-ttu-id="ba43c-160">이벤트</span><span class="sxs-lookup"><span data-stu-id="ba43c-160">Event</span></span>
* <span data-ttu-id="ba43c-161">필드</span><span class="sxs-lookup"><span data-stu-id="ba43c-161">Field</span></span>
* <span data-ttu-id="ba43c-162">GenericParameter</span><span class="sxs-lookup"><span data-stu-id="ba43c-162">GenericParameter</span></span>
* <span data-ttu-id="ba43c-163">인터페이스</span><span class="sxs-lookup"><span data-stu-id="ba43c-163">Interface</span></span>
* <span data-ttu-id="ba43c-164">메서드</span><span class="sxs-lookup"><span data-stu-id="ba43c-164">Method</span></span>
* <span data-ttu-id="ba43c-165">Module</span><span class="sxs-lookup"><span data-stu-id="ba43c-165">Module</span></span>
* <span data-ttu-id="ba43c-166">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ba43c-166">Parameter</span></span>
* <span data-ttu-id="ba43c-167">속성</span><span class="sxs-lookup"><span data-stu-id="ba43c-167">Property</span></span>
* <span data-ttu-id="ba43c-168">ReturnValue</span><span class="sxs-lookup"><span data-stu-id="ba43c-168">ReturnValue</span></span>
* <span data-ttu-id="ba43c-169">구조체</span><span class="sxs-lookup"><span data-stu-id="ba43c-169">Struct</span></span>

<span data-ttu-id="ba43c-170">특성 클래스를 만들 때 기본적으로 C#은 허용 가능한 특성 대상 중 하나에 대해 해당 특성을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba43c-170">When you create an attribute class, by default, C# will allow you to use that attribute on any of the possible attribute targets.</span></span> <span data-ttu-id="ba43c-171">특성을 특정 대상으로 제한하려는 경우 특성 클래스에 대해 `AttributeUsageAttribute`를 사용하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ba43c-171">If you want to restrict your attribute to certain targets, you can do so by using the `AttributeUsageAttribute` on your attribute class.</span></span> <span data-ttu-id="ba43c-172">맞습니다. 특성에 대한 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="ba43c-172">That's right, an attribute on an attribute!</span></span>

[!code-csharp[Using your own attribute](../../../samples/snippets/csharp/tutorials/attributes/Program.cs#AttributeUsageExample1)]

<span data-ttu-id="ba43c-173">클래스 또는 구조체 이외의 항목에 대해 위 특성을 적용하려고 하면 `Attribute 'MyAttributeForClassAndStructOnly' is not valid on this declaration type. It is only valid on 'class, struct' declarations`와 같은 컴파일러 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="ba43c-173">If you attempt to put the above attribute on something that's not a class or a struct, you will get a compiler error like `Attribute 'MyAttributeForClassAndStructOnly' is not valid on this declaration type. It is only valid on 'class, struct' declarations`</span></span>

[!code-csharp[Using your own attribute](../../../samples/snippets/csharp/tutorials/attributes/Program.cs#AttributeUsageExample2)]

## <a name="how-to-use-attributes-attached-to-a-code-element"></a><span data-ttu-id="ba43c-174">코드 요소에 연결된 특성을 사용하는 방법</span><span class="sxs-lookup"><span data-stu-id="ba43c-174">How to use attributes attached to a code element</span></span>

<span data-ttu-id="ba43c-175">특성는 메타데이터로 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="ba43c-175">Attributes act as metadata.</span></span> <span data-ttu-id="ba43c-176">외부 영향이 없으면 어떤 작업도 수행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ba43c-176">Without some outward force, they won't actually do anything.</span></span>

<span data-ttu-id="ba43c-177">특성을 찾아 작업을 수행하려면 일반적으로 [리플렉션](../programming-guide/concepts/reflection.md)이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="ba43c-177">To find and act on attributes, [Reflection](../programming-guide/concepts/reflection.md) is generally needed.</span></span> <span data-ttu-id="ba43c-178">이 자습서에서는 리플렉션을 자세히 다루지 않겠지만, 기본 개념은 리플렉션을 사용하면 다른 코드를 검사하는 코드를 C#에서 작성할 수 있다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ba43c-178">I won't cover Reflection in-depth in this tutorial, but the basic idea is that Reflection allows you to write code in C# that examines other code.</span></span>

<span data-ttu-id="ba43c-179">예를 들어 리플렉션을 사용하여 클래스에 대한 정보(코드 헤드에 `using System.Reflection;` 추가)를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba43c-179">For instance, you can use Reflection to get information about a class(add `using System.Reflection;` at the head of your code):</span></span>

[!code-csharp[Getting type information with Reflection](../../../samples/snippets/csharp/tutorials/attributes/Program.cs#ReflectionExample1)]

<span data-ttu-id="ba43c-180">다음과 같이 출력됩니다.`The assembly qualified name of MyClass is ConsoleApplication.MyClass, attributes, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null`</span><span class="sxs-lookup"><span data-stu-id="ba43c-180">That will print out something like: `The assembly qualified name of MyClass is ConsoleApplication.MyClass, attributes, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null`</span></span>

<span data-ttu-id="ba43c-181">`TypeInfo` 개체(또는 `MemberInfo`, `FieldInfo` 등)가 있으면 `GetCustomAttributes` 메서드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba43c-181">Once you have a `TypeInfo` object (or a `MemberInfo`, `FieldInfo`, etc), you can use the `GetCustomAttributes` method.</span></span> <span data-ttu-id="ba43c-182">그러면 `Attribute` 개체 컬렉션이 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="ba43c-182">This will return a collection of `Attribute` objects.</span></span>
<span data-ttu-id="ba43c-183">`GetCustomAttribute`를 사용하고 특성 유형을 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba43c-183">You can also use `GetCustomAttribute` and specify an Attribute type.</span></span>

<span data-ttu-id="ba43c-184">`MyClass`의 `MemberInfo` 인스턴스에 대해 `GetCustomAttributes`를 사용하는 예제는 다음과 같습니다(앞에서 살펴본 `[Obsolete]` 특성을 포함하는 예제).</span><span class="sxs-lookup"><span data-stu-id="ba43c-184">Here's an example of using `GetCustomAttributes` on a `MemberInfo` instance for `MyClass` (which we saw earlier has an `[Obsolete]` attribute on it).</span></span>

[!code-csharp[Getting type information with Reflection](../../../samples/snippets/csharp/tutorials/attributes/Program.cs#ReflectionExample2)]

<span data-ttu-id="ba43c-185">해당 내용은 콘솔에 `Attribute on MyClass: ObsoleteAttribute`와 같이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ba43c-185">That will print to console: `Attribute on MyClass: ObsoleteAttribute`.</span></span> <span data-ttu-id="ba43c-186">`MyClass`에 다른 특성을 추가해 보세요.</span><span class="sxs-lookup"><span data-stu-id="ba43c-186">Try adding other attributes to `MyClass`.</span></span>

<span data-ttu-id="ba43c-187">이러한 `Attribute` 개체가 지연되어 인스턴스화되는 것에 유의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba43c-187">It's important to note that these `Attribute` objects are instantiated lazily.</span></span> <span data-ttu-id="ba43c-188">즉, `GetCustomAttribute` 또는 `GetCustomAttributes`를 사용해야만 인스턴스화됩니다.</span><span class="sxs-lookup"><span data-stu-id="ba43c-188">That is, they won't be instantiated until you use `GetCustomAttribute` or `GetCustomAttributes`.</span></span>
<span data-ttu-id="ba43c-189">또한 매번 인스턴스화되기도 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba43c-189">They are also instantiated each time.</span></span> <span data-ttu-id="ba43c-190">`GetCustomAttributes`를 연속해서 2번 호출하면 2개의 다른 `ObsoleteAttribute` 인스턴스가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="ba43c-190">Calling `GetCustomAttributes` twice in a row will return two different instances of `ObsoleteAttribute`.</span></span>

## <a name="common-attributes-in-the-base-class-library-bcl"></a><span data-ttu-id="ba43c-191">BCL(기본 클래스 라이브러리)의 공통 특성</span><span class="sxs-lookup"><span data-stu-id="ba43c-191">Common attributes in the base class library (BCL)</span></span>

<span data-ttu-id="ba43c-192">특성은 많은 도구 및 프레임워크에서 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ba43c-192">Attributes are used by many tools and frameworks.</span></span> <span data-ttu-id="ba43c-193">NUnit은 NUnit Test Runner에서 사용되는 `[Test]` 및 `[TestFixture]` 같은 특성을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ba43c-193">NUnit uses attributes like `[Test]` and `[TestFixture]` that are used by the NUnit test runner.</span></span> <span data-ttu-id="ba43c-194">ASP.NET MVC는 `[Authorize]`와 같은 특성을 사용하고 MVC 작업에 대해 크로스 커팅(Cross-Cutting) 문제를 해결하기 위한 작업 필터 프레임워크를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ba43c-194">ASP.NET MVC uses attributes like `[Authorize]` and provides an action filter framework to perform cross-cutting concerns on MVC actions.</span></span> <span data-ttu-id="ba43c-195">[PostSharp](https://www.postsharp.net)은 특성 구문을 사용하여 C#을 사용한 AOP(Aspect-Oriented Programming)를 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="ba43c-195">[PostSharp](https://www.postsharp.net) uses the attribute syntax to allow aspect-oriented programming in C#.</span></span>

<span data-ttu-id="ba43c-196">.NET Core 기본 클래스 라이브러리에 기본 제공되는 몇 가지 유의할 만한 특성은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ba43c-196">Here are a few notable attributes built into the .NET Core base class libraries:</span></span>

* <span data-ttu-id="ba43c-197">`[Obsolete]`.</span><span class="sxs-lookup"><span data-stu-id="ba43c-197">`[Obsolete]`.</span></span> <span data-ttu-id="ba43c-198">이 특성은 위 예제에서 사용되었으며 `System` 네임스페이스에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba43c-198">This one was used in the above examples, and it lives in the `System` namespace.</span></span> <span data-ttu-id="ba43c-199">기본 코드를 변경하는 방법에 대해 선언적 설명서를 제공하는 것이 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="ba43c-199">It is useful to provide declarative documentation about a changing code base.</span></span> <span data-ttu-id="ba43c-200">메시지는 문자열의 형태로 제공될 수 있으며 다른 부울 매개 변수가 컴파일러 경고를 컴파일러 오류로 에스컬레이션하는 데 사용될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba43c-200">A message can be provided in the form of a string, and another boolean parameter can be used to escalate from a compiler warning to a compiler error.</span></span>

* <span data-ttu-id="ba43c-201">`[Conditional]`.</span><span class="sxs-lookup"><span data-stu-id="ba43c-201">`[Conditional]`.</span></span> <span data-ttu-id="ba43c-202">이 특성은 `System.Diagnostics` 네임스페이스에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba43c-202">This attribute is in the `System.Diagnostics` namespace.</span></span> <span data-ttu-id="ba43c-203">이 특성은 메서드(또는 특성 클래스)에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba43c-203">This attribute can be applied to methods (or attribute classes).</span></span> <span data-ttu-id="ba43c-204">생성자에는 문자열을 전달해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba43c-204">You must pass a string to the constructor.</span></span>
<span data-ttu-id="ba43c-205">해당 문자열이 `#define` 지시문과 일치하지 않는 경우 해당 메서드에 대한 호출(메서드 자체는 아님)이 C# 컴파일러에 의해 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="ba43c-205">If that string doesn't match a `#define` directive, then any calls to that method (but not the method itself) will be removed by the C# compiler.</span></span> <span data-ttu-id="ba43c-206">일반적으로 이 특성은 디버깅(진단) 목적으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ba43c-206">Typically this is used for debugging (diagnostics) purposes.</span></span>

* <span data-ttu-id="ba43c-207">`[CallerMemberName]`.</span><span class="sxs-lookup"><span data-stu-id="ba43c-207">`[CallerMemberName]`.</span></span> <span data-ttu-id="ba43c-208">이 특성은 매개 변수에 사용될 수 있으며 `System.Runtime.CompilerServices` 네임스페이스에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba43c-208">This attribute can be used on parameters, and lives in the `System.Runtime.CompilerServices` namespace.</span></span> <span data-ttu-id="ba43c-209">다른 메서드를 호출하는 메서드의 이름을 삽입하는 데 사용되는 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="ba43c-209">This is an attribute that is used to inject the name of the method that is calling another method.</span></span> <span data-ttu-id="ba43c-210">일반적으로 다양한 UI 프레임워크에서 INotifyPropertyChanged를 구현하는 경우 '매직 문자열'을 제거하는 방법으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ba43c-210">This is typically used as a way to eliminate 'magic strings' when implementing INotifyPropertyChanged in various UI frameworks.</span></span> <span data-ttu-id="ba43c-211">예제:</span><span class="sxs-lookup"><span data-stu-id="ba43c-211">As an example:</span></span>

[!code-csharp[Using CallerMemberName when implementing INotifyPropertyChanged](../../../samples/snippets/csharp/tutorials/attributes/Program.cs#CallerMemberName1)]

<span data-ttu-id="ba43c-212">위의 코드에서는 리터럴 `"Name"` 문자열이 없어도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ba43c-212">In the above code, you don't have to have a literal `"Name"` string.</span></span> <span data-ttu-id="ba43c-213">이 경우 입력 관련 버그가 방지되며 좀 더 매끄러운 리팩터링/이름 바꾸기가 가능해집니다.</span><span class="sxs-lookup"><span data-stu-id="ba43c-213">This can help prevent typo-related bugs and also makes for smoother refactoring/renaming.</span></span>

## <a name="summary"></a><span data-ttu-id="ba43c-214">요약</span><span class="sxs-lookup"><span data-stu-id="ba43c-214">Summary</span></span>

<span data-ttu-id="ba43c-215">특성은 C#에 선언적 기능을 제공하지만 코드의 메타데이터 형식이며 단독으로 동작하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ba43c-215">Attributes bring declarative power to C#, but they are a meta-data form of code and don't act by themselves.</span></span>
