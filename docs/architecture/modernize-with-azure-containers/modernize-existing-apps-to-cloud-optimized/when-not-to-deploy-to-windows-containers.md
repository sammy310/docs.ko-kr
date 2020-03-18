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
# <a name="when-not-to-deploy-to-windows-containers"></a>Windows 컨테이너에 배포하면 안 되는 경우

일부 Windows 기술은 Windows 컨테이너에서 지원되지 않습니다. 이러한 경우에도 일반적으로 Windows 및 IIS만 표준 VM으로 마이그레이션해야 합니다.

2018년 5월 현재 Windows 컨테이너에서 지원되지 않는 사례는 다음과 같습니다.

- 현재 MSMQ(Microsoft Message Queuing)는 Windows Server v1803 릴리스를 기반으로 하는 Windows 컨테이너에서만 사용할 수 있지만 다른 이전 릴리스에서는 사용할 수 없습니다.

  - [UserVoice 요청 포럼](https://windowsserver.uservoice.com/forums/304624-containers/suggestions/15719031-create-base-container-image-with-msmq-server)

  - [토론 포럼](https://social.msdn.microsoft.com/Forums/bce99a7d-aa60-44fa-a348-450855650810/msmqserver-is-it-supported?forum=windowscontainers)

- MSDTC(Microsoft Distributed Transaction Coordinator)는 현재 Windows 컨테이너에서 지원되지 않습니다.

  - [GitHub 문제](https://github.com/MicrosoftDocs/Virtualization-Documentation/issues/494)

- 현재 Microsoft Office는 컨테이너를 지원하지 않습니다.

  - [UserVoice 요청 포럼](https://windowsserver.uservoice.com/forums/304624-containers/suggestions/19686220-provide-office-support-for-containers)

- UI 앱(시각적 사용자 인터페이스가 있는 클라이언트 앱)은 지원되는 시나리오가 아닙니다.

- Windows 인프라 역할(DNS, DHCP, DC, NTP, PRINT, File server, IAM 등)은 지원되는 시나리오가 아닙니다.

커뮤니티에서 지원되지 않는 추가 시나리오 및 요청은 Windows 컨테이너에 대한 UserVoice 포럼을 참조하세요. <https://windowsserver.uservoice.com/forums/304624-containers>.

### <a name="additional-resources"></a>추가 자료

- **Azure의 가상 머신 및 컨테이너**

    <https://azure.microsoft.com/overview/containers/>

> [!div class="step-by-step"]
> [이전](deploy-existing-net-apps-as-windows-containers.md)
> [다음](when-to-deploy-windows-containers-in-your-on-premises-iaas-vm-infrastructure.md)
