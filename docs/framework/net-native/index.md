---
title: .NET 네이티브로 앱 컴파일
ms.date: 03/30/2017
helpviewer_keywords:
- native compilation
- .NET and native code
- compilation with .NET Native
- .NET Native
- C# and native compilation
ms.assetid: 47cd5648-9469-4b1d-804c-43cc04384045
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c3c845cefad451c608f5c095e4941c3368dc9975
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64650557"
---
# <a name="compiling-apps-with-net-native"></a><span data-ttu-id="08ad7-102">.NET 네이티브로 앱 컴파일</span><span class="sxs-lookup"><span data-stu-id="08ad7-102">Compiling Apps with .NET Native</span></span>
[!INCLUDE[net_native](../../../includes/net-native-md.md)] <span data-ttu-id="08ad7-103">Visual Studio 2015 및 이상 버전을 사용 하 여 포함 된 Windows 앱 빌드 및 배포에 대 한 미리 컴파일 기술입니다.</span><span class="sxs-lookup"><span data-stu-id="08ad7-103">is a precompilation technology for building and deploying Windows apps that is included with Visual Studio 2015 and later versions.</span></span> <span data-ttu-id="08ad7-104">관리 코드(C# 또는 Visual Basic)로 작성되었으며 .NET Framework 및 Windows 10의 대상을 네이티브 코드로 지정하는 앱의 릴리스 버전을 자동으로 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="08ad7-104">It automatically compiles the release version of apps that are written in managed code (C# or Visual Basic) and that target the .NET Framework and Windows 10 to native code.</span></span>  
  
 <span data-ttu-id="08ad7-105">일반적으로 .NET Framework를 대상으로 하는 앱은 IL(중간 언어)로 컴파일됩니다.</span><span class="sxs-lookup"><span data-stu-id="08ad7-105">Typically, apps that target the .NET Framework are compiled to intermediate language (IL).</span></span> <span data-ttu-id="08ad7-106">런타임에 JIT(Just-In-Time) 컴파일러가 IL을 네이티브 코드로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="08ad7-106">At run time, the just-in-time (JIT) compiler translates the IL to native code.</span></span> <span data-ttu-id="08ad7-107">반면 [!INCLUDE[net_native](../../../includes/net-native-md.md)] 에서는 Windows 앱을 네이티브 코드로 직접 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="08ad7-107">In contrast, [!INCLUDE[net_native](../../../includes/net-native-md.md)] compiles Windows apps directly to native code.</span></span> <span data-ttu-id="08ad7-108">이러한 방식이 개발자에게 의미하는 바는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="08ad7-108">For developers, this means:</span></span>  
  
- <span data-ttu-id="08ad7-109">앱에 네이티브 코드의 성능을 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="08ad7-109">Your apps feature the performance of native code.</span></span> <span data-ttu-id="08ad7-110">일반적으로 성능이 향상이 됩니다 먼저 IL로 컴파일되고 JIT 컴파일러에서 네이티브 코드로 컴파일된 다음 코드에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08ad7-110">Usually, performance will be superior to code that is first compiled to IL and then compiled to native code by the JIT compiler.</span></span> 
  
- <span data-ttu-id="08ad7-111">C# 또는 Visual Basic에서 프로그래밍을 계속할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08ad7-111">You can continue to program in C# or Visual Basic.</span></span>  
  
- <span data-ttu-id="08ad7-112">클래스 라이브러리, 자동 메모리 관리, 가비지 수집, 예외 처리 등의 .NET Framework에서 제공하는 리소스를 계속 활용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08ad7-112">You can continue to take advantage of the resources provided by the .NET Framework, including its class library, automatic memory management and garbage collection, and exception handling.</span></span>  
  
 <span data-ttu-id="08ad7-113">앱 사용자에 대해 [!INCLUDE[net_native](../../../includes/net-native-md.md)]에서 제공하는 이점은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="08ad7-113">For users of your apps, [!INCLUDE[net_native](../../../includes/net-native-md.md)] offers these advantages:</span></span>  
  
- <span data-ttu-id="08ad7-114">대부분의 앱 및 시나리오에 대 한 더 빠른 실행 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="08ad7-114">Faster execution times for the majority of apps and scenarios.</span></span>
  
- <span data-ttu-id="08ad7-115">대부분의 앱 및 시나리오에 대 한 빠른 시작 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="08ad7-115">Faster startup times for the majority of apps and scenarios.</span></span> 
  
- <span data-ttu-id="08ad7-116">저렴 한 배포 및 업데이트 비용입니다.</span><span class="sxs-lookup"><span data-stu-id="08ad7-116">Low deployment and update costs.</span></span>  
  
- <span data-ttu-id="08ad7-117">앱 메모리 사용량을 최적화 합니다.</span><span class="sxs-lookup"><span data-stu-id="08ad7-117">Optimized app memory usage.</span></span>  

> [!IMPORTANT]
> <span data-ttu-id="08ad7-118">대부분의 앱와 시나리오에 대 한.NET 네이티브 시작 시간을 크게 단축 및 제공 NGEN 이미지 또는 IL로 컴파일된 앱에 비해 뛰어난 성능을 합니다.</span><span class="sxs-lookup"><span data-stu-id="08ad7-118">For the vast majority of apps and scenarios, .NET Native offers significantly faster startup times and superior performance when compared to an app compiled to IL or to an NGEN image.</span></span> <span data-ttu-id="08ad7-119">그러나 결과가 달라질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08ad7-119">However, your results may vary.</span></span> <span data-ttu-id="08ad7-120">앱에는 성능 향상의.NET 네이티브에서 활용할 수 있도록는 비-.NET 네이티브 버전을 앱의 성능을 비교 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="08ad7-120">To ensure that your app has benefited from the performance enhancements of .NET Native, you should compare its performance with that of the non-.NET Native version of your app.</span></span> <span data-ttu-id="08ad7-121">자세한 내용은 [성능 세션 개요](https://docs.microsoft.com/visualstudio/profiling/performance-session-overview)합니다.</span><span class="sxs-lookup"><span data-stu-id="08ad7-121">For more information, see [Performance Session Overview](https://docs.microsoft.com/visualstudio/profiling/performance-session-overview).</span></span>
 
<span data-ttu-id="08ad7-122">[!INCLUDE[net_native](../../../includes/net-native-md.md)] 를 사용하는 경우 이처럼 네이티브 코드로의 컴파일이 수행될 뿐 아니라,</span><span class="sxs-lookup"><span data-stu-id="08ad7-122">But [!INCLUDE[net_native](../../../includes/net-native-md.md)] involves more than a compilation to native code.</span></span> <span data-ttu-id="08ad7-123">.NET Framework 앱 빌드 및 실행 방식도 바뀝니다.</span><span class="sxs-lookup"><span data-stu-id="08ad7-123">It transforms the way that .NET Framework apps are built and executed.</span></span> <span data-ttu-id="08ad7-124">특히 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="08ad7-124">In particular:</span></span>  
  
- <span data-ttu-id="08ad7-125">미리 컴파일하는 동안 .NET Framework의 필수 부분이 앱에 정적으로 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="08ad7-125">During precompilation, required portions of the .NET Framework are statically linked into your app.</span></span> <span data-ttu-id="08ad7-126">따라서 앱이 .NET Framework의 앱 로컬 라이브러리를 사용하여 실행될 수 있으며 컴파일러가 전역 분석을 수행하여 성능을 개선할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08ad7-126">This allows the app to run with app-local libraries of the .NET Framework, and the compiler to perform global analysis to deliver performance wins.</span></span> <span data-ttu-id="08ad7-127">따라서 .NET Framework를 업데이트한 후에도 앱이 지속적으로 빠르게 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="08ad7-127">As a result, apps launch consistently faster even after .NET Framework updates.</span></span>  
  
- <span data-ttu-id="08ad7-128">[!INCLUDE[net_native](../../../includes/net-native-md.md)] 런타임 정적 미리 컴파일에 최적화 되어 있고 대부분의 경우에서 뛰어난 성능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="08ad7-128">The [!INCLUDE[net_native](../../../includes/net-native-md.md)] runtime is optimized for static precompilation and in the vast majority of cases offers superior performance.</span></span> <span data-ttu-id="08ad7-129">그와 동시에 개발자의 생산성을 높여 주는 핵심 리플렉션 기능도 계속 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="08ad7-129">At the same time, it retains the core reflection features that developers find so productive.</span></span>  
  
- [!INCLUDE[net_native](../../../includes/net-native-md.md)] <span data-ttu-id="08ad7-130">는 정적 미리 컴파일 시나리오용으로 최적화된 C++ 컴파일러와 같은 백 엔드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="08ad7-130">uses the same back end as the C++ compiler, which is optimized for static precompilation scenarios.</span></span>  
  
 [!INCLUDE[net_native](../../../includes/net-native-md.md)] <span data-ttu-id="08ad7-131">는 아래 표에 나와 있는 것처럼 내부적으로 C++와 같거나 비슷한 도구를 사용하므로 관리 코드 개발자에게 C++의 성능 이점을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08ad7-131">is able to bring the performance benefits of C++ to managed code developers because it uses the same or similar tools as C++ under the hood, as shown in this table.</span></span>  
  
||[!INCLUDE[net_native](../../../includes/net-native-md.md)]|<span data-ttu-id="08ad7-132">C++</span><span class="sxs-lookup"><span data-stu-id="08ad7-132">C++</span></span>|  
|-|----------------------------------------------------------------|-----------|  
|<span data-ttu-id="08ad7-133">라이브러리</span><span class="sxs-lookup"><span data-stu-id="08ad7-133">Libraries</span></span>|<span data-ttu-id="08ad7-134">.NET Framework + Windows 런타임</span><span class="sxs-lookup"><span data-stu-id="08ad7-134">The .NET Framework + Windows Runtime</span></span>|<span data-ttu-id="08ad7-135">Win32 + Windows 런타임</span><span class="sxs-lookup"><span data-stu-id="08ad7-135">Win32 + Windows Runtime</span></span>|  
|<span data-ttu-id="08ad7-136">컴파일러</span><span class="sxs-lookup"><span data-stu-id="08ad7-136">Compiler</span></span>|<span data-ttu-id="08ad7-137">UTC 최적화 컴파일러</span><span class="sxs-lookup"><span data-stu-id="08ad7-137">UTC optimizing compiler</span></span>|<span data-ttu-id="08ad7-138">UTC 최적화 컴파일러</span><span class="sxs-lookup"><span data-stu-id="08ad7-138">UTC optimizing compiler</span></span>|  
|<span data-ttu-id="08ad7-139">배포됨</span><span class="sxs-lookup"><span data-stu-id="08ad7-139">Deployed</span></span>|<span data-ttu-id="08ad7-140">실행 가능 이진 파일</span><span class="sxs-lookup"><span data-stu-id="08ad7-140">Ready-to-run binaries</span></span>|<span data-ttu-id="08ad7-141">실행 가능 이진 파일(ASM)</span><span class="sxs-lookup"><span data-stu-id="08ad7-141">Ready-to-run binaries (ASM)</span></span>|  
|<span data-ttu-id="08ad7-142">런타임</span><span class="sxs-lookup"><span data-stu-id="08ad7-142">Runtime</span></span>|<span data-ttu-id="08ad7-143">MRT.dll(최소 CLR 런타임)</span><span class="sxs-lookup"><span data-stu-id="08ad7-143">MRT.dll (Minimal CLR Runtime)</span></span>|<span data-ttu-id="08ad7-144">CRT.dll(C 런타임)</span><span class="sxs-lookup"><span data-stu-id="08ad7-144">CRT.dll (C Runtime)</span></span>|  
  
 <span data-ttu-id="08ad7-145">Windows 10용 Windows 앱의 경우 앱 패키지(.appx 파일)의 .NET 네이티브 코드 컴파일 이진 파일을 Windows 스토어에 업로드합니다.</span><span class="sxs-lookup"><span data-stu-id="08ad7-145">For Windows apps for Windows 10, you upload .NET Native Code Compilation binaries in app packages (.appx files) to the Windows Store.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="08ad7-146">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="08ad7-146">In This Section</span></span>  
 <span data-ttu-id="08ad7-147">.NET 네이티브 코드 컴파일을 사용한 앱 개발에 대한 자세한 내용은 다음 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="08ad7-147">For more information about developing apps with .NET Native Code Compilation, see these topics:</span></span>  
  
- [<span data-ttu-id="08ad7-148">.NET 네이티브 코드 컴파일 시작 하기: 개발자 환경 연습</span><span class="sxs-lookup"><span data-stu-id="08ad7-148">Getting Started with .NET Native Code Compilation: The Developer Experience Walkthrough</span></span>](../../../docs/framework/net-native/getting-started-with-net-native.md)  
  
- <span data-ttu-id="08ad7-149">[.NET 네이티브 및 컴파일:](../../../docs/framework/net-native/net-native-and-compilation.md) 어떻게.NET 네이티브는 프로젝트를를 네이티브 코드로 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="08ad7-149">[.NET Native and Compilation:](../../../docs/framework/net-native/net-native-and-compilation.md) How .NET Native compiles your project to native code.</span></span>  
  
- [<span data-ttu-id="08ad7-150">리플렉션 및 .NET 네이티브</span><span class="sxs-lookup"><span data-stu-id="08ad7-150">Reflection and .NET Native</span></span>](../../../docs/framework/net-native/reflection-and-net-native.md)  
  
    - [<span data-ttu-id="08ad7-151">리플렉션을 사용하는 API</span><span class="sxs-lookup"><span data-stu-id="08ad7-151">APIs That Rely on Reflection</span></span>](../../../docs/framework/net-native/apis-that-rely-on-reflection.md)  
  
    - [<span data-ttu-id="08ad7-152">리플렉션 API 참조</span><span class="sxs-lookup"><span data-stu-id="08ad7-152">Reflection API Reference</span></span>](../../../docs/framework/net-native/net-native-reflection-api-reference.md)  
  
    - [<span data-ttu-id="08ad7-153">런타임 지시문(rd.xml) 구성 파일 참조</span><span class="sxs-lookup"><span data-stu-id="08ad7-153">Runtime Directives (rd.xml) Configuration File Reference</span></span>](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)  
  
- [<span data-ttu-id="08ad7-154">Serialization 및 메타데이터</span><span class="sxs-lookup"><span data-stu-id="08ad7-154">Serialization and Metadata</span></span>](../../../docs/framework/net-native/serialization-and-metadata.md)  
  
- [<span data-ttu-id="08ad7-155">Windows 스토어 앱을 .NET 네이티브로 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="08ad7-155">Migrating Your Windows Store App to .NET Native</span></span>](../../../docs/framework/net-native/migrating-your-windows-store-app-to-net-native.md)  
  
- [<span data-ttu-id="08ad7-156">.NET 네이티브 일반 문제 해결</span><span class="sxs-lookup"><span data-stu-id="08ad7-156">.NET Native General Troubleshooting</span></span>](../../../docs/framework/net-native/net-native-general-troubleshooting.md)
