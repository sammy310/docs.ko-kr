---
title: Microsoft 플랫폼 및 도구를 사용하여 컨테이너화된 Docker 애플리케이션 수명 주기
description: Docker 및 Microsoft 플랫폼과 도구를 사용하여 컨테이너화된 애플리케이션을 개발하고 배포하는 개발 및 배포 프로세스의 대략적인 개요를 확인하세요.
ms.date: 11/10/2020
ms.openlocfilehash: cf20ea97ec252649cdb14add40ead67b6319520a
ms.sourcegitcommit: bc9c63541c3dc756d48a7ce9d22b5583a18cf7fd
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/11/2020
ms.locfileid: "94506664"
---
# <a name="containerized-docker-application-lifecycle-with-microsoft-platform-and-tools"></a>Microsoft 플랫폼 및 도구를 사용하여 컨테이너화된 Docker 애플리케이션 수명 주기

![책 표지](./media/devops-book-cover-large-we.png)

**EDITION v3.1** - ASP.NET Core 3.1로 업데이트되었습니다

책 업데이트 및 커뮤니티 기여에 대한 자세한 내용은 [changelog](https://aka.ms/DockerLifecycleEbookChangelog)를 참조하세요.

이 가이드는 Docker와 Microsoft 플랫폼 및 도구를 사용하여 컨테이너화된 ASP.NET Core 애플리케이션을 개발하고 배포하기 위한 일반적인 개요입니다. 이 가이드는 CI/CD 파이프라인을 구현하기 위한 Azure DevOps뿐만 아니라 배포를 위한 ACR(Azure Container Registry) 및 AKS(Azure Kubernetes Service)도 간략하게 소개합니다.

자세한 개발 관련 세부 정보는 [.NET 마이크로 서비스: 컨테이너화된 .NET 애플리케이션의 아키텍처](../microservices/index.md) 가이드 및 IT 관련 참조 애플리케이션 [eShopOnContainers](https://github.com/dotnet-architecture/eShopOnContainers)를 참조할 수 있습니다.

## <a name="send-us-your-feedback"></a>피드백을 보내주세요.

이 가이드는 .NET에서 컨테이너화된 애플리케이션 및 마이크로 서비스의 아키텍처를 쉽게 이해할 수 있도록 작성되었습니다. 가이드 및 관련 참조 애플리케이션은 계속 발전할 예정이므로, 피드백이 있으시면 언제든지 보내주세요! 이 가이드를 개선할 수 있는 방법에 대한 의견이 있으시면 <https://aka.ms/ebookfeedback>에서 피드백을 제출해주세요.

## <a name="credits"></a>크레딧

만든 이:

> **Cesar de la Torre** , 선임 PM, .NET 제품 팀, Microsoft Corp.

위임 편집자:

> **Janine Patrick**

개발 편집자:

> **Bob Russell** , 솔루션 전문가, Microsoft
>
> [**Octal Publishing, Inc.**](http://www.octalpub.com/)

편집 프로덕션:

> [Dianne Russell](http://www.octalpub.com/)
>
> **Octal Publishing, Inc.**

교열 편집자:

> **Bob Russell** , 솔루션 전문가, Microsoft

참가자 및 검토자:

> **Nish Anil** , 선임 프로그램 관리자, .NET 팀, Microsoft
>
> **Miguel Veloso** , 소프트웨어 개발 엔지니어, Plain Concepts
>
> **Sumit Ghosh** , 주임 컨설턴트, Neudesic

## <a name="copyright"></a>Copyright

게시자:

Microsoft 개발자 사업부, .NET 및 Visual Studio 제품 팀

Microsoft Corporation의 사업부

One Microsoft Way

Redmond, Washington 98052-6399

Copyright &copy; 2020 by Microsoft Corporation

All rights reserved. 이 가이드의 내용 중 어떤 부분도 게시자의 서면 허가 없이는 어떠한 형식이나 방법으로도 복제하거나 전송할 수 없습니다.

이 가이드는 작성자의 견해와 의견을 "있는 그대로" 제공하고 전달합니다. URL 및 기타 인터넷 웹 사이트 참조를 비롯하여 이 가이드에 제공된 견해, 의견 및 정보는 예고 없이 변경될 수 있습니다.

여기에 설명된 일부 예제는 예시 용도로만 제공되며 실제 데이터가 아닙니다. 실제로 연관시키거나 관련시키려고 의도하거나 추론해서는 안 됩니다.

"상표" 웹 페이지의 <https://www.microsoft.com>에 나열된 Microsoft 및 상표는 Microsoft 그룹 계열사의 상표입니다.

Mac 및 macOS는 Apple Inc.의 상표입니다.

Docker 고래 로고는 Docker, Inc.의 등록 상표로, 허가하에 사용됩니다.

기타 모든 표시와 로고는 해당 소유자의 자산입니다.

>[!div class="step-by-step"]
>[다음](introduction-to-containers-and-docker.md)
