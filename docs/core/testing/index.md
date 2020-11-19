---
title: .NET에서 테스트
description: 이 문서에서는 .NET에서 테스트하기 위한 테스트 개념, 용어 및 도구에 대한 간략한 개요를 제공합니다.
author: IEvangelist
ms.author: dapine
ms.date: 10/19/2020
ms.openlocfilehash: 137a8f4e3bc9e3be529d5034c233d283cf158b31
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/18/2020
ms.locfileid: "94824859"
---
# <a name="testing-in-net"></a><span data-ttu-id="09ebb-103">.NET에서 테스트</span><span class="sxs-lookup"><span data-stu-id="09ebb-103">Testing in .NET</span></span>

<span data-ttu-id="09ebb-104">이 문서에서는 테스트 개념을 소개하고 다양한 종류의 테스트를 사용하여 코드의 유효성을 검사하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="09ebb-104">This article introduces the concept of testing, and illustrates how different kinds of tests can be used to validate code.</span></span> <span data-ttu-id="09ebb-105">[.NET CLI](#net-cli) 또는 [IDE(통합 개발 환경)](#ide)와 같이 .NET 애플리케이션을 테스트하는 데 사용할 수 있는 다양한 도구가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09ebb-105">There are various tools available for testing .NET applications, such as the [.NET CLI](#net-cli) or [Integrated Development Environments (IDEs)](#ide).</span></span>

## <a name="test-types"></a><span data-ttu-id="09ebb-106">테스트 형식</span><span class="sxs-lookup"><span data-stu-id="09ebb-106">Test types</span></span>

<span data-ttu-id="09ebb-107">자동화된 테스트를 사용하는 것이 애플리케이션 코드가 작성자가 의도한 대로 수행되는지 확인하는 좋은 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="09ebb-107">Having automated tests is a great way to ensure that application code does what its authors intend it to do.</span></span> <span data-ttu-id="09ebb-108">이 문서에서는 단위 테스트, 통합 테스트 및 부하 테스트에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="09ebb-108">This article covers unit tests, integration tests, and load tests.</span></span>

### <a name="unit-tests"></a><span data-ttu-id="09ebb-109">단위 테스트</span><span class="sxs-lookup"><span data-stu-id="09ebb-109">Unit tests</span></span>

<span data-ttu-id="09ebb-110">*단위 테스트* 는 "작업 단위"라고도 하는 개별 소프트웨어 구성 요소 또는 메서드를 실행하는 테스트입니다.</span><span class="sxs-lookup"><span data-stu-id="09ebb-110">A *unit test* is a test that exercises individual software components or methods, also known as "unit of work".</span></span> <span data-ttu-id="09ebb-111">단위 테스트는 개발자의 제어 내에서만 코드를 테스트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="09ebb-111">Unit tests should only test code within the developer's control.</span></span> <span data-ttu-id="09ebb-112">인프라 문제를 테스트하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="09ebb-112">They do not test infrastructure concerns.</span></span> <span data-ttu-id="09ebb-113">인프라 문제에는 데이터베이스, 파일 시스템 및 네트워크 리소스와의 상호 작용이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="09ebb-113">Infrastructure concerns include interacting with databases, file systems, and network resources.</span></span>

<span data-ttu-id="09ebb-114">단위 테스트를 만드는 방법에 대한 자세한 내용은 [테스트 도구](#testing-tools)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="09ebb-114">For more information on creating unit tests, see [Testing tools](#testing-tools).</span></span>

### <a name="integration-tests"></a><span data-ttu-id="09ebb-115">통합 테스트</span><span class="sxs-lookup"><span data-stu-id="09ebb-115">Integration tests</span></span>

<span data-ttu-id="09ebb-116">*통합 테스트* 는 "통합"이라고도 하는 둘 이상의 소프트웨어 구성 요소가 함께 작동하는 기능을 실행한다는 점에서 단위 테스트와 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="09ebb-116">An *integration test* differs from a unit test in that it exercises two or more software components' ability to function together, also known as their "integration."</span></span> <span data-ttu-id="09ebb-117">이러한 테스트는 테스트 중인 시스템의 광범위한 스펙트럼에서 작동하는 반면 단위 테스트는 개별 구성 요소에 중점을 둡니다.</span><span class="sxs-lookup"><span data-stu-id="09ebb-117">These tests operate on a broader spectrum of the system under test, whereas unit tests focus on individual components.</span></span> <span data-ttu-id="09ebb-118">종종 통합 테스트에는 인프라 문제가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="09ebb-118">Often, integration tests do include infrastructure concerns.</span></span>

### <a name="load-tests"></a><span data-ttu-id="09ebb-119">부하 테스트</span><span class="sxs-lookup"><span data-stu-id="09ebb-119">Load tests</span></span>

<span data-ttu-id="09ebb-120">*부하 테스트* 는 시스템에서 지정된 부하를 처리할 수 있는지 여부(예: 애플리케이션을 사용하는 동시 사용자 수와 상호 작용 반응을 처리하는 앱의 기능)를 결정하는 것을 목표로 합니다.</span><span class="sxs-lookup"><span data-stu-id="09ebb-120">A *load test* aims to determine whether or not a system can handle a specified load, for example, the number of concurrent users using an application and the app's ability to handle interactions responsively.</span></span> <span data-ttu-id="09ebb-121">웹 애플리케이션의 부하 테스트에 대한 자세한 내용은 [ASP.NET Core 부하/스트레스 테스트](/aspnet/core/test/load-tests)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="09ebb-121">For more information on load testing of web applications, see [ASP.NET Core load/stress testing](/aspnet/core/test/load-tests).</span></span>

## <a name="test-considerations"></a><span data-ttu-id="09ebb-122">테스트 고려 사항</span><span class="sxs-lookup"><span data-stu-id="09ebb-122">Test considerations</span></span>

<span data-ttu-id="09ebb-123">테스트를 작성하는 [모범 사례](unit-testing-best-practices.md)가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09ebb-123">Keep in mind there are [best practices](unit-testing-best-practices.md) for writing tests.</span></span> <span data-ttu-id="09ebb-124">예를 들어 [TDD(테스트 기반 개발)](https://deviq.com/test-driven-development)는 확인하려는 코드보다 단위 테스트를 먼저 작성한 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="09ebb-124">For example, [Test Driven Development (TDD)](https://deviq.com/test-driven-development) is when a unit test is written before the code it's meant to check.</span></span> <span data-ttu-id="09ebb-125">TDD는 책을 작성하기 전에 책에 대한 개요를 만드는 것과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="09ebb-125">TDD is like creating an outline for a book before you write it.</span></span> <span data-ttu-id="09ebb-126">이 기능을 통해 개발자가 간단하고 읽을 수 있고 효율적인 코드를 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09ebb-126">It is meant to help developers write simpler, more readable, and efficient code.</span></span>

## <a name="testing-tools"></a><span data-ttu-id="09ebb-127">테스트 도구</span><span class="sxs-lookup"><span data-stu-id="09ebb-127">Testing tools</span></span>

<span data-ttu-id="09ebb-128">.NET은 다중 언어 개발 플랫폼이며, [C#](../../csharp/index.yml), [F#](../../fsharp/index.yml) 및 [Visual Basic](../../visual-basic/index.yml)에 대한 다양한 테스트 형식을 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09ebb-128">.NET is a multi-language development platform, and you can write various test types for [C#](../../csharp/index.yml), [F#](../../fsharp/index.yml), and [Visual Basic](../../visual-basic/index.yml).</span></span> <span data-ttu-id="09ebb-129">이러한 각 언어에 대해 여러 테스트 프레임워크 중에서 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09ebb-129">For each of these languages, you can choose between several test frameworks.</span></span>

### <a name="xunit"></a><span data-ttu-id="09ebb-130">xUnit</span><span class="sxs-lookup"><span data-stu-id="09ebb-130">xUnit</span></span>

<span data-ttu-id="09ebb-131">[xUnit](https://xunit.net)은 무료로 제공되는 .NET용 오픈 소스 커뮤니티 중심 유닛 테스트 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="09ebb-131">[xUnit](https://xunit.net) is a free, open source, community-focused unit testing tool for .NET.</span></span> <span data-ttu-id="09ebb-132">NUnit v2의 원본 발명가가 작성한 xUnit.net은 .NET 앱을 단위 테스트하기 위한 최신 기술입니다.</span><span class="sxs-lookup"><span data-stu-id="09ebb-132">Written by the original inventor of NUnit v2, xUnit.net is the latest technology for unit testing .NET apps.</span></span> <span data-ttu-id="09ebb-133">xUnit.net은 ReSharper, CodeRush, TestDriven.NET 및 [Xamarin](https://dotnet.microsoft.com/apps/xamarin)에서 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="09ebb-133">xUnit.net works with ReSharper, CodeRush, TestDriven.NET, and [Xamarin](https://dotnet.microsoft.com/apps/xamarin).</span></span> <span data-ttu-id="09ebb-134">[.NET Foundation](https://dotnetfoundation.org)의 프로젝트이며, 해당 사용 규정에 따라 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="09ebb-134">It is a project of the [.NET Foundation](https://dotnetfoundation.org) and operates under their code of conduct.</span></span>

<span data-ttu-id="09ebb-135">자세한 내용은 다음 자료를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="09ebb-135">For more information, see the following resources:</span></span>

- [<span data-ttu-id="09ebb-136">C#을 사용한 단위 테스트</span><span class="sxs-lookup"><span data-stu-id="09ebb-136">Unit testing with C#</span></span>](unit-testing-with-dotnet-test.md)
- [<span data-ttu-id="09ebb-137">F#을 사용한 단위 테스트</span><span class="sxs-lookup"><span data-stu-id="09ebb-137">Unit testing with F#</span></span>](unit-testing-fsharp-with-dotnet-test.md)
- [<span data-ttu-id="09ebb-138">Visual Basic을 사용한 단위 테스트</span><span class="sxs-lookup"><span data-stu-id="09ebb-138">Unit testing with Visual Basic</span></span>](unit-testing-visual-basic-with-dotnet-test.md)

### <a name="nunit"></a><span data-ttu-id="09ebb-139">NUnit</span><span class="sxs-lookup"><span data-stu-id="09ebb-139">NUnit</span></span>

<span data-ttu-id="09ebb-140">[NUnit](https://nunit.org)은 모든 .NET 언어에 대한 단위 테스트 프레임워크입니다.</span><span class="sxs-lookup"><span data-stu-id="09ebb-140">[NUnit](https://nunit.org) is a unit-testing framework for all .NET languages.</span></span> <span data-ttu-id="09ebb-141">처음에 JUnit에서 이식된 현재 프로덕션 릴리스는 다양한 .NET 플랫폼에 대한 많은 새로운 기능과 지원으로 다시 작성되었습니다.</span><span class="sxs-lookup"><span data-stu-id="09ebb-141">Initially ported from JUnit, the current production release has been rewritten with many new features and support for a wide range of .NET platforms.</span></span> <span data-ttu-id="09ebb-142">[.NET Foundation](https://dotnetfoundation.org)의 프로젝트입니다.</span><span class="sxs-lookup"><span data-stu-id="09ebb-142">It is a project of the [.NET Foundation](https://dotnetfoundation.org).</span></span>

<span data-ttu-id="09ebb-143">자세한 내용은 다음 자료를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="09ebb-143">For more information, see the following resources:</span></span>

- [<span data-ttu-id="09ebb-144">C#을 사용한 단위 테스트</span><span class="sxs-lookup"><span data-stu-id="09ebb-144">Unit testing with C#</span></span>](unit-testing-with-nunit.md)
- [<span data-ttu-id="09ebb-145">F#을 사용한 단위 테스트</span><span class="sxs-lookup"><span data-stu-id="09ebb-145">Unit testing with F#</span></span>](unit-testing-fsharp-with-nunit.md)
- [<span data-ttu-id="09ebb-146">Visual Basic을 사용한 단위 테스트</span><span class="sxs-lookup"><span data-stu-id="09ebb-146">Unit testing with Visual Basic</span></span>](unit-testing-visual-basic-with-nunit.md)

### <a name="mstest"></a><span data-ttu-id="09ebb-147">MSTest</span><span class="sxs-lookup"><span data-stu-id="09ebb-147">MSTest</span></span>

<span data-ttu-id="09ebb-148">[MSTest](https://github.com/Microsoft/testfx-docs)는 모든 .NET 언어에 대한 Microsoft 테스트 프레임워크입니다.</span><span class="sxs-lookup"><span data-stu-id="09ebb-148">[MSTest](https://github.com/Microsoft/testfx-docs) is the Microsoft test framework for all .NET languages.</span></span> <span data-ttu-id="09ebb-149">확장 가능하며 .NET CLI와 Visual Studio 모두에서 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="09ebb-149">It's extensible and works with both .NET CLI and Visual Studio.</span></span> <span data-ttu-id="09ebb-150">자세한 내용은 다음 자료를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="09ebb-150">For more information, see the following resources:</span></span>

- [<span data-ttu-id="09ebb-151">C#을 사용한 단위 테스트</span><span class="sxs-lookup"><span data-stu-id="09ebb-151">Unit testing with C#</span></span>](unit-testing-with-mstest.md)
- [<span data-ttu-id="09ebb-152">F#을 사용한 단위 테스트</span><span class="sxs-lookup"><span data-stu-id="09ebb-152">Unit testing with F#</span></span>](unit-testing-fsharp-with-mstest.md)
- [<span data-ttu-id="09ebb-153">Visual Basic을 사용한 단위 테스트</span><span class="sxs-lookup"><span data-stu-id="09ebb-153">Unit testing with Visual Basic</span></span>](unit-testing-visual-basic-with-mstest.md)

### <a name="net-cli"></a><span data-ttu-id="09ebb-154">.NET CLI</span><span class="sxs-lookup"><span data-stu-id="09ebb-154">.NET CLI</span></span>

<span data-ttu-id="09ebb-155">[dotnet test](../tools/dotnet-test.md) 명령을 사용하여 [.NET CLI](../tools/index.md)에서 솔루션 단위 테스트를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09ebb-155">You can run a solutions unit tests from the [.NET CLI](../tools/index.md), with the [dotnet test](../tools/dotnet-test.md) command.</span></span> <span data-ttu-id="09ebb-156">.NET CLI는 [IDE(통합 개발 환경)](#ide)에서 사용자 인터페이스를 통해 사용할 수 있는 대부분의 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="09ebb-156">The .NET CLI exposes a majority of the functionality that [Integrated Development Environments (IDEs)](#ide) make available through user interfaces.</span></span> <span data-ttu-id="09ebb-157">.NET CLI는 교차 플랫폼이며 연속 통합 및 지속적인 전달 파이프라인의 일부로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09ebb-157">The .NET CLI is cross-platform and available to use as part of continuous integration and delivery pipelines.</span></span> <span data-ttu-id="09ebb-158">.NET CLI는 일반적인 작업을 자동화하기 위해 스크립팅된 프로세스와 함께 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="09ebb-158">The .NET CLI is used with scripted processes to automate common tasks.</span></span>

### <a name="ide"></a><span data-ttu-id="09ebb-159">IDE</span><span class="sxs-lookup"><span data-stu-id="09ebb-159">IDE</span></span>

<span data-ttu-id="09ebb-160">Visual Studio, Mac용 Visual Studio 또는 Visual Studio Code 사용 여부와 상관없이 기능 테스트를 위한 그래픽 사용자 인터페이스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09ebb-160">Whether you're using Visual Studio, Visual Studio for Mac, or Visual Studio Code, there are graphical user interfaces for testing functionality.</span></span> <span data-ttu-id="09ebb-161">CLI보다 IDE에서 더 많은 기능을 사용할 수 있습니다(예: [Live Unit Testing](/visualstudio/test/live-unit-testing)).</span><span class="sxs-lookup"><span data-stu-id="09ebb-161">There are more features available to IDEs than the CLI, for example [Live Unit Testing](/visualstudio/test/live-unit-testing).</span></span> <span data-ttu-id="09ebb-162">자세한 내용은 [Visual Studio를 사용하는 테스트 포함 및 제외](/visualstudio/test/live-unit-testing#include-and-exclude-test-projects-and-test-methods)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="09ebb-162">For more information, see [Including and excluding tests with Visual Studio](/visualstudio/test/live-unit-testing#include-and-exclude-test-projects-and-test-methods).</span></span>

## <a name="see-also"></a><span data-ttu-id="09ebb-163">참고 항목</span><span class="sxs-lookup"><span data-stu-id="09ebb-163">See also</span></span>

<span data-ttu-id="09ebb-164">자세한 내용은 다음 아티클을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="09ebb-164">For more information, see the following articles:</span></span>

- [<span data-ttu-id="09ebb-165">.NET을 사용한 단위 테스트 모범 사례</span><span class="sxs-lookup"><span data-stu-id="09ebb-165">Unit testing best practices with .NET</span></span>](unit-testing-best-practices.md)
- [<span data-ttu-id="09ebb-166">ASP.NET Core의 통합 테스트</span><span class="sxs-lookup"><span data-stu-id="09ebb-166">Integration tests in ASP.NET Core</span></span>](/aspnet/core/test/integration-tests#test-app-prerequisites)
- [<span data-ttu-id="09ebb-167">선택적 단위 테스트 실행</span><span class="sxs-lookup"><span data-stu-id="09ebb-167">Running selective unit tests</span></span>](selective-unit-tests.md)
- [<span data-ttu-id="09ebb-168">유닛 테스트에 코드 검사 사용</span><span class="sxs-lookup"><span data-stu-id="09ebb-168">Use code coverage for unit testing</span></span>](unit-testing-code-coverage.md)
