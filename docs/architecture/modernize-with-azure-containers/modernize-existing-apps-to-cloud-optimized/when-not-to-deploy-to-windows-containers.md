---
title: Windows 컨테이너에 배포하면 안 되는 경우
description: Azure Cloud 및 Windows 컨테이너를 사용하여 기존 .NET 애플리케이션 현대화 | Windows 컨테이너에 배포하면 안 되는 경우
ms.date: 04/28/2018
ms.openlocfilehash: 65e793b846b495e9a1be6db9ddfa38bbf0d49445
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "69577956"
---
# <a name="when-not-to-deploy-to-windows-containers"></a><span data-ttu-id="1b677-103">Windows 컨테이너에 배포하면 안 되는 경우</span><span class="sxs-lookup"><span data-stu-id="1b677-103">When not to deploy to Windows Containers</span></span>

<span data-ttu-id="1b677-104">일부 Windows 기술은 Windows 컨테이너에서 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1b677-104">Some Windows technologies are not supported by Windows Containers.</span></span> <span data-ttu-id="1b677-105">이러한 경우에도 일반적으로 Windows 및 IIS만 표준 VM으로 마이그레이션해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b677-105">In those cases, you still need to migrate to standards VMs, usually with just Windows and IIS.</span></span>

<span data-ttu-id="1b677-106">2018년 5월 현재 Windows 컨테이너에서 지원되지 않는 사례는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="1b677-106">Cases not supported in Windows Containers, as of May 2018:</span></span>

- <span data-ttu-id="1b677-107">현재 MSMQ(Microsoft Message Queuing)는 Windows Server v1803 릴리스를 기반으로 하는 Windows 컨테이너에서만 사용할 수 있지만 다른 이전 릴리스에서는 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1b677-107">Microsoft Message Queuing (MSMQ) currently is only available in Windows Containers based on Windows Server v1803 release, but not in any other prior releases.</span></span>

  - [<span data-ttu-id="1b677-108">UserVoice 요청 포럼</span><span class="sxs-lookup"><span data-stu-id="1b677-108">UserVoice request forum</span></span>](https://windowsserver.uservoice.com/forums/304624-containers/suggestions/15719031-create-base-container-image-with-msmq-server)

  - [<span data-ttu-id="1b677-109">토론 포럼</span><span class="sxs-lookup"><span data-stu-id="1b677-109">Discussion forum</span></span>](https://social.msdn.microsoft.com/Forums/bce99a7d-aa60-44fa-a348-450855650810/msmqserver-is-it-supported?forum=windowscontainers)

- <span data-ttu-id="1b677-110">MSDTC(Microsoft Distributed Transaction Coordinator)는 현재 Windows 컨테이너에서 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1b677-110">Microsoft Distributed Transaction Coordinator (MSDTC) currently is not supported in Windows Containers.</span></span>

  - [<span data-ttu-id="1b677-111">GitHub 문제</span><span class="sxs-lookup"><span data-stu-id="1b677-111">GitHub issue</span></span>](https://github.com/MicrosoftDocs/Virtualization-Documentation/issues/494)

- <span data-ttu-id="1b677-112">현재 Microsoft Office는 컨테이너를 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1b677-112">Microsoft Office currently does not support containers.</span></span>

  - [<span data-ttu-id="1b677-113">UserVoice 요청 포럼</span><span class="sxs-lookup"><span data-stu-id="1b677-113">UserVoice request forum</span></span>](https://windowsserver.uservoice.com/forums/304624-containers/suggestions/19686220-provide-office-support-for-containers)

- <span data-ttu-id="1b677-114">UI 앱(시각적 사용자 인터페이스가 있는 클라이언트 앱)은 지원되는 시나리오가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="1b677-114">UI apps (client apps with a visual user interface) are not supported scenarios.</span></span>

- <span data-ttu-id="1b677-115">Windows 인프라 역할(DNS, DHCP, DC, NTP, PRINT, File server, IAM 등)은 지원되는 시나리오가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="1b677-115">Windows infrastructure roles (DNS, DHCP, DC, NTP, PRINT, File server, IAM etc.) are not supported scenarios.</span></span>

<span data-ttu-id="1b677-116">커뮤니티에서 지원되지 않는 추가 시나리오 및 요청은 Windows 컨테이너에 대한 UserVoice 포럼을 참조하세요. <https://windowsserver.uservoice.com/forums/304624-containers>.</span><span class="sxs-lookup"><span data-stu-id="1b677-116">For additional not-supported scenarios and requests from the community, see the UserVoice forum for Windows Containers: <https://windowsserver.uservoice.com/forums/304624-containers>.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="1b677-117">추가 자료</span><span class="sxs-lookup"><span data-stu-id="1b677-117">Additional resources</span></span>

- <span data-ttu-id="1b677-118">**Azure의 가상 머신 및 컨테이너**</span><span class="sxs-lookup"><span data-stu-id="1b677-118">**Virtual machines and containers in Azure**</span></span>

    <https://azure.microsoft.com/overview/containers/>

> [!div class="step-by-step"]
> <span data-ttu-id="1b677-119">[이전](deploy-existing-net-apps-as-windows-containers.md)
> [다음](when-to-deploy-windows-containers-in-your-on-premises-iaas-vm-infrastructure.md)</span><span class="sxs-lookup"><span data-stu-id="1b677-119">[Previous](deploy-existing-net-apps-as-windows-containers.md)
[Next](when-to-deploy-windows-containers-in-your-on-premises-iaas-vm-infrastructure.md)</span></span>
