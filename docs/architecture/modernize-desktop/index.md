---
title: .NET Core 3.1을 사용하여 Windows 10의 데스크톱 앱 현대화
description: .NET Core 3.1을 사용하여 기존 데스크톱 앱을 현대화하는 방법 알아보기
ms.date: 05/12/2020
ms.openlocfilehash: 5861f806a9158ef761c47bc23e51327d4e2d0480
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2020
ms.locfileid: "83422664"
---
# <a name="modernizing-desktop-apps-on-windows-10-with-net-core-31"></a>.NET Core 3.1을 사용하여 Windows 10의 데스크톱 앱 현대화

![데스크톱 앱 현대화 eBook 표지를 보여 주는 스크린샷.](./media/modernizing-existing-desktop-apps-ebook-cover.png)

게시자:

Microsoft 개발자 사업부, .NET 및 Visual Studio 제품 팀

Microsoft Corporation의 사업부

One Microsoft Way

Redmond, Washington 98052-6399

Copyright © 2020 by Microsoft Corporation

All rights reserved. 이 가이드의 내용 중 어떤 부분도 게시자의 서면 허가 없이는 어떠한 형식이나 방법으로도 복제하거나 전송할 수 없습니다.

이 가이드는 작성자의 견해와 의견을 "있는 그대로" 제공하고 전달합니다. URL 및 기타 인터넷 웹 사이트 참조를 비롯하여 이 가이드에 제공된 견해, 의견 및 정보는 예고 없이 변경될 수 있습니다.

여기에 설명된 일부 예제는 예시 용도로만 제공되며 실제 데이터가 아닙니다. 실제로 연관시키거나 관련시키려고 의도하거나 추론해서는 안 됩니다.

"상표" 웹 페이지의 <https://www.microsoft.com>에 나열된 Microsoft 및 상표는 Microsoft 그룹 계열사의 상표입니다.

Mac 및 macOS는 Apple Inc.의 상표입니다.

기타 모든 표시와 로고는 해당 소유자의 자산입니다.

공동 작성자:

> **Olia Gavrysh**, 프로그램 관리자, .NET 팀, Microsoft

> **Miguel Angel Castejón Dominguez**, 혁신 설계자, Kabel

참가자 및 검토자:

> **Maira Wenzel**, 선임 프로그램 관리자, .NET 팀, Microsoft

> **Andy De Gorge**, 선임 콘텐츠 개발자, .NET 문서 팀, Microsoft

> **Miguel Ramos**, 선임 프로그램 관리자, Windows 개발자 플랫폼 팀, Microsoft

> **Adam Braden**, 수석 프로그램 관리자, Windows 개발자 플랫폼 팀, Microsoft

> **Ricardo Minguez Pablos**, 선임 프로그램 관리자, Azure IoT 팀, Microsoft

> **Nish Anil**, 선임 프로그램 관리자, .NET 팀, Microsoft

> **Beth Massi**, 선임 제품 마케팅 관리자, Microsoft

> **Scott Hunter**, 파트너 프로그램 관리 책임자, .NET 팀, Microsoft

> **Marta Fuentes Lara**, Kabel

> **Raúl Fernández de Córdoba**, Kabel

> **Antonio Manuel Fernández Cantos**, Kabel

## <a name="introduction"></a>소개

현대화 과정을 통해 기존 데스크톱 애플리케이션을 이동하고 최신 런타임, 언어 및 플랫폼 기능을 통합하기 위해 채택할 수 있는 전략에 대한 책입니다. 애플리케이션이 서로 다르고 사용자의 요구 사항 및 기본 설정도 다르기 때문에 고유한 레시피는 없다는 것을 알 수 있을 것입니다. 좋은 소식은, 애플리케이션에 새로운 기능을 추가하기 위해 적용할 수 있는 일반적인 방법이 있다는 것입니다. 심지어 그중 일부는 코드를 크게 수정하지 않아도 됩니다. 이 책에서는 모든 해당 기능이 백그라운드에서 어떻게 작동하는지 보여 주고 해당 기능의 구현 메커니즘을 설명합니다. 또한 프로젝트 개발에 대한 영감을 얻을 수 있도록 기존 데스크톱 애플리케이션을 현대화하는 과정을 구체적으로 보여 주는 일반적인 시나리오를 몇 가지 제공합니다.

