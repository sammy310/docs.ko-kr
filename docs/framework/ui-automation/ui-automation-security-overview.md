---
title: UI 자동화 보안 개요
ms.date: 03/30/2017
helpviewer_keywords:
- UI Automation, security model
- security model, UI Automation
ms.assetid: 1d853695-973c-48ae-b382-4132ae702805
ms.openlocfilehash: c74f770f917fc3b2a7d3a18c08270745dac68b12
ms.sourcegitcommit: 9b1ac36b6c80176fd4e20eb5bfcbd9d56c3264cf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/28/2019
ms.locfileid: "67422428"
---
# <a name="ui-automation-security-overview"></a><span data-ttu-id="8df45-102">UI 자동화 보안 개요</span><span class="sxs-lookup"><span data-stu-id="8df45-102">UI Automation Security Overview</span></span>

> [!NOTE]
> <span data-ttu-id="8df45-103">이 설명서는 <xref:System.Windows.Automation> 네임스페이스에 정의된 관리되는 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 클래스를 사용하려는 .NET Framework 개발자를 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="8df45-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="8df45-104">에 대 한 최신 정보에 대 한 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]를 참조 하세요 [Windows Automation API: UI 자동화](https://go.microsoft.com/fwlink/?LinkID=156746)합니다.</span><span class="sxs-lookup"><span data-stu-id="8df45-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>

