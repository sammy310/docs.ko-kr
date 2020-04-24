---
title: Windows 서비스 애플리케이션 개발
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
ms.openlocfilehash: 61f969c22ac06bd6ed20ccfa9124db3bb35d0692
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2020
ms.locfileid: "71053550"
---
# <a name="develop-windows-service-apps"></a><span data-ttu-id="d7332-102">Windows 서비스 앱 개발</span><span class="sxs-lookup"><span data-stu-id="d7332-102">Develop Windows service apps</span></span>

<span data-ttu-id="d7332-103">Visual Studio 또는 .NET Framework SDK를 사용하면 서비스로 설치되는 애플리케이션을 만들어 서비스를 쉽게 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7332-103">Using Visual Studio or the .NET Framework SDK, you can easily create services by creating an application that is installed as a service.</span></span> <span data-ttu-id="d7332-104">이 유형의 애플리케이션을 Windows 서비스라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7332-104">This type of application is called a Windows service.</span></span> <span data-ttu-id="d7332-105">프레임워크 기능을 사용하여 서비스를 만들고 설치하고 시작 및 중지할 수 있으며 서비스 동작을 제어할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7332-105">With framework features, you can create services, install them, and start, stop, and otherwise control their behavior.</span></span>

> [!NOTE]
> <span data-ttu-id="d7332-106">Visual Studio에서는 필요한 경우 기존 C++ 코드와 상호 운용될 수 있는 Visual C# 또는 Visual Basic의 관리 코드에서 서비스를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7332-106">In Visual Studio you can create a service in managed code in Visual C# or Visual Basic, which can interoperate with existing C++ code if required.</span></span> <span data-ttu-id="d7332-107">또는 [ATL 프로젝트 마법사](/cpp/atl/reference/atl-project-wizard)를 사용하여 네이티브 C++에서 Windows 서비스를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7332-107">Or, you can create a Windows service in native C++ by using the [ATL Project Wizard](/cpp/atl/reference/atl-project-wizard).</span></span>

## <a name="in-this-section"></a><span data-ttu-id="d7332-108">단원 내용</span><span class="sxs-lookup"><span data-stu-id="d7332-108">In this section</span></span>

[<span data-ttu-id="d7332-109">Windows 서비스 애플리케이션 소개</span><span class="sxs-lookup"><span data-stu-id="d7332-109">Introduction to Windows Service Applications</span></span>](introduction-to-windows-service-applications.md)

<span data-ttu-id="d7332-110">Windows 서비스 애플리케이션, 서비스 수명 및 서비스 애플리케이션이 다른 일반적인 프로젝트 유형과 다른 점에 대해 간략히 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d7332-110">Provides an overview of Windows service applications, the lifetime of a service, and how service applications differ from other common project types.</span></span>

[<span data-ttu-id="d7332-111">연습: 구성 요소 디자이너에서 Windows 서비스 애플리케이션 만들기</span><span class="sxs-lookup"><span data-stu-id="d7332-111">Walkthrough: Creating a Windows Service Application in the Component Designer</span></span>](walkthrough-creating-a-windows-service-application-in-the-component-designer.md)

<span data-ttu-id="d7332-112">Visual Basic 및 Visual C#에서 서비스를 만드는 예제를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d7332-112">Provides an example of creating a service in Visual Basic and Visual C#.</span></span>

[<span data-ttu-id="d7332-113">서비스 애플리케이션 프로그래밍 아키텍처</span><span class="sxs-lookup"><span data-stu-id="d7332-113">Service Application Programming Architecture</span></span>](service-application-programming-architecture.md)

<span data-ttu-id="d7332-114">서비스 프로그래밍에서 사용되는 언어 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d7332-114">Explains the language elements used in service programming.</span></span>

[<span data-ttu-id="d7332-115">방법: Windows 서비스 만들기</span><span class="sxs-lookup"><span data-stu-id="d7332-115">How to: Create Windows Services</span></span>](how-to-create-windows-services.md)

<span data-ttu-id="d7332-116">Windows 서비스 프로젝트 템플릿을 사용하여 Windows 서비스를 만들고 구성하는 프로세스에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d7332-116">Describes the process of creating and configuring Windows services using the Windows service project template.</span></span>

## <a name="related-sections"></a><span data-ttu-id="d7332-117">관련 단원</span><span class="sxs-lookup"><span data-stu-id="d7332-117">Related sections</span></span>

<span data-ttu-id="d7332-118"><xref:System.ServiceProcess.ServiceBase> - 서비스를 만드는 데 사용되는 <xref:System.ServiceProcess.ServiceBase> 클래스의 주요 기능에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d7332-118"><xref:System.ServiceProcess.ServiceBase> - Describes the major features of the <xref:System.ServiceProcess.ServiceBase> class, which is used to create services.</span></span>

<span data-ttu-id="d7332-119"><xref:System.ServiceProcess.ServiceProcessInstaller> - 서비스를 설치 및 제거하기 위해 <xref:System.ServiceProcess.ServiceInstaller> 클래스와 함께 사용되는 <xref:System.ServiceProcess.ServiceProcessInstaller> 클래스의 기능에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d7332-119"><xref:System.ServiceProcess.ServiceProcessInstaller> - Describes the features of the <xref:System.ServiceProcess.ServiceProcessInstaller> class, which is used along with the <xref:System.ServiceProcess.ServiceInstaller> class to install and uninstall your services.</span></span>

<span data-ttu-id="d7332-120"><xref:System.ServiceProcess.ServiceInstaller> - 서비스를 설치 및 제거하기 위해 <xref:System.ServiceProcess.ServiceProcessInstaller> 클래스와 함께 사용되는 <xref:System.ServiceProcess.ServiceInstaller> 클래스의 기능에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d7332-120"><xref:System.ServiceProcess.ServiceInstaller> - Describes the features of the <xref:System.ServiceProcess.ServiceInstaller> class, which is used along with the <xref:System.ServiceProcess.ServiceProcessInstaller> class to install and uninstall your service.</span></span>

<span data-ttu-id="d7332-121">[템플릿에서 프로젝트 만들기](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/0fyc0azh(v=vs.120)) - 이 챕터에서 사용되는 프로젝트 유형과 이들 유형 중에서 선택하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d7332-121">[Create Projects from Templates](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/0fyc0azh(v=vs.120)) -  Describes the projects types used in this chapter and how to choose between them.</span></span>