기존 애플리케이션을 현대화하는 Microsoft의 접근 방식은 사용자 지정 경로를 유연하게 만들 수 있도록 하는 것입니다. 이 책에서 설명하는 모든 현대화 전략은 대부분 독립적입니다. 애플리케이션과 관련된 항목을 선택하고 중요하지 않은 항목은 건너뛸 수 있습니다. 즉, 여러 전략을 혼합하여 애플리케이션 요구를 가장 적절히 충족할 수 있습니다.

## <a name="who-should-use-the-book"></a>이 책의 대상 사용자

이 책은 기존 Windows Forms 및 WPF 데스크톱 애플리케이션을 현대화하여 .NET Core 및 Windows 10의 이점을 활용하려는 개발자 및 솔루션 설계자를 위해 작성되었습니다.

또한 기존 데스크톱 애플리케이션 업데이트의 이점을 개괄적으로 알고자 하는 엔터프라이즈 설계자 또는 개발 리더나 디렉터와 같은 기술 의사 결정자인 경우 이 책을 유용하게 활용할 수 있습니다.

## <a name="how-to-use-the-book"></a>책 사용 방법

이 책에서는 기존 애플리케이션을 현대화하는 “이유”를 설명하고, .NET Core 3.1 및 MSIX를 사용하여 데스크톱 앱을 현대화하는 경우에 얻게 되는 구체적인 이점을 소개합니다. 이 책의 내용은 개요를 알고 싶지만 구현과 기술적인 단계별 세부 정보에 대해 중점을 둘 필요가 없는 설계자와 기술 의사 결정자를 위해 고안되었습니다.

애플리케이션 예제에 대한 완벽한 마이그레이션 프로세스를 소개하는 5장을 포함하여 챕터마다 샘플 구현 코드 조각과 스크린샷을 제공합니다.

## <a name="what-this-book-doesnt-cover"></a>이 책에서 다루지 않는 내용

이 책에서는 리프트 앤 시프트 시나리오에 중점을 둔 시나리오의 특정 하위 집합에 대해 설명하고, 코드를 다시 작성할 필요 없이 현대화의 이점을 얻는 방법을 간략하게 설명합니다.

이 책은 .NET Core를 사용하여 최신 애플리케이션을 처음부터 개발하는 방법 또는 Windows Forms 및 WPF를 시작하는 방법에 관한 것은 아닙니다. 이 책은 데스크톱 개발을 위해 최신 기술로 기존 데스크톱 애플리케이션을 업데이트하는 방법에 중점을 둡니다.

## <a name="samples-used-in-this-book"></a>이 책에서 사용하는 샘플

현대화를 수행하는 데 필요한 단계를 강조하기 위해 `eShopModernizing`이라는 애플리케이션 예제를 사용합니다. 이 애플리케이션에는 Windows Forms와 WPF가 포함되어 있으며, 이 두 가지 모두에서 .NET Core로의 현대화를 수행하는 방법에 대한 단계별 프로세스가 보여 줍니다.

또한 이 책의 GitHub 리포지토리에는 단계별 자습서를 수행하기로 결정한 경우에 참조할 수 있는 프로세스 결과가 있습니다.

## <a name="send-your-feedback"></a>피드백 보내기

이 책과 관련 샘플은 지속적으로 진화합니다. 여러분의 피드백을 기다리고 있습니다! 이 책을 향상시킬 수 있는 방법에 대한 의견이 있으면 [GitHub 문제](https://github.com/dotnet/docs/issues)에 빌드된 페이지의 맨 아래에서 피드백 섹션을 사용하세요.

>[!div class="step-by-step"]
>[다음](why-modern-applications.md)
