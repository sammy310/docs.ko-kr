---
title: 추가 마이그레이션 리소스
description: 팀에서 .NET Framework 앱을 .NET Core로 이식 하는 데 도움이 되는 리소스를 찾을 수 있는 곳은 어디 인가요?
author: ardalis
ms.date: 11/13/2020
ms.openlocfilehash: c6563f4791d133606cb1818a088bff17a315b1f6
ms.sourcegitcommit: bdbf6472de867a0a11aaa5b9384a2506c24f27d2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2021
ms.locfileid: "102401885"
---
# <a name="additional-migration-resources"></a>추가 마이그레이션 리소스

ASP.NET MVC 및/또는 Web API에서 ASP.NET Core로의 마이그레이션을 계획 하 고 실행 하는 경우이 책을 벗어나는 데 도움이 되는 많은 리소스가 있습니다. 이러한 정보를 적어 두고 마이그레이션 과정에서 발생 하는 장애물을 극복 하는 데 도움이 되는 경우 활용 하세요.

## <a name="official-documentation"></a>공식 설명서

공식 설명서 웹 사이트인 [docs.microsoft.com](https://docs.microsoft.com/)에는 버전, 프레임 워크, 주요 변경 내용 및 지원 옵션에 대 한 최신 정보가 포함 되어 있습니다. 이 책에서 docs 문서에 대 한 많은 링크를 찾을 수 있지만 직면 하는 모든 문제에 대해 최소한 문서를 빠르게 검색 하 여 문제를 포함 하 고 해결 방법을 제공 하는 정보가 이미 있는지 확인 하는 것이 좋습니다.

## <a name="github"></a>GitHub

.NET Core는 오픈 소스 프로젝트 이므로 GitHub에서 많은 문제가 검색, 보고, 설명 및 수정 됩니다. Microsoft에는 유용한 리포지토리를 찾을 수 있는 여러 GitHub 조직이 있습니다. 이러한 조직의 일부 목록과 해당 공용 리포지토리가 아래에 나열 되어 있습니다.

- [Microsoft](https://github.com/microsoft)
  - [ASP.NET API 버전 관리](https://github.com/microsoft/aspnet-api-versioning)
- [dotnet](https://github.com/dotnet)
  - [ASP.NET Core](https://github.com/dotnet/aspnetcore)
  - [.NET 런타임](https://github.com/dotnet/runtime)
  - [Entity Framework Core](https://github.com/dotnet/efcore)
  - [C # 언어](https://github.com/dotnet/csharplang)
  - [문서](https://github.com/dotnet/docs)
  - [Docs 샘플](https://github.com/dotnet/samples)
  - [변환 시도](https://github.com/dotnet/try-convert)
  - [.NET 업그레이드 도우미 도구](https://aka.ms/dotnet-upgrade-assistant)
- [.NET 아키텍처 참조 앱](https://github.com/dotnet-architecture)
  - [eShopModernizing](https://github.com/dotnet-architecture/eShopModernizing)
  - [eShopOnWeb](https://github.com/dotnet-architecture/eShopOnWeb)
  - [eShopOnContainers](https://github.com/dotnet-architecture/eShopOnContainers)

마이그레이션에 문제가 발생 하는 경우 이러한 GitHub 리포지토리를 보고 하는 것이 좋습니다. 제품 팀은 문제를 확인 하 고 일반적으로 버그 보고서에 신속 하 게 응답 합니다. ("방법" 질문은 보다 적절 하 게 Stack Overflow으로 전달 될 수 있습니다.)

## <a name="stack-overflow"></a>Stack Overflow

[Stack Overflow](https://stackoverflow.com/) 에는 제공 된 이전 질문 및 답변의 형태로 풍부한 정보가 포함 되어 있으며, 가장 유용한 답변을 먼저 나열 하 고 문제를 해결 한 경우 표시 합니다. 발생할 수 있는 문제에 대 한 기존 솔루션을 검색 하는 것 외에도 질문을 하 고 .NET 커뮤니티의 응답을 요청할 수 있습니다. 태그를 사용 하 여 검색 범위를 좁힐 수 있으며, 질문을 하는 데 필요한 경험을 최대한 활용할 수 있도록 질문을 할 때 적절 한 태그를 사용 해야 합니다.

## <a name="youtube-channels"></a>YouTube 채널

YouTube에는 많은 양의 .NET 및 .NET Core 비디오 콘텐츠가 있으며, 여기에는 발생할 수 있는 시나리오를 다루는 유용한 자습서 또는 연습이 포함 되어 있습니다. 온라인에서 도움을 얻을 수 있는 다른 노력이 있으면 별도로 검색 하는 것이 좋습니다. 다음은 시작 하는 데 도움이 되는 몇 가지 좋은 위치입니다.

- [dotnet](https://www.youtube.com/dotnet)
- [Visual Studio](https://www.youtube.com/visualstudio)

## <a name="twitter-gitter-slack-and-other-community-channels"></a>Twitter, Gitter, 여유 시간 및 기타 커뮤니티 채널

.Net [커뮤니티 페이지](https://dotnet.microsoft.com/platform/community)에서 .net 개발자와 연결 하는 다른 여러 가지 방법을 찾을 수 있습니다. [DotNetEvolution Discord 서버](https://aka.ms/dotnet-discord)에 가입할 수도 있습니다. 또한 대부분의 제품 팀 및 팀 구성원은 Twitter 뿐만 아니라 여러 다른 커뮤니티에도 있습니다. 또한 [Twitter에서이 설명서의 작성자](https://twitter.com/ardalis) 와 의견을 주고 받을 수 있습니다.

## <a name="references"></a>참조

- [.NET Framework에서 .NET Core로의 이식 개요](../../core/porting/index.md)
- [.NET 업그레이드 도우미 도구](https://aka.ms/dotnet-upgrade-assistant)
- [ASP.NET에서 ASP.NET Core로 마이그레이션](../../core/porting/index.md)
- [.NET 커뮤니티 리소스](https://dotnet.microsoft.com/platform/community)

>[!div class="step-by-step"]
>[이전](deployment-strategies.md)
>[다음](architectural-differences.md)