<span data-ttu-id="8df45-105">이 개요에서는 [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] 의 [!INCLUDE[TLA#tla_winvista](../../../includes/tlasharptla-winvista-md.md)]에 대한 보안 모델을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="8df45-105">This overview describes the security model for [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] in [!INCLUDE[TLA#tla_winvista](../../../includes/tlasharptla-winvista-md.md)].</span></span>

<a name="User_Account_Control"></a>

## <a name="user-account-control"></a><span data-ttu-id="8df45-106">사용자 계정 컨트롤</span><span class="sxs-lookup"><span data-stu-id="8df45-106">User Account Control</span></span>

<span data-ttu-id="8df45-107">보안은 [!INCLUDE[TLA#tla_winvista](../../../includes/tlasharptla-winvista-md.md)] 의 중요 사항이며, 혁신적 기능 중에는 사용자가 더 높은 권한이 필요한 애플리케이션과 서비스를 실행할 수 없도록 차단되지 않고 표준(비관리자) 사용자로 실행할 수 있는 기능이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8df45-107">Security is a major focus of [!INCLUDE[TLA#tla_winvista](../../../includes/tlasharptla-winvista-md.md)] and among the innovations is the ability for users to run as standard (non-administrator) users without necessarily being blocked from running applications and services that require higher privileges.</span></span>

<span data-ttu-id="8df45-108">[!INCLUDE[TLA2#tla_winvista](../../../includes/tla2sharptla-winvista-md.md)]에서는 대부분의 응용 프로그램에 표준 또는 관리 토큰이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="8df45-108">In [!INCLUDE[TLA2#tla_winvista](../../../includes/tla2sharptla-winvista-md.md)], most applications are supplied with either a standard or an administrative token.</span></span> <span data-ttu-id="8df45-109">애플리케이션을 관리 애플리케이션으로 식별할 수 없는 경우 기본적으로 표준 애플리케이션으로 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="8df45-109">If an application cannot be identified as an administrative application, it is launched as a standard application by default.</span></span> <span data-ttu-id="8df45-110">관리 애플리케이션으로 식별된 애플리케이션을 시작하기 전에 [!INCLUDE[TLA2#tla_winvista](../../../includes/tla2sharptla-winvista-md.md)] 에서 높은 권한으로 애플리케이션을 실행할 것인지 묻는 메시지를 사용자에게 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="8df45-110">Before an application identified as administrative can be launched, [!INCLUDE[TLA2#tla_winvista](../../../includes/tla2sharptla-winvista-md.md)] prompts the user for consent to run the application as elevated.</span></span> <span data-ttu-id="8df45-111">관리자 자격 증명이 필요한 애플리케이션 또는 시스템 구성 요소가 실행 권한을 요청할 때까지 관리자가 표준 사용자로 실행되므로 사용자가 로컬 관리자 그룹의 멤버인 경우에도 동의 확인 프롬프트가 기본적으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="8df45-111">The consent prompt is displayed by default, even if the user is a member of the local Administrators group, because administrators run as standard users until an application or system component that requires administrative credentials requests permission to run.</span></span>

<a name="Tasks_Requiring_Higher_Privileges"></a>

## <a name="tasks-requiring-higher-privileges"></a><span data-ttu-id="8df45-112">더 높은 권한이 필요한 작업</span><span class="sxs-lookup"><span data-stu-id="8df45-112">Tasks Requiring Higher Privileges</span></span>

<span data-ttu-id="8df45-113">사용자가 관리자 권한이 필요한 작업을 수행하려고 [!INCLUDE[TLA2#tla_winvista](../../../includes/tla2sharptla-winvista-md.md)] 에서 사용자에게 계속할 것인지 묻는 대화 상자를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="8df45-113">When a user attempts to perform a task that requires administrative privileges, [!INCLUDE[TLA2#tla_winvista](../../../includes/tla2sharptla-winvista-md.md)] presents a dialog box asking the user for consent to continue.</span></span> <span data-ttu-id="8df45-114">이 대화 상자는 악성 소프트웨어가 사용자 입력을 시뮬레이션할 수 없도록 크로스 프로세스 통신으로부터 보호됩니다.</span><span class="sxs-lookup"><span data-stu-id="8df45-114">This dialog box is protected from cross-process communication, so that malicious software cannot simulate user input.</span></span> <span data-ttu-id="8df45-115">마찬가지로, 데스크톱 로그온 화면은 일반적으로 다른 프로세스에서 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8df45-115">Similarly, the desktop logon screen cannot normally be accessed by other processes.</span></span>

<span data-ttu-id="8df45-116">UI 자동화 클라이언트는 더 높은 권한 수준에서 실행 중일 수도 있는 다른 프로세스와 통신해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8df45-116">UI Automation clients must communicate with other processes, some of them perhaps running at a higher privilege level.</span></span> <span data-ttu-id="8df45-117">클라이언트가 일반적으로 다른 프로세스에 표시되지 않는 시스템 대화 상자에 액세스해야 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8df45-117">Clients also might need access to the system dialog boxes that are not normally visible to other processes.</span></span> <span data-ttu-id="8df45-118">따라서 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 클라이언트는 시스템에서 신뢰되어야 하며 특수 권한으로 실행되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8df45-118">Therefore, [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] clients must be trusted by the system, and must run with special privileges.</span></span>

<span data-ttu-id="8df45-119">더 높은 권한 수준에서 실행 중인 애플리케이션과 통신할 수 있도록 신뢰되려면 애플리케이션에 서명해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8df45-119">To be trusted to communicate with applications running at a higher privilege level, applications must be signed.</span></span>

<a name="Manifest_Files"></a>

## <a name="manifest-files"></a><span data-ttu-id="8df45-120">매니페스트 파일</span><span class="sxs-lookup"><span data-stu-id="8df45-120">Manifest Files</span></span>

<span data-ttu-id="8df45-121">포함 된 매니페스트 파일을 사용 하 여 구축 해야 응용 프로그램 보호 된 시스템 UI에 액세스 합니다 `uiAccess` 특성을 `requestedExecutionLevel` 태그를 다음과 같이:</span><span class="sxs-lookup"><span data-stu-id="8df45-121">To gain access to the protected system UI, applications must be built with a manifest file that includes the `uiAccess` attribute in the `requestedExecutionLevel` tag, as follows:</span></span>

```xml
<trustInfo xmlns="urn:schemas-microsoft-com:asm.v3">
  <security>
    <requestedPrivileges>
      <requestedExecutionLevel
        level="highestAvailable"
        uiAccess="true" />
    </requestedPrivileges>
  </security>
</trustInfo>
```

<span data-ttu-id="8df45-122">이 코드에서 `level` 특성의 값은 예제일 뿐입니다.</span><span class="sxs-lookup"><span data-stu-id="8df45-122">The value of the `level` attribute in this code is an example only.</span></span>

<span data-ttu-id="8df45-123">`uiAccess` 기본적으로 "false" 즉, 특성을 생략 하거나 어셈블리에 대 한 매니페스트가 없을 경우 응용 프로그램은 보호 된 UI에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8df45-123">`uiAccess` is "false" by default; that is, if the attribute is omitted, or if there is no manifest for the assembly, the application will not be able to gain access to protected UI.</span></span>

<span data-ttu-id="8df45-124">에 대 한 자세한 [!INCLUDE[TLA#tla_longhorn2](../../../includes/tlasharptla-longhorn2-md.md)] 보안, 응용 프로그램 서명 및 어셈블리 매니페스트를 만드는 방법에 참조 [Developer Best Practices and Guidelines for Applications는 최소 권한 환경에서](https://docs.microsoft.com/previous-versions/dotnet/articles/aa480150(v=msdn.10))합니다.</span><span class="sxs-lookup"><span data-stu-id="8df45-124">For more information on [!INCLUDE[TLA#tla_longhorn2](../../../includes/tlasharptla-longhorn2-md.md)] security, on signing applications, and on creating assembly manifests, see [Developer Best Practices and Guidelines for Applications in a Least Privileged Environment](https://docs.microsoft.com/previous-versions/dotnet/articles/aa480150(v=msdn.10)).</span></span>
