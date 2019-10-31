---
title: .NET Framework 설명서
ms.date: 04/02/2019
ms.custom: updateeachrelease
f1_keywords:
- f61f02f2-2f20-483d-8f56-a9c8f3a54986
helpviewer_keywords:
- .NET Framework, documentation
- documentation, .NET Framework
ms.assetid: f61f02f2-2f20-483d-8f56-a9c8f3a54986
ms.openlocfilehash: e00fb73bf884446ec220a114c49863386da456ef
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73114253"
---
# <a name="net-framework-guide"></a><span data-ttu-id="ff855-102">.NET Framework 가이드</span><span class="sxs-lookup"><span data-stu-id="ff855-102">.NET Framework Guide</span></span>

> [!NOTE]
> <span data-ttu-id="ff855-103">이 .NET Framework 콘텐츠 집합에는 .NET Framework 버전 4.5~4.8에 대한 정보가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ff855-103">This .NET Framework content set includes information for .NET Framework versions 4.5 through 4.8.</span></span> <span data-ttu-id="ff855-104">.NET Framework를 다운로드하려면 [.NET Framework 설치](./install/guide-for-developers.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ff855-104">To download the .NET Framework, see [Installing the .NET Framework](./install/guide-for-developers.md).</span></span> <span data-ttu-id="ff855-105">.NET Framework의 새로운 기능 및 변경 내용 목록은 [.NET Framework의 새로운 기능](./whats-new/index.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ff855-105">For a list of new features and changes in the NET Framework, see [What's New in the .NET Framework](./whats-new/index.md).</span></span> <span data-ttu-id="ff855-106">지원되는 플랫폼 목록은 [.NET Framework 시스템 요구 사항](./get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ff855-106">For a list of supported platforms, see [.NET Framework System Requirements](./get-started/system-requirements.md).</span></span> <span data-ttu-id="ff855-107">.NET Framework의 이전 버전에 대한 설명서는 [.NET 이전 버전 설명서](https://docs.microsoft.com/previous-versions/dotnet/)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ff855-107">For documentation about older versions of the .NET Framework, see [.NET previous versions documentation](https://docs.microsoft.com/previous-versions/dotnet/).</span></span>

<span data-ttu-id="ff855-108">.NET Framework는 웹, Windows, Windows Phone, Windows Server 및 Microsoft Azure용 앱을 빌드하기 위한 개발 플랫폼으로,</span><span class="sxs-lookup"><span data-stu-id="ff855-108">The .NET Framework is a development platform for building apps for web, Windows, Windows Phone, Windows Server, and Microsoft Azure.</span></span> <span data-ttu-id="ff855-109">많은 업계 표준에 대한 다양한 기능 및 지원을 포함하는 .NET Framework 클래스 라이브러리와 CLR(공용 언어 런타임)로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="ff855-109">It consists of the common language runtime (CLR) and the .NET Framework class library, which includes a broad range of functionality and support for many industry standards.</span></span>

<span data-ttu-id="ff855-110">.NET Framework는 메모리 관리, 유형 및 메모리 안전성, 보안, 네트워킹 및 애플리케이션 배포를 비롯하여 다양한 서비스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ff855-110">The .NET Framework provides many services, including memory management, type and memory safety, security, networking, and application deployment.</span></span> <span data-ttu-id="ff855-111">또한 하위 수준의 Windows 운영 체제를 추상화하는 사용하기 쉬운 데이터 구조 및 API를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ff855-111">It provides easy-to-use data structures and APIs that abstract the lower-level Windows operating system.</span></span> <span data-ttu-id="ff855-112">.NET Framework와 함께 C#, F#, Visual Basic 등의 다양한 프로그래밍 언어를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ff855-112">You can use different programming languages with the .NET Framework, including C#, F#, and Visual Basic.</span></span>

<span data-ttu-id="ff855-113">사용자와 개발자 모두를 위한 .NET Framework에 대한 일반적인 소개는 [시작](./get-started/index.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="ff855-113">For a general introduction to the .NET Framework for both users and developers, see [Getting Started](./get-started/index.md).</span></span> <span data-ttu-id="ff855-114">.NET Framework의 아키텍처 및 주요 기능에 대한 소개는 [개요](./get-started/overview.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ff855-114">For an introduction to the architecture and key features of the .NET Framework, see the [overview](./get-started/overview.md).</span></span>

<span data-ttu-id="ff855-115">[Windows 컨테이너](/virtualization/windowscontainers/about/)를 통해 Docker와 함께 .NET Framework를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ff855-115">The .NET Framework can be used with Docker and with [Windows Containers](/virtualization/windowscontainers/about/).</span></span>

## <a name="installation"></a><span data-ttu-id="ff855-116">설치</span><span class="sxs-lookup"><span data-stu-id="ff855-116">Installation</span></span>

<span data-ttu-id="ff855-117">Windows와 함께 .NET Framework를 사용하면 .NET Framework 애플리케이션을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ff855-117">The .NET Framework comes with Windows, enabling you to run .NET Framework applications.</span></span> <span data-ttu-id="ff855-118">Windows 버전과 함께 제공되는 버전보다 이후 버전의 .NET Framework가 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ff855-118">You may need a later version of the .NET Framework than the one that comes with your Windows version.</span></span> <span data-ttu-id="ff855-119">자세한 내용은 [Windows에 .NET Framework 설치](./install/index.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ff855-119">For more information, see [Install the .NET Framework on Windows](./install/index.md).</span></span>

<span data-ttu-id="ff855-120">[.NET Framework 복구](./install/repair.md)를 참조하여 .NET Framework를 설치할 때 오류가 발생하는 경우 .NET Framework 설치를 복구하는 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="ff855-120">See [Repair the .NET Framework](./install/repair.md) to learn how to repair your .NET Framework installation if you're experiencing errors when installing the .NET Framework.</span></span>

<span data-ttu-id="ff855-121">.NET Framework 다운로드에 대한 자세한 내용은 [개발자용 .NET Framework 설치](./install/guide-for-developers.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ff855-121">For more detailed information on downloading the .NET Framework, see [Install the .NET Framework for developers](./install/guide-for-developers.md).</span></span>

## <a name="in-this-section"></a><span data-ttu-id="ff855-122">단원 내용</span><span class="sxs-lookup"><span data-stu-id="ff855-122">In this section</span></span>

* [<span data-ttu-id="ff855-123">새로운 기능</span><span class="sxs-lookup"><span data-stu-id="ff855-123">What's New</span></span>](./whats-new/index.md)  
<span data-ttu-id="ff855-124">최신 버전의 .NET Framework에 새로 추가된 주요 기능과 변경 내용에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ff855-124">Describes key new features and changes in the latest versions of the .NET Framework.</span></span> <span data-ttu-id="ff855-125">사용되지 않는 형식 및 멤버의 목록을 제공하고 이전 .NET Framework 버전에서 애플리케이션을 마이그레이션하는 방법에 대한 지침을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ff855-125">Includes lists of obsolete types and members, and provides a guide for migrating your applications from the previous version of the .NET Framework.</span></span>

* [<span data-ttu-id="ff855-126">시작</span><span class="sxs-lookup"><span data-stu-id="ff855-126">Get Started</span></span>](./get-started/index.md)  
<span data-ttu-id="ff855-127">.NET Framework의 포괄적인 개요 및 추가 리소스에 대한 링크를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ff855-127">Provides a comprehensive overview of the .NET Framework and links to additional resources.</span></span>

* [<span data-ttu-id="ff855-128">설치 가이드</span><span class="sxs-lookup"><span data-stu-id="ff855-128">Installation Guide</span></span>](./install/index.md)  
<span data-ttu-id="ff855-129">.NET Framework 설치 및 문제 해결에 대한 리소스와 지침을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ff855-129">Provides resources and guidance about .NET Framework installation and troubleshooting.</span></span>

* [<span data-ttu-id="ff855-130">마이그레이션 가이드</span><span class="sxs-lookup"><span data-stu-id="ff855-130">Migration Guide</span></span>](./migration-guide/index.md)  
<span data-ttu-id="ff855-131">애플리케이션을 새 버전의 .NET Framework로 마이그레이션하는 경우 고려해야 할 리소스 및 변경 내용 목록을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ff855-131">Provides resources and a list of changes you need to consider if you're migrating your application to a new version of the .NET Framework.</span></span>

* [<span data-ttu-id="ff855-132">개발 가이드</span><span class="sxs-lookup"><span data-stu-id="ff855-132">Development Guide</span></span>](./development-guide.md)  
<span data-ttu-id="ff855-133">만들기, 구성, 디버깅, 보안, 애플리케이션 배포, 동적 프로그래밍에 대한 정보, 상호 운용성, 확장성, 메모리 관리 및 스레딩을 포함하여 애플리케이션 개발에 대한 모든 주요 기술 분야 및 작업에 대한 지침을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ff855-133">Provides a guide to all key technology areas and tasks for application development, including creating, configuring, debugging, securing, and deploying your application, and information about dynamic programming, interoperability, extensibility, memory management, and threading.</span></span>

* [<span data-ttu-id="ff855-134">도구</span><span class="sxs-lookup"><span data-stu-id="ff855-134">Tools</span></span>](./tools/index.md)  
<span data-ttu-id="ff855-135">.NET Framework 기술을 사용하여 애플리케이션을 개발, 구성 및 배포하는 데 도움이 되는 도구에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ff855-135">Describes the tools that help you develop, configure, and deploy applications by using .NET Framework technologies.</span></span>

* [<span data-ttu-id="ff855-136">추가 클래스 라이브러리 및 API</span><span class="sxs-lookup"><span data-stu-id="ff855-136">Additional class libraries and APIs</span></span>](./additional-apis/index.md)  
<span data-ttu-id="ff855-137">Microsoft 도구에서 사용되는 전용 .NET Framework API에 대한 설명서를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ff855-137">Provides documentation for private .NET Framework APIs used by Microsoft tools.</span></span>

## <a name="see-also"></a><span data-ttu-id="ff855-138">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ff855-138">See also</span></span>

* [<span data-ttu-id="ff855-139">.NET Framework 클래스 라이브러리</span><span class="sxs-lookup"><span data-stu-id="ff855-139">.NET Framework Class Library</span></span>](/dotnet/api/?view=netframework-4.8)
