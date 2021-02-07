---
description: '자세한 정보: .NET 네이티브로 앱 컴파일'
title: .NET 네이티브로 앱 컴파일
ms.date: 03/30/2017
helpviewer_keywords:
- native compilation
- .NET and native code
- compilation with .NET Native
- .NET Native
- C# and native compilation
ms.assetid: 47cd5648-9469-4b1d-804c-43cc04384045
ms.openlocfilehash: 2626daf17fda751edd7915f15fd4b68ffb623dff
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99747662"
---
# <a name="compiling-apps-with-net-native"></a><span data-ttu-id="3bc0b-103">.NET 네이티브로 앱 컴파일</span><span class="sxs-lookup"><span data-stu-id="3bc0b-103">Compiling Apps with .NET Native</span></span>

<span data-ttu-id="3bc0b-104">.NET 네이티브는 Visual Studio 2015 이상 버전에 포함 된 Windows 앱을 빌드하고 배포 하기 위한 미리 컴파일 기술입니다.</span><span class="sxs-lookup"><span data-stu-id="3bc0b-104">.NET Native is a precompilation technology for building and deploying Windows apps that is included with Visual Studio 2015 and later versions.</span></span> <span data-ttu-id="3bc0b-105">관리 코드(C# 또는 Visual Basic)로 작성되었으며 .NET Framework 및 Windows 10의 대상을 네이티브 코드로 지정하는 앱의 릴리스 버전을 자동으로 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="3bc0b-105">It automatically compiles the release version of apps that are written in managed code (C# or Visual Basic) and that target the .NET Framework and Windows 10 to native code.</span></span>

<span data-ttu-id="3bc0b-106">일반적으로 .NET Framework를 대상으로 하는 앱은 IL(중간 언어)로 컴파일됩니다.</span><span class="sxs-lookup"><span data-stu-id="3bc0b-106">Typically, apps that target the .NET Framework are compiled to intermediate language (IL).</span></span> <span data-ttu-id="3bc0b-107">런타임에 JIT(Just-In-Time) 컴파일러가 IL을 네이티브 코드로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="3bc0b-107">At run time, the just-in-time (JIT) compiler translates the IL to native code.</span></span> <span data-ttu-id="3bc0b-108">반면, .NET 네이티브는 Windows 앱을 네이티브 코드로 직접 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="3bc0b-108">In contrast, .NET Native compiles Windows apps directly to native code.</span></span> <span data-ttu-id="3bc0b-109">이러한 방식이 개발자에게 의미하는 바는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="3bc0b-109">For developers, this means:</span></span>

- <span data-ttu-id="3bc0b-110">앱이 네이티브 코드의 성능을 향상 합니다.</span><span class="sxs-lookup"><span data-stu-id="3bc0b-110">Your apps feature the performance of native code.</span></span> <span data-ttu-id="3bc0b-111">일반적으로 성능은 먼저 IL로 컴파일된 다음 JIT 컴파일러에서 네이티브 코드로 컴파일되는 코드 보다 더 우수 합니다.</span><span class="sxs-lookup"><span data-stu-id="3bc0b-111">Usually, performance will be superior to code that is first compiled to IL and then compiled to native code by the JIT compiler.</span></span>

- <span data-ttu-id="3bc0b-112">C# 또는 Visual Basic에서 프로그래밍을 계속할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3bc0b-112">You can continue to program in C# or Visual Basic.</span></span>

- <span data-ttu-id="3bc0b-113">클래스 라이브러리, 자동 메모리 관리, 가비지 수집, 예외 처리 등의 .NET Framework에서 제공하는 리소스를 계속 활용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3bc0b-113">You can continue to take advantage of the resources provided by the .NET Framework, including its class library, automatic memory management and garbage collection, and exception handling.</span></span>

<span data-ttu-id="3bc0b-114">앱 사용자의 경우 .NET 네이티브는 다음과 같은 이점을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="3bc0b-114">For users of your apps, .NET Native offers these advantages:</span></span>

- <span data-ttu-id="3bc0b-115">대부분의 앱 및 시나리오에 대 한 실행 시간을 단축 합니다.</span><span class="sxs-lookup"><span data-stu-id="3bc0b-115">Faster execution times for the majority of apps and scenarios.</span></span>

- <span data-ttu-id="3bc0b-116">대부분의 앱 및 시나리오에 대 한 시작 시간을 단축 합니다.</span><span class="sxs-lookup"><span data-stu-id="3bc0b-116">Faster startup times for the majority of apps and scenarios.</span></span>

- <span data-ttu-id="3bc0b-117">낮은 배포 및 업데이트 비용</span><span class="sxs-lookup"><span data-stu-id="3bc0b-117">Low deployment and update costs.</span></span>

- <span data-ttu-id="3bc0b-118">최적화 된 앱 메모리 사용량입니다.</span><span class="sxs-lookup"><span data-stu-id="3bc0b-118">Optimized app memory usage.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3bc0b-119">대부분의 앱 및 시나리오에서 .NET 네이티브는 IL 또는 NGEN 이미지로 컴파일된 앱에 비해 훨씬 빠른 시작 시간 및 뛰어난 성능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="3bc0b-119">For the vast majority of apps and scenarios, .NET Native offers significantly faster startup times and superior performance when compared to an app compiled to IL or to an NGEN image.</span></span> <span data-ttu-id="3bc0b-120">그러나 결과가 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3bc0b-120">However, your results may vary.</span></span> <span data-ttu-id="3bc0b-121">앱이 .NET 네이티브의 성능 향상으로 인 한 혜택을 보장 하려면 해당 성능과 앱의 non-.NET 네이티브 버전을 비교 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3bc0b-121">To ensure that your app has benefited from the performance enhancements of .NET Native, you should compare its performance with that of the non-.NET Native version of your app.</span></span> <span data-ttu-id="3bc0b-122">자세한 내용은 [성능 세션 개요](/visualstudio/profiling/performance-session-overview)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3bc0b-122">For more information, see [Performance Session Overview](/visualstudio/profiling/performance-session-overview).</span></span>

<span data-ttu-id="3bc0b-123">하지만 .NET 네이티브에는 네이티브 코드에 대 한 컴파일 이상의 작업이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3bc0b-123">But .NET Native involves more than a compilation to native code.</span></span> <span data-ttu-id="3bc0b-124">.NET Framework 앱 빌드 및 실행 방식도 바뀝니다.</span><span class="sxs-lookup"><span data-stu-id="3bc0b-124">It transforms the way that .NET Framework apps are built and executed.</span></span> <span data-ttu-id="3bc0b-125">특히 다음 사항에 주의하십시오.</span><span class="sxs-lookup"><span data-stu-id="3bc0b-125">In particular:</span></span>

- <span data-ttu-id="3bc0b-126">미리 컴파일하는 동안 .NET Framework의 필수 부분이 앱에 정적으로 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="3bc0b-126">During precompilation, required portions of the .NET Framework are statically linked into your app.</span></span> <span data-ttu-id="3bc0b-127">따라서 앱이 .NET Framework의 앱 로컬 라이브러리를 사용하여 실행될 수 있으며 컴파일러가 전역 분석을 수행하여 성능을 개선할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3bc0b-127">This allows the app to run with app-local libraries of the .NET Framework, and the compiler to perform global analysis to deliver performance wins.</span></span> <span data-ttu-id="3bc0b-128">따라서 .NET Framework를 업데이트한 후에도 앱이 지속적으로 빠르게 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="3bc0b-128">As a result, apps launch consistently faster even after .NET Framework updates.</span></span>

- <span data-ttu-id="3bc0b-129">.NET 네이티브 런타임은 정적 미리 컴파일에 최적화 되어 있으며 대부분의 경우 우수한 성능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="3bc0b-129">The .NET Native runtime is optimized for static precompilation and in the vast majority of cases offers superior performance.</span></span> <span data-ttu-id="3bc0b-130">그와 동시에 개발자의 생산성을 높여 주는 핵심 리플렉션 기능도 계속 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="3bc0b-130">At the same time, it retains the core reflection features that developers find so productive.</span></span>

- <span data-ttu-id="3bc0b-131">.NET 네이티브는 정적 미리 컴파일 시나리오용으로 최적화 된 c + + 컴파일러와 같은 백 엔드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="3bc0b-131">.NET Native uses the same back end as the C++ compiler, which is optimized for static precompilation scenarios.</span></span>

<span data-ttu-id="3bc0b-132">이 표에 표시 된 것 처럼 .NET 네이티브는 c + +와 같거나 비슷한 도구를 사용 하 여 관리 코드 개발자에 게 c + +의 성능 이점을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3bc0b-132">.NET Native is able to bring the performance benefits of C++ to managed code developers because it uses the same or similar tools as C++ under the hood, as shown in this table.</span></span>

||<span data-ttu-id="3bc0b-133">.NET 네이티브</span><span class="sxs-lookup"><span data-stu-id="3bc0b-133">.NET Native</span></span>|<span data-ttu-id="3bc0b-134">C++</span><span class="sxs-lookup"><span data-stu-id="3bc0b-134">C++</span></span>|
|-|----------------------------------------------------------------|-----------|
|<span data-ttu-id="3bc0b-135">라이브러리</span><span class="sxs-lookup"><span data-stu-id="3bc0b-135">Libraries</span></span>|<span data-ttu-id="3bc0b-136">.NET Framework + Windows 런타임</span><span class="sxs-lookup"><span data-stu-id="3bc0b-136">The .NET Framework + Windows Runtime</span></span>|<span data-ttu-id="3bc0b-137">Win32 + Windows 런타임</span><span class="sxs-lookup"><span data-stu-id="3bc0b-137">Win32 + Windows Runtime</span></span>|
|<span data-ttu-id="3bc0b-138">컴파일러</span><span class="sxs-lookup"><span data-stu-id="3bc0b-138">Compiler</span></span>|<span data-ttu-id="3bc0b-139">UTC 최적화 컴파일러</span><span class="sxs-lookup"><span data-stu-id="3bc0b-139">UTC optimizing compiler</span></span>|<span data-ttu-id="3bc0b-140">UTC 최적화 컴파일러</span><span class="sxs-lookup"><span data-stu-id="3bc0b-140">UTC optimizing compiler</span></span>|
|<span data-ttu-id="3bc0b-141">배포됨</span><span class="sxs-lookup"><span data-stu-id="3bc0b-141">Deployed</span></span>|<span data-ttu-id="3bc0b-142">실행 가능 이진 파일</span><span class="sxs-lookup"><span data-stu-id="3bc0b-142">Ready-to-run binaries</span></span>|<span data-ttu-id="3bc0b-143">실행 가능 이진 파일(ASM)</span><span class="sxs-lookup"><span data-stu-id="3bc0b-143">Ready-to-run binaries (ASM)</span></span>|
|<span data-ttu-id="3bc0b-144">런타임</span><span class="sxs-lookup"><span data-stu-id="3bc0b-144">Runtime</span></span>|<span data-ttu-id="3bc0b-145">MRT.dll(최소 CLR 런타임)</span><span class="sxs-lookup"><span data-stu-id="3bc0b-145">MRT.dll (Minimal CLR Runtime)</span></span>|<span data-ttu-id="3bc0b-146">CRT.dll(C 런타임)</span><span class="sxs-lookup"><span data-stu-id="3bc0b-146">CRT.dll (C Runtime)</span></span>|

<span data-ttu-id="3bc0b-147">Windows 10용 Windows 앱의 경우 앱 패키지(.appx 파일)의 .NET 네이티브 코드 컴파일 이진 파일을 Windows 스토어에 업로드합니다.</span><span class="sxs-lookup"><span data-stu-id="3bc0b-147">For Windows apps for Windows 10, you upload .NET Native Code Compilation binaries in app packages (.appx files) to the Windows Store.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="3bc0b-148">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="3bc0b-148">In This Section</span></span>

<span data-ttu-id="3bc0b-149">.NET 네이티브 코드 컴파일을 사용한 앱 개발에 대한 자세한 내용은 다음 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3bc0b-149">For more information about developing apps with .NET Native Code Compilation, see these topics:</span></span>

- [<span data-ttu-id="3bc0b-150">.NET 네이티브 코드 컴파일 시작: 개발자 환경 연습</span><span class="sxs-lookup"><span data-stu-id="3bc0b-150">Getting Started with .NET Native Code Compilation: The Developer Experience Walkthrough</span></span>](getting-started-with-net-native.md)

- <span data-ttu-id="3bc0b-151">[.NET 네이티브 및 컴파일:](net-native-and-compilation.md) .NET 네이티브에서 프로젝트를 네이티브 코드로 컴파일하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="3bc0b-151">[.NET Native and Compilation:](net-native-and-compilation.md) How .NET Native compiles your project to native code.</span></span>

- [<span data-ttu-id="3bc0b-152">리플렉션 및 .NET 네이티브</span><span class="sxs-lookup"><span data-stu-id="3bc0b-152">Reflection and .NET Native</span></span>](reflection-and-net-native.md)

  - [<span data-ttu-id="3bc0b-153">리플렉션을 사용하는 API</span><span class="sxs-lookup"><span data-stu-id="3bc0b-153">APIs That Rely on Reflection</span></span>](apis-that-rely-on-reflection.md)

  - [<span data-ttu-id="3bc0b-154">리플렉션 API 참조</span><span class="sxs-lookup"><span data-stu-id="3bc0b-154">Reflection API Reference</span></span>](net-native-reflection-api-reference.md)

  - [<span data-ttu-id="3bc0b-155">런타임 지시문(rd.xml) 구성 파일 참조</span><span class="sxs-lookup"><span data-stu-id="3bc0b-155">Runtime Directives (rd.xml) Configuration File Reference</span></span>](runtime-directives-rd-xml-configuration-file-reference.md)

- [<span data-ttu-id="3bc0b-156">Serialization 및 메타데이터</span><span class="sxs-lookup"><span data-stu-id="3bc0b-156">Serialization and Metadata</span></span>](serialization-and-metadata.md)

- [<span data-ttu-id="3bc0b-157">Windows 스토어 앱을 .NET 네이티브로 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="3bc0b-157">Migrating Your Windows Store App to .NET Native</span></span>](migrating-your-windows-store-app-to-net-native.md)

- [<span data-ttu-id="3bc0b-158">.NET 네이티브 일반 문제 해결</span><span class="sxs-lookup"><span data-stu-id="3bc0b-158">.NET Native General Troubleshooting</span></span>](net-native-general-troubleshooting.md)
