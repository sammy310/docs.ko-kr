---
title: Windows 컨테이너에 배포하면 안 되는 경우
description: Azure 클라우드와 Windows 컨테이너를 사용하여 기존 .NET 응용 프로그램 최신화 | Windows 컨테이너를 배포하지 않는 경우
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 04/28/2018
ms.openlocfilehash: c5d8f50c7b9967eba0ec01c9e864a02b6a3b201a
ms.sourcegitcommit: 438919211260bb415fc8f96ca3eabc33cf2d681d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2019
ms.locfileid: "59611941"
---
# <a name="when-not-to-deploy-to-windows-containers"></a><span data-ttu-id="3b2c6-103">Windows 컨테이너에 배포하면 안 되는 경우</span><span class="sxs-lookup"><span data-stu-id="3b2c6-103">When not to deploy to Windows Containers</span></span>

<span data-ttu-id="3b2c6-104">일부 Windows 기술은 Windows 컨테이너에서 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3b2c6-104">Some Windows technologies are not supported by Windows Containers.</span></span> <span data-ttu-id="3b2c6-105">이러한 경우 일반적으로 Windows와 IIS만 사용하여 표준 VM에 마이그레이션해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b2c6-105">In those cases, you still need to migrate to standards VMs, usually with just Windows and IIS.</span></span>

<span data-ttu-id="3b2c6-106">2018년 5월 기준으로 Windows 컨테이너에서 지원되지 않는 경우는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="3b2c6-106">Cases not supported in Windows Containers, as of May 2018:</span></span> 

-   <span data-ttu-id="3b2c6-107">현재 Microsoft 메시지 큐(MSMQ)는 다른 이전 릴리스에서는 사용할 수 없고 Windows Server v1803 릴리스 기반의 Windows 컨테이너에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b2c6-107">Microsoft Message Queuing (MSMQ) currently is only available in Windows Containers based on Windows Server v1803 release, but not in any other prior releases.</span></span> 

    -   [<span data-ttu-id="3b2c6-108">UserVoice 요청 포럼</span><span class="sxs-lookup"><span data-stu-id="3b2c6-108">UserVoice request forum</span></span>](https://windowsserver.uservoice.com/forums/304624-containers/suggestions/15719031-create-base-container-image-with-msmq-server)

    -   [<span data-ttu-id="3b2c6-109">토론 포럼</span><span class="sxs-lookup"><span data-stu-id="3b2c6-109">Discussion forum</span></span>](https://social.msdn.microsoft.com/Forums/bce99a7d-aa60-44fa-a348-450855650810/msmqserver-is-it-supported?forum=windowscontainers)

-   <span data-ttu-id="3b2c6-110">Microsoft Distributed Transaction Coordinator(MSDTC)는 현재 Windows 컨테이너에서 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3b2c6-110">Microsoft Distributed Transaction Coordinator (MSDTC) currently is not supported in Windows Containers.</span></span>

    -   [<span data-ttu-id="3b2c6-111">GitHub 문제</span><span class="sxs-lookup"><span data-stu-id="3b2c6-111">GitHub issue</span></span>](https://github.com/MicrosoftDocs/Virtualization-Documentation/issues/494)

-   <span data-ttu-id="3b2c6-112">현재 Microsoft Office는 컨테이너를 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3b2c6-112">Microsoft Office currently does not support containers.</span></span>

    -   [<span data-ttu-id="3b2c6-113">UserVoice 요청 포럼</span><span class="sxs-lookup"><span data-stu-id="3b2c6-113">UserVoice request forum</span></span>](https://windowsserver.uservoice.com/forums/304624-containers/suggestions/19686220-provide-office-support-for-containers)

-   <span data-ttu-id="3b2c6-114">UI 앱(시각적 사용자 인터페이스를 사용한 클라이언트 앱)은 지원되는 시나리오가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="3b2c6-114">UI apps (client apps with a visual user interface) are not supported scenarios.</span></span>

-   <span data-ttu-id="3b2c6-115">Windows 인프라 역할(DNS, DHCP, DC, NTP, 인쇄, 파일 서버, IAM 등)은 지원되는 시나리오가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="3b2c6-115">Windows infrastructure roles (DNS, DHCP, DC, NTP, PRINT, File server, IAM etc.) are not supported scenarios.</span></span>

<span data-ttu-id="3b2c6-116">지원되지 않는 더 많은 시나리오와 커뮤니티의 요청은 다음의 Windows 컨테이너의 UserVoice 포럼을 참조하세요: <https://windowsserver.uservoice.com/forums/304624-containers></span><span class="sxs-lookup"><span data-stu-id="3b2c6-116">For additional not-supported scenarios and requests from the community, see the UserVoice forum for Windows Containers: <https://windowsserver.uservoice.com/forums/304624-containers>.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="3b2c6-117">추가 자료</span><span class="sxs-lookup"><span data-stu-id="3b2c6-117">Additional resources</span></span>

-   <span data-ttu-id="3b2c6-118">**Virtual machine과 Azure의 컨테이너**</span><span class="sxs-lookup"><span data-stu-id="3b2c6-118">**Virtual machines and containers in Azure**</span></span>

    <https://azure.microsoft.com/overview/containers/>

>[!div class="step-by-step"]
><span data-ttu-id="3b2c6-119">[이전](deploy-existing-net-apps-as-windows-containers.md)
>[다음](when-to-deploy-windows-containers-in-your-on-premises-iaas-vm-infrastructure.md)</span><span class="sxs-lookup"><span data-stu-id="3b2c6-119">[Previous](deploy-existing-net-apps-as-windows-containers.md)
[Next](when-to-deploy-windows-containers-in-your-on-premises-iaas-vm-infrastructure.md)</span></span>
