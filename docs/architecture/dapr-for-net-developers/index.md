---
title: .NET 개발자용 Dapr
description: Microsoft의 오픈 소스 Distributed Application Runtime의 전체 기능을 이해하고 활용하기 위한 .NET 개발자용 안내서입니다.
author: robvet
ms.date: 02/17/2021
ms.openlocfilehash: 2ab66257cca6f99074e2aa45a24869012b4976fe
ms.sourcegitcommit: d623f686701b94bef905ec5e93d8b55d031c5d6f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/17/2021
ms.locfileid: "103623722"
---
# <a name="dapr-for-net-developers"></a>.NET 개발자용 Dapr

![표지 이미지](./media/cover.png)

**미리 보기 버전**

게시자:

Microsoft 개발자 부서, .NET 및 Azure Incubations 팀

Microsoft Corporation의 사업부

One Microsoft Way

Redmond, Washington 98052-6399

Copyright &copy; 2021 by Microsoft Corporation

All rights reserved. 이 가이드의 내용 중 어떤 부분도 게시자의 서면 허가 없이는 어떠한 형식이나 방법으로도 복제하거나 전송할 수 없습니다.

이 가이드는 작성자의 견해와 의견을 "있는 그대로" 제공하고 전달합니다. URL 및 기타 인터넷 웹 사이트 참조를 비롯하여 이 가이드에 제공된 견해, 의견 및 정보는 예고 없이 변경될 수 있습니다.

여기에 설명된 일부 예제는 예시 용도로만 제공되며 실제 데이터가 아닙니다. 실제로 연관시키거나 관련시키려고 의도하거나 추론해서는 안 됩니다.

"상표" 웹 페이지의 <https://www.microsoft.com>에 나열된 Microsoft 및 상표는 Microsoft 그룹 계열사의 상표입니다.

Mac 및 macOS는 Apple Inc.의 상표입니다.

Docker 고래 로고는 Docker, Inc.의 등록 상표로, 허가하에 사용됩니다.

기타 모든 표시와 로고는 해당 소유자의 자산입니다.

작성자:

> **Rob Vettor**, 수석 클라우드 솔루션 설계자 - [thinkingincloudnative.com](https://thinkingincloudnative.com/about/), Microsoft
>
> **Sander Molenkamp**, 수석 클라우드 설계자/Microsoft MVP - [sandermolenkamp.com](https://www.sandermolenkamp.com), [정보 지원](https://www.infosupport.com/en/)
>
> **Edwin van Wijk**, 수속 솔루션 설계자/Microsoft MVP - [defaultconstructor.com](https://defaultconstructor.com), [정보 지원](https://www.infosupport.com/en/)

참가자 및 검토자:

> **Mark Russinovich**, Azure CTO 및 기술자, Azure Office of CTO, Microsoft
>
> **Nish Anil**, 선임 프로그램 관리자, .NET 팀, Microsoft
>
> **Mark Fussell**, 수석 프로그램 관리자, Azure Incubations, Microsoft
>
> **Yaron Schneider**, 수석 소프트웨어 엔지니어, Azure Incubations, Microsoft
>
> **Ori Zohar**, 선임 프로그램 관리자, Azure Incubations, Microsoft

편집자:

> **David Pine**, 선임 콘텐츠 개발자, Microsoft .NET 팀
>
> **Maira Wenzel**, 선임 프로그램 관리자, .NET 팀, Microsoft

## <a name="version"></a>버전

이 안내서는 **Dapr 1.0** 버전의 내용을 다룹니다. .NET Core 샘플은 **.NET Core 3.1** 을 바탕으로 합니다.

## <a name="who-should-use-this-guide"></a>이 가이드의 대상 사용자

이 가이드의 주요 대상 사용자는 클라우드용으로 설계된 애플리케이션을 구축하는 방법을 알아보려는 개발자, 개발 책임자 및 설계자입니다.

보조 대상은 클라우드 네이티브 접근 방법을 사용하여 애플리케이션을 빌드할지 여부를 선택하는 기술 의사 결정자입니다.

## <a name="how-you-can-use-this-guide"></a>이 가이드를 사용하는 방법

이 가이드는 [PDF](https://aka.ms/dapr-ebook) 양식과 온라인에서 모두 사용할 수 있습니다. 이러한 항목에 관한 일반적인 이해를 돕기 위해 이 문서 또는 온라인 버전 링크를 팀에 전달하세요. 이러한 항목은 대부분은 기본 원칙 및 패턴에 대한 일관된 이해를 도와주고 항목 관련 결정에 포함되는 장단점을 설명합니다. 이 문서의 목표는 팀 및 리더에게 애플리케이션의 아키텍처, 개발 및 호스팅과 관련하여 올바른 결정을 내리는 데 필요한 정보를 제공하는 것입니다.

## <a name="send-your-feedback"></a>피드백 보내기

이 책과 관련 샘플은 지속적으로 진화합니다. 여러분의 피드백을 기다리고 있습니다! 이 책을 향상시킬 수 있는 방법에 대한 의견이 있으면 [GitHub 문제](https://github.com/dotnet/docs/issues)에 빌드된 페이지의 맨 아래에서 피드백 섹션을 사용하세요.

>[!div class="step-by-step"]
>[다음](foreword.md)
