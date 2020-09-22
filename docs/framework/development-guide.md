---
title: .NET Framework 개발 가이드
description: .NET 앱을 생성, 구성, 디버그, 배포하고 보안을 적용하는 방법을 설명하는 .NET 개발 가이드를 살펴봅니다.
ms.date: 03/30/2017
helpviewer_keywords:
- .NET Framework, development guide
ms.assetid: 26e3d285-24c3-435c-a797-9fe5affb8525
ms.openlocfilehash: 73b930efa893fd2b481c4c130754154a0d10d5b4
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "90547886"
---
# <a name="net-framework-development-guide"></a><span data-ttu-id="14a9b-103">.NET Framework 개발 가이드</span><span class="sxs-lookup"><span data-stu-id="14a9b-103">.NET Framework development guide</span></span>

<span data-ttu-id="14a9b-104">이 섹션에서는 .NET Framework 앱을 생성, 구성, 디버그, 배포하고 보안을 적용하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="14a9b-104">This section explains how to create, configure, debug, secure, and deploy your .NET Framework apps.</span></span> <span data-ttu-id="14a9b-105">이 섹션에서는 또한 동적 프로그래밍, 상호 운용성, 확장성, 메모리 관리 및 스레딩과 같은 기술 영역에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="14a9b-105">The section also provides information about technology areas such as dynamic programming, interoperability, extensibility, memory management, and threading.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="14a9b-106">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="14a9b-106">In This Section</span></span>
  
 [<span data-ttu-id="14a9b-107">데이터 및 모델링</span><span class="sxs-lookup"><span data-stu-id="14a9b-107">Data and Modeling</span></span>](./data/index.md)  
 <span data-ttu-id="14a9b-108">ADO.NET, LINQ(Language Integrated Query), WCF Data Services 및 XML을 사용하여 데이터에 액세스하는 방법에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="14a9b-108">Provides information about how to access data using ADO.NET, Language Integrated Query (LINQ), WCF Data Services, and XML.</span></span>  
  
 [<span data-ttu-id="14a9b-109">클라이언트 애플리케이션</span><span class="sxs-lookup"><span data-stu-id="14a9b-109">Client Applications</span></span>](develop-client-apps.md)  
 <span data-ttu-id="14a9b-110">WPF(Windows Presentation Foundation) 또는 Windows Forms를 사용하여 Windows 기반 앱을 만드는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="14a9b-110">Explains how to create Windows-based apps by using Windows Presentation Foundation (WPF) or Windows Forms.</span></span>  
  
 [<span data-ttu-id="14a9b-111">ASP.NET을 사용하여 개발한 웹 애플리케이션</span><span class="sxs-lookup"><span data-stu-id="14a9b-111">Web Applications with ASP.NET</span></span>](develop-web-apps-with-aspnet.md)  
 <span data-ttu-id="14a9b-112">ASP.NET을 사용하여 최소한의 코딩으로 엔터프라이즈급 웹 응용 프로그램을 빌드하는 방법에 대한 링크를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="14a9b-112">Provides links to information about using ASP.NET to build enterprise-class web apps with a minimum of coding.</span></span>  
  
 [<span data-ttu-id="14a9b-113">WCF를 사용하여 개발한 서비스 기반 애플리케이션</span><span class="sxs-lookup"><span data-stu-id="14a9b-113">Service-Oriented Applications with WCF</span></span>](./wcf/index.md)  
 <span data-ttu-id="14a9b-114">WCF(Windows Communication Foundation)를 사용하여 안전하고 신뢰할 수 있는 서비스 지향 앱을 빌드하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="14a9b-114">Describes how to use Windows Communication Foundation (WCF) to build service-oriented apps that are secure and reliable.</span></span>  
  
 <span data-ttu-id="14a9b-115">[Windows Workflow Foundation으로 워크플로 만들기](windows-workflow-foundation/index.md) Windows WF(Workflow Foundation)를 사용하는 프로그래밍 모델, 샘플 및 도구에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="14a9b-115">[Building workflows with Windows Workflow Foundation](windows-workflow-foundation/index.md) Provides information about the programming model, samples, and tools for using Windows Workflow Foundation (WF).</span></span>  

 [<span data-ttu-id="14a9b-116">Windows 서비스 애플리케이션</span><span class="sxs-lookup"><span data-stu-id="14a9b-116">Windows Service Applications</span></span>](./windows-services/index.md)  
 <span data-ttu-id="14a9b-117">Visual Studio 및 .NET Framework를 사용하여 서비스로서 설치되는 앱을 만들고 서비스 동작을 시작, 중지 및 다른 방식으로 제어하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="14a9b-117">Explains how you can use Visual Studio and the .NET Framework to create an app that is installed as a service, and start, stop, and otherwise control its behavior.</span></span>  
  
 [<span data-ttu-id="14a9b-118">.NET의 병렬 처리, 동시성 및 비동기 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="14a9b-118">Parallel Processing, Concurrency, and Async Programming in .NET</span></span>](../standard/parallel-processing-and-concurrency.md)  
 <span data-ttu-id="14a9b-119">관리되는 스레딩, 병렬 프로그래밍 및 비동기 프로그래밍 디자인 패턴에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="14a9b-119">Provides information about managed threading, parallel programming, and asynchronous programming design patterns.</span></span>  
  
 [<span data-ttu-id="14a9b-120">.NET Framework의 네트워크 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="14a9b-120">Network Programming in the .NET Framework</span></span>](./network-programming/index.md)  
 <span data-ttu-id="14a9b-121">더 빠르고 쉽게 앱에 통합할 수 있는 계층적이고 확장 가능하며 관리되는 인터넷 서비스 구현에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="14a9b-121">Describes the layered, extensible, and managed implementation of Internet services that you can quickly and easily integrate into your apps.</span></span>  
  
 <span data-ttu-id="14a9b-122">[.NET Framework 앱 구성](configure-apps/index.md) .NET Framework 앱을 다시 컴파일하지 않고도 구성 파일을 사용하여 설정을 변경할 수 있는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="14a9b-122">[Configuring .NET Framework Apps](configure-apps/index.md) Explains how you can use configuration files to change settings without having to recompile your .NET Framework apps.</span></span>  
  
 [<span data-ttu-id="14a9b-123">.NET Native로 앱 컴파일</span><span class="sxs-lookup"><span data-stu-id="14a9b-123">Compiling Apps with .NET Native</span></span>](./net-native/index.md)  
 <span data-ttu-id="14a9b-124">.NET 네이티브 미리 컴파일 기술을 사용하여 Windows 스토어 앱을 빌드 및 배포하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="14a9b-124">Explains how you can use the .NET Native precompilation technology to build and deploy Windows Store apps.</span></span> <span data-ttu-id="14a9b-125">.NET 네이티브에서는 관리 코드(C#)로 작성되며 .NET Framework을 대상으로 지정하는 앱을 네이티브 코드로 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="14a9b-125">.NET Native compiles apps that are written in managed code (C#) and that target the .NET Framework to native code.</span></span>  
  
 [<span data-ttu-id="14a9b-126">보안</span><span class="sxs-lookup"><span data-stu-id="14a9b-126">Security</span></span>](../standard/security/index.md)  
 <span data-ttu-id="14a9b-127">안전한 앱 개발을 용이하게 하는 .NET Framework의 클래스 및 서비스에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="14a9b-127">Provides information about the classes and services in the .NET Framework that facilitate secure app development.</span></span>  
  
 [<span data-ttu-id="14a9b-128">디버깅, 추적 및 프로파일링</span><span class="sxs-lookup"><span data-stu-id="14a9b-128">Debugging, Tracing, and Profiling</span></span>](./debug-trace-profile/index.md)  
 <span data-ttu-id="14a9b-129">.NET Framework 앱 및 앱 환경을 테스트하고 최적화하며 프로파일링하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="14a9b-129">Explains how to test, optimize, and profile .NET Framework apps and the app environment.</span></span> <span data-ttu-id="14a9b-130">이 단원은 관리자와 개발자 모두가 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14a9b-130">This section includes information for administrators as well as developers.</span></span>  
  
 [<span data-ttu-id="14a9b-131">여러 플랫폼을 대상으로 개발</span><span class="sxs-lookup"><span data-stu-id="14a9b-131">Developing for Multiple Platforms</span></span>](../standard/cross-platform/index.md)  
 <span data-ttu-id="14a9b-132">.NET Framework 를 사용하여 여러 플랫폼과 휴대폰, 데스크톱 및 웹 등 여러 디바이스 간에 공유할 수 있는 어셈블리를 빌드하는 방법에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="14a9b-132">Provides information about how you can use the .NET Framework to build assemblies that can be shared across multiple platforms and multiple devices such as phones, desktop, and web.</span></span>  
  
 [<span data-ttu-id="14a9b-133">배포</span><span class="sxs-lookup"><span data-stu-id="14a9b-133">Deployment</span></span>](./deployment/index.md)  
 <span data-ttu-id="14a9b-134">.NET Framework 앱을 패키지 및 배포하는 방법에 대해 설명하고 개발자와 관리자 모두를 위한 배포 가이드를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="14a9b-134">Explains how to package and distribute your .NET Framework app, and includes deployment guides for both developers and administrators.</span></span>  
  
 [<span data-ttu-id="14a9b-135">성능</span><span class="sxs-lookup"><span data-stu-id="14a9b-135">Performance</span></span>](./performance/index.md)  
 <span data-ttu-id="14a9b-136">캐싱, 초기화 지연, 안정성 및 ETW 이벤트에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="14a9b-136">Provides information about caching, lazy initialization, reliability, and ETW events.</span></span>  

## <a name="reference"></a><span data-ttu-id="14a9b-137">참고</span><span class="sxs-lookup"><span data-stu-id="14a9b-137">Reference</span></span>  
 [<span data-ttu-id="14a9b-138">.NET Framework 클래스 라이브러리</span><span class="sxs-lookup"><span data-stu-id="14a9b-138">.NET Framework Class Library</span></span>](../../api/index.md?view=netframework-4.7)  
 <span data-ttu-id="14a9b-139">.NET Framework 네임스페이스에 포함된 각 클래스에 대한 구문, 코드 예제 및 사용 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="14a9b-139">Supplies syntax, code examples, and usage information for each class that is contained in the .NET Framework namespaces.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="14a9b-140">관련 단원</span><span class="sxs-lookup"><span data-stu-id="14a9b-140">Related Sections</span></span>  
 [<span data-ttu-id="14a9b-141">시작</span><span class="sxs-lookup"><span data-stu-id="14a9b-141">Getting Started</span></span>](./get-started/index.md)  
 <span data-ttu-id="14a9b-142">.NET Framework의 포괄적인 개요 및 추가 리소스에 대한 링크를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="14a9b-142">Provides a comprehensive overview of the .NET Framework and links to additional resources.</span></span>  
  
 [<span data-ttu-id="14a9b-143">새로운 기능</span><span class="sxs-lookup"><span data-stu-id="14a9b-143">What's New</span></span>](./whats-new/index.md)  
 <span data-ttu-id="14a9b-144">최신 버전의 .NET Framework에 새로 추가된 주요 기능과 변경 내용에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="14a9b-144">Describes key new features and changes in the latest version of the .NET Framework.</span></span> <span data-ttu-id="14a9b-145">새로운 형식과 멤버, 사용되지 않는 형식과 멤버의 목록을 제공하고 이전 .NET Framework 버전에서 앱을 마이그레이션하는 방법에 대한 지침을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="14a9b-145">Includes lists of new and obsolete types and members, and provides a guide for migrating your apps from the previous version of the .NET Framework.</span></span>  
  
 [<span data-ttu-id="14a9b-146">도구</span><span class="sxs-lookup"><span data-stu-id="14a9b-146">Tools</span></span>](./tools/index.md)  
 <span data-ttu-id="14a9b-147">.NET Framework 기술을 사용하여 앱을 개발, 구성 및 배포하는 데 도움이 되는 도구에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="14a9b-147">Describes the tools that help you develop, configure, and deploy apps by using .NET Framework technologies.</span></span>  
  
 [<span data-ttu-id="14a9b-148">.NET 샘플 및 자습서</span><span class="sxs-lookup"><span data-stu-id="14a9b-148">.NET samples and tutorials</span></span>](../samples-and-tutorials/index.md)  
 <span data-ttu-id="14a9b-149">.NET을 학습할 수 있는 샘플 및 자습서에 대한 링크를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="14a9b-149">Provides links to samples and tutorials that help you learn about .NET.</span></span>
