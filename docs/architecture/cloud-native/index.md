---
title: Azure용 클라우드 네이티브 .NET 애플리케이션 설계
description: Azure의 컨테이너, 마이크로 서비스 및 서버리스 기능을 활용하여 클라우드 네이티브 애플리케이션을 빌드하는 방법을 보여 주는 가이드입니다.
author: ardalis
ms.date: 11/10/2020
ms.openlocfilehash: 673bfef27c3767f68b1c30d4383cee010ba377f0
ms.sourcegitcommit: bc9c63541c3dc756d48a7ce9d22b5583a18cf7fd
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/11/2020
ms.locfileid: "94506651"
---
# <a name="architecting-cloud-native-net-applications-for-azure"></a>Azure용 클라우드 네이티브 .NET 애플리케이션 설계

![표지 이미지](./media/cover.png)

**버전 v1.0**

책 업데이트 및 커뮤니티 기여에 대한 자세한 내용은 [changelog](https://aka.ms/cn-ebook-changelog)를 참조하세요.

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

작성자:

> **Rob Vettor** , 수석 클라우드 시스템 설계자/IP 설계자 - [thinkingincloudnative.com](https://thinkingincloudnative.com/about/), Microsoft
>
> **Steve "ardalis" Smith** , 소프트웨어 설계자이자 강사 - [Ardalis.com](https://ardalis.com)

참가자 및 검토자:

> **Cesar De la torre** , 수석 프로그램 관리자, .NET 팀, Microsoft
>
> **Nish Anil** , 선임 프로그램 관리자, .NET 팀, Microsoft
>
> **Jeremy Likness** , 선임 프로그램 관리자, .NET 팀, Microsoft
>
> **Cecil Phillip** , 선임 Cloud Advocate, Microsoft

편집자:

> **Maira Wenzel** , 프로그램 관리자, .NET 팀, Microsoft

## <a name="version"></a>버전

이 가이드는 .NET Core 3.1 릴리스와 동시에 **.NET Core 3.1** 버전을 다루도록 작성되었으며, 동일한 기술 “웨이브”(즉 Azure 및 추가 타사 기술)와 관련된 여러 추가 업데이트를 포함합니다.

## <a name="who-should-use-this-guide"></a>이 가이드의 대상 사용자

이 가이드의 주요 대상 사용자는 클라우드용으로 설계된 애플리케이션을 구축하는 방법을 알아보려는 개발자, 개발 책임자 및 설계자입니다.

보조 대상은 클라우드 네이티브 접근 방법을 사용하여 애플리케이션을 빌드할지 여부를 선택하는 기술 의사 결정자입니다.

## <a name="how-you-can-use-this-guide"></a>이 가이드를 사용하는 방법

이 가이드에서는 클라우드 네이티브를 정의하고 클라우드 네이티브 원칙 및 기술을 사용하여 빌드된 참조 애플리케이션을 소개합니다. 처음 두 장을 제외한 나머지 부분은 대부분의 클라우드 네이티브 애플리케이션에 공통된 항목을 중심으로 세부 장들로 분류되어 있습니다. 해당 장으로 바로 이동하여 클라우드 네이티브 접근 방식에 대해 알아볼 수 있습니다.

- 데이터 및 데이터 액세스
- 통신 패턴
- 크기 조정 및 확장성
- 애플리케이션 복원력
- 모니터링 및 상태
- ID 및 보안
- DevOps

이 가이드는 [PDF](https://dotnet.microsoft.com/download/e-book/cloud-native-azure/pdf) 양식과 온라인에서 모두 사용할 수 있습니다. 이러한 항목에 관한 일반적인 이해를 돕기 위해 이 문서 또는 온라인 버전 링크를 팀에 전달하세요. 이러한 항목은 대부분은 기본 원칙 및 패턴에 대한 일관된 이해를 도와주고 항목 관련 결정에 포함되는 장단점을 설명합니다. 이 문서의 목표는 팀 및 리더에게 애플리케이션의 아키텍처, 개발 및 호스팅과 관련하여 올바른 결정을 내리는 데 필요한 정보를 제공하는 것입니다.

## <a name="send-your-feedback"></a>피드백 보내기

이 책과 관련 샘플은 지속적으로 진화합니다. 여러분의 피드백을 기다리고 있습니다! 이 책을 향상시킬 수 있는 방법에 대한 의견이 있으면 [GitHub 문제](https://github.com/dotnet/docs/issues)에 빌드된 페이지의 맨 아래에서 피드백 섹션을 사용하세요.

>[!div class="step-by-step"]
>[다음](introduction.md)
