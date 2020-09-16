---
title: Windows 서비스 애플리케이션 개발
description: Visual Studio 또는 .NET SDK를 사용하여 Windows 서비스 앱을 개발하는 방법을 설명하는 문서에 대한 링크를 참조하세요.
ms.date: 03/30/2017
helpviewer_keywords:
- ServiceInstaller class, Windows Service applications
- Service class, Windows Service applications
- Windows Service applications
- Windows NT services
- ServiceProcessInstaller class, Windows Service applications
- services
- .NET applications, Windows applications
ms.assetid: ba72d648-9553-4849-b829-069ad5ea014b
author: ghogen
ms.openlocfilehash: 1f02b8229c0d62fa6c0e74ae1e670831b0becb0b
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "90557803"
---
# <a name="develop-windows-service-apps"></a><span data-ttu-id="95984-103">Windows 서비스 앱 개발</span><span class="sxs-lookup"><span data-stu-id="95984-103">Develop Windows service apps</span></span>

<span data-ttu-id="95984-104">Visual Studio 또는 .NET Framework SDK를 사용하면 서비스로 설치되는 애플리케이션을 만들어 서비스를 쉽게 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95984-104">Using Visual Studio or the .NET Framework SDK, you can easily create services by creating an application that is installed as a service.</span></span> <span data-ttu-id="95984-105">이 유형의 애플리케이션을 Windows 서비스라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="95984-105">This type of application is called a Windows service.</span></span> <span data-ttu-id="95984-106">프레임워크 기능을 사용하여 서비스를 만들고 설치하고 시작 및 중지할 수 있으며 서비스 동작을 제어할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95984-106">With framework features, you can create services, install them, and start, stop, and otherwise control their behavior.</span></span>

> [!NOTE]
> <span data-ttu-id="95984-107">Visual Studio에서는 필요한 경우 기존 C++ 코드와 상호 운용될 수 있는 Visual C# 또는 Visual Basic의 관리 코드에서 서비스를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95984-107">In Visual Studio you can create a service in managed code in Visual C# or Visual Basic, which can interoperate with existing C++ code if required.</span></span> <span data-ttu-id="95984-108">또는 [ATL 프로젝트 마법사](/cpp/atl/reference/atl-project-wizard)를 사용하여 네이티브 C++에서 Windows 서비스를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95984-108">Or, you can create a Windows service in native C++ by using the [ATL Project Wizard](/cpp/atl/reference/atl-project-wizard).</span></span>

## <a name="in-this-section"></a><span data-ttu-id="95984-109">단원 내용</span><span class="sxs-lookup"><span data-stu-id="95984-109">In this section</span></span>

[<span data-ttu-id="95984-110">Windows 서비스 애플리케이션 소개</span><span class="sxs-lookup"><span data-stu-id="95984-110">Introduction to Windows Service Applications</span></span>](introduction-to-windows-service-applications.md)

<span data-ttu-id="95984-111">Windows 서비스 애플리케이션, 서비스 수명 및 서비스 애플리케이션이 다른 일반적인 프로젝트 유형과 다른 점에 대해 간략히 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="95984-111">Provides an overview of Windows service applications, the lifetime of a service, and how service applications differ from other common project types.</span></span>

[<span data-ttu-id="95984-112">연습: 구성 요소 디자이너에서 Windows 서비스 애플리케이션 만들기</span><span class="sxs-lookup"><span data-stu-id="95984-112">Walkthrough: Creating a Windows Service Application in the Component Designer</span></span>](walkthrough-creating-a-windows-service-application-in-the-component-designer.md)

<span data-ttu-id="95984-113">Visual Basic 및 Visual C#에서 서비스를 만드는 예제를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="95984-113">Provides an example of creating a service in Visual Basic and Visual C#.</span></span>

[<span data-ttu-id="95984-114">서비스 애플리케이션 프로그래밍 아키텍처</span><span class="sxs-lookup"><span data-stu-id="95984-114">Service Application Programming Architecture</span></span>](service-application-programming-architecture.md)

<span data-ttu-id="95984-115">서비스 프로그래밍에서 사용되는 언어 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="95984-115">Explains the language elements used in service programming.</span></span>

[<span data-ttu-id="95984-116">방법: Windows 서비스 만들기</span><span class="sxs-lookup"><span data-stu-id="95984-116">How to: Create Windows Services</span></span>](how-to-create-windows-services.md)

<span data-ttu-id="95984-117">Windows 서비스 프로젝트 템플릿을 사용하여 Windows 서비스를 만들고 구성하는 프로세스에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="95984-117">Describes the process of creating and configuring Windows services using the Windows service project template.</span></span>

## <a name="related-sections"></a><span data-ttu-id="95984-118">관련 단원</span><span class="sxs-lookup"><span data-stu-id="95984-118">Related sections</span></span>

<span data-ttu-id="95984-119"><xref:System.ServiceProcess.ServiceBase> - 서비스를 만드는 데 사용되는 <xref:System.ServiceProcess.ServiceBase> 클래스의 주요 기능에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="95984-119"><xref:System.ServiceProcess.ServiceBase> - Describes the major features of the <xref:System.ServiceProcess.ServiceBase> class, which is used to create services.</span></span>

<span data-ttu-id="95984-120"><xref:System.ServiceProcess.ServiceProcessInstaller> - 서비스를 설치 및 제거하기 위해 <xref:System.ServiceProcess.ServiceInstaller> 클래스와 함께 사용되는 <xref:System.ServiceProcess.ServiceProcessInstaller> 클래스의 기능에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="95984-120"><xref:System.ServiceProcess.ServiceProcessInstaller> - Describes the features of the <xref:System.ServiceProcess.ServiceProcessInstaller> class, which is used along with the <xref:System.ServiceProcess.ServiceInstaller> class to install and uninstall your services.</span></span>

<span data-ttu-id="95984-121"><xref:System.ServiceProcess.ServiceInstaller> - 서비스를 설치 및 제거하기 위해 <xref:System.ServiceProcess.ServiceProcessInstaller> 클래스와 함께 사용되는 <xref:System.ServiceProcess.ServiceInstaller> 클래스의 기능에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="95984-121"><xref:System.ServiceProcess.ServiceInstaller> - Describes the features of the <xref:System.ServiceProcess.ServiceInstaller> class, which is used along with the <xref:System.ServiceProcess.ServiceProcessInstaller> class to install and uninstall your service.</span></span>

<span data-ttu-id="95984-122">[템플릿에서 프로젝트 만들기](/previous-versions/visualstudio/visual-studio-2013/0fyc0azh(v=vs.120)) - 이 챕터에서 사용되는 프로젝트 유형과 이들 유형 중에서 선택하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="95984-122">[Create Projects from Templates](/previous-versions/visualstudio/visual-studio-2013/0fyc0azh(v=vs.120)) -  Describes the projects types used in this chapter and how to choose between them.</span></span>
