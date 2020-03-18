---
title: WCF 개발자를 위한 ASP.NET Core gRPC - WCF 개발자를 위한 gRPC
description: ASP.NET Core 3.0에서 WCF 개발자를 위한 gRPC 서비스를 구축하는 방법 소개
ms.date: 09/02/2019
ms.openlocfilehash: 40307124c521659a00339884bacf48881fa3e048
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2020
ms.locfileid: "77543237"
---
# <a name="aspnet-core-grpc-for-wcf-developers"></a>WCF 개발자를 위한 ASP.NET Core gRPC

![표지 이미지](./media/cover.png)

게시자:

Microsoft 개발자 사업부, .NET 및 Visual Studio 제품 팀

Microsoft Corporation의 사업부

One Microsoft Way

Redmond, Washington 98052-6399

Copyright © 2019 by Microsoft Corporation

All rights reserved. 이 가이드의 내용 중 어떤 부분도 게시자의 서면 허가 없이는 어떠한 형식이나 방법으로도 복제하거나 전송할 수 없습니다.

이 가이드는 작성자의 견해와 의견을 “있는 그대로” 제공하고 전달합니다. URL 및 기타 인터넷 웹 사이트 참조를 비롯하여 이 가이드에 제공된 견해, 의견 및 정보는 예고 없이 변경될 수 있습니다.

여기에 설명된 일부 예제는 예시 용도로만 제공되며 실제 데이터가 아닙니다. 실제로 연관시키거나 관련시키려고 의도하거나 추론해서는 안 됩니다.

“상표” 웹 페이지의 https://www.microsoft.com 에 나열된 Microsoft 및 상표는 Microsoft 그룹 계열사의 상표입니다.

Docker 고래 로고는 Docker, Inc.의 등록 상표로, 허가하에 사용됩니다.

기타 모든 표시와 로고는 해당 소유자의 자산입니다.

작성자:

> **Mark Rendle** - 최고 기술 책임자 - [Visual Recode](https://visualrecode.com)
>
> **Miranda Steiner** - 기술 작성자

편집기:

> **Maira Wenzel** - 선임 콘텐츠 개발자 - Microsoft

## <a name="introduction"></a>소개

gRPC는 네트워크 서비스와 분산 애플리케이션을 빌드하기 위한 최신 프레임워크입니다. SOAP의 플랫폼 간 상호 운용성과 결합된 WCF(Windows Communication Foundation) NetTCP 바인딩의 성능을 상상해 보세요. gRPC는 HTTP/2 및 Protobuf 메시지 인코딩 프로토콜을 기반으로 하여 애플리케이션과 서비스 간에 뛰어난 성능의 저대역폭 통신을 제공합니다. .NET, Java, Python, Node.js, Go, C++ 등을 비롯한 가장 인기 있는 프로그래밍 언어 및 플랫폼에서 서버 및 클라이언트 코드 생성을 지원합니다. .NET 4.x용 기존 gRPC 도구 및 라이브러리와 함께 ASP.NET Core 3.0에서 gRPC에 대한 최고 수준의 지원을 제공하므로 조직에서 .NET Core를 도입하려는 개발 팀을 위한 WCF의 훌륭한 대안입니다.

## <a name="who-should-use-this-guide"></a>이 가이드의 대상 사용자

이 가이드는 이전에 WCF를 사용했으며 .NET Core 3.0 이상 버전용 최신 RPC 환경으로 애플리케이션을 마이그레이션하려는 .NET Framework 또는 .NET Core에서 작업하는 개발자를 위해 작성되었습니다. 더 일반적으로는 .NET Core 3.0로 업그레이드하거나 업그레이드를 고려 중이고 기본 제공 gRPC 도구를 사용하려는 경우에도 이 가이드가 유용합니다.

## <a name="how-you-can-use-this-guide"></a>이 가이드를 사용하는 방법

다음은 WCF에 대한 특정 참조를 유사한 플랫폼으로 사용하여 ASP.NET Core 3.0에서 gRPC 서비스를 빌드하는 방법을 간략히 소개합니다. 여기서는 각 개념을 WCF의 해당 기능과 연계하여 gRPC의 원칙을 설명하고 기존 WCF 애플리케이션을 gRPC로 마이그레이션하기 위한 지침을 제공합니다. 또한 WCF를 경험하고 새 서비스를 빌드하기 위해 gRPC를 알아보려는 개발자에게 유용합니다. 애플리케이션 예제를 사용자 프로젝트를 위한 템플릿 또는 참조로 사용하고, 가이드 또는 샘플에서 코드를 복사하여 재사용할 수 있습니다.

이 가이드를 팀에서 자유롭게 공유하고 이러한 여러가지 고려 사항과 기회에 대한 이해를 도모하세요. 모든 사람이 공통적인 용어와 기본 원칙으로 작업하도록 하면 아키텍처 패턴 및 사례를 일관성 있게 적용하는 데 도움이 됩니다.

## <a name="references"></a>참조 항목

- **gRPC 웹 사이트**
  <https://grpc.io>
- **서버 앱에 대해 .NET Core와 .NET Framework 중에 선택**
  <https://docs.microsoft.com/dotnet/standard/choosing-core-framework-server>

>[!div class="step-by-step"]
>[다음](introduction.md)
