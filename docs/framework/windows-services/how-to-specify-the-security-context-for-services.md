---
title: '방법: 서비스에 대한 보안 컨텍스트 지정'
description: 서비스에 대한 보안 컨텍스트를 지정합니다. 기본 시스템 계정 컨텍스트에서 실행되는 서비스에는 로그인한 사용자와 다른 시스템 리소스 액세스 권한이 있습니다.
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Service applications, security
- security [Visual Studio], contexts
- contexts, Visual Studio security
- security [Visual Studio], service applications
- ServiceProcessInstaller class, security context
- services, security
- ServiceInstaller class, security context
ms.assetid: 02187c7b-dbf2-45f2-96c2-e11010225a22
ms.openlocfilehash: dcf0680f1bcb0f0e927bdb37ea56f7b3025be09b
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96270539"
---
# <a name="how-to-specify-the-security-context-for-services"></a><span data-ttu-id="a1a99-104">방법: 서비스에 대한 보안 컨텍스트 지정</span><span class="sxs-lookup"><span data-stu-id="a1a99-104">How to: Specify the Security Context for Services</span></span>

<span data-ttu-id="a1a99-105">기본적으로 서비스는 로그인한 사용자와 다른 보안 컨텍스트에서 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="a1a99-105">By default, services run in a different security context than that of the logged-in user.</span></span> <span data-ttu-id="a1a99-106">서비스는 기본 시스템 계정 `LocalSystem`의 컨텍스트에서 실행되므로, 시스템 리소스에 대해 사용자와는 다른 액세스 권한을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="a1a99-106">Services run in the context of the default system account, called `LocalSystem`, which gives them different access privileges to system resources than the user.</span></span> <span data-ttu-id="a1a99-107">이 동작을 변경하여 서비스를 실행할 다른 사용자 계정을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1a99-107">You can change this behavior to specify a different user account under which your service should run.</span></span>  
  
 <span data-ttu-id="a1a99-108">보안 컨텍스트는 서비스가 실행되는 프로세스에 대한 <xref:System.ServiceProcess.ServiceProcessInstaller.Account%2A> 속성을 조작하여 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="a1a99-108">You set the security context by manipulating the <xref:System.ServiceProcess.ServiceProcessInstaller.Account%2A> property for the process within which the service runs.</span></span> <span data-ttu-id="a1a99-109">이 속성을 사용하면 서비스를 다음 네 가지 계정 유형 중 하나로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1a99-109">This property allows you to set the service to one of four account types:</span></span>  
  
- <span data-ttu-id="a1a99-110">`User` - 네트워크의 단일 사용자가 지정한 계정의 컨텐스트에서 서비스가 설치 및 실행될 때 시스템에서 유효한 사용자 이름과 암호를 묻는 메시지를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="a1a99-110">`User`, which causes the system to prompt for a valid user name and password when the service is installed and runs in the context of an account specified by a single user on the network;</span></span>  
  
- <span data-ttu-id="a1a99-111">`LocalService` - 로컬 컴퓨터에서 권한 없는 사용자의 역할을 하며 원격 서버에 익명 자격 증명을 제공하는 계정의 컨텍스트에서 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="a1a99-111">`LocalService`, which runs in the context of an account that acts as a non-privileged user on the local computer, and presents anonymous credentials to any remote server;</span></span>  
  
- <span data-ttu-id="a1a99-112">`LocalSystem` - 광범위한 로컬 권한을 제공하며 원격 서버에 컴퓨터의 자격 증명을 제공하는 계정의 컨텍스트에서 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="a1a99-112">`LocalSystem`, which runs in the context of an account that provides extensive local privileges, and presents the computer's credentials to any remote server;</span></span>  
  
- <span data-ttu-id="a1a99-113">`NetworkService` - 로컬 컴퓨터에서 권한 없는 사용자 역할을 하며 원격 서버에 컴퓨터의 자격 증명을 제공하는 계정의 컨텍스트에서 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="a1a99-113">`NetworkService`, which runs in the context of an account that acts as a non-privileged user on the local computer, and presents the computer's credentials to any remote server.</span></span>  
  
 <span data-ttu-id="a1a99-114">자세한 내용은 <xref:System.ServiceProcess.ServiceAccount> 열거형을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a1a99-114">For more information, see the <xref:System.ServiceProcess.ServiceAccount> enumeration.</span></span>  
  
### <a name="to-specify-the-security-context-for-a-service"></a><span data-ttu-id="a1a99-115">서비스에 대한 보안 컨텍스트를 지정하려면</span><span class="sxs-lookup"><span data-stu-id="a1a99-115">To specify the security context for a service</span></span>  
  
1. <span data-ttu-id="a1a99-116">서비스를 만든 후 서비스에 필요한 설치 관리자를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a1a99-116">After creating your service, add the necessary installers for it.</span></span> <span data-ttu-id="a1a99-117">자세한 내용은 [방법: 서비스 애플리케이션에 설치 관리자 추가](how-to-add-installers-to-your-service-application.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a1a99-117">For more information, see [How to: Add Installers to Your Service Application](how-to-add-installers-to-your-service-application.md).</span></span>  
  
2. <span data-ttu-id="a1a99-118">디자이너에서 `ProjectInstaller` 클래스에 액세스하고 작업 중인 서비스에 대한 서비스 프로세스 설치 관리자를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a1a99-118">In the designer, access the `ProjectInstaller` class and click the service process installer for the service you are working with.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="a1a99-119">모든 서비스 애플리케이션의 `ProjectInstaller` 클래스에는 적어도 두 개의 설치 구성 요소가 있는데, 프로젝트의 모든 서비스에 대한 프로세스를 설치하는 구성 요소와 애플리케이션에 포함된 각 서비스에 대한 설치 관리자 1개입니다.</span><span class="sxs-lookup"><span data-stu-id="a1a99-119">For every service application, there are at least two installation components in the `ProjectInstaller` class — one that installs the processes for all services in the project, and one installer for each service the application contains.</span></span> <span data-ttu-id="a1a99-120">이 인스턴스에서 <xref:System.ServiceProcess.ServiceProcessInstaller>을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1a99-120">In this instance, you want to select <xref:System.ServiceProcess.ServiceProcessInstaller>.</span></span>  
  
3. <span data-ttu-id="a1a99-121">**속성** 창에서 <xref:System.ServiceProcess.ServiceProcessInstaller.Account%2A>를 적절한 값으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="a1a99-121">In the **Properties** window, set the <xref:System.ServiceProcess.ServiceProcessInstaller.Account%2A> to the appropriate value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1a99-122">참조</span><span class="sxs-lookup"><span data-stu-id="a1a99-122">See also</span></span>

- [<span data-ttu-id="a1a99-123">Windows 서비스 애플리케이션 소개</span><span class="sxs-lookup"><span data-stu-id="a1a99-123">Introduction to Windows Service Applications</span></span>](introduction-to-windows-service-applications.md)
- [<span data-ttu-id="a1a99-124">방법: 서비스 애플리케이션에 설치 관리자 추가</span><span class="sxs-lookup"><span data-stu-id="a1a99-124">How to: Add Installers to Your Service Application</span></span>](how-to-add-installers-to-your-service-application.md)
- [<span data-ttu-id="a1a99-125">방법: Windows 서비스 만들기</span><span class="sxs-lookup"><span data-stu-id="a1a99-125">How to: Create Windows Services</span></span>](how-to-create-windows-services.md)
