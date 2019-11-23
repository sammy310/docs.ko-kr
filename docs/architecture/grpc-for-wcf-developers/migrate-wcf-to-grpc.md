---
title: Wcf 개발자를 위한 gRPC gRPC로 WCF 솔루션 마이그레이션
description: 다양 한 형식의 WCF 서비스를 gRPC의 해당 항목으로 마이그레이션하는 방법입니다.
ms.date: 09/02/2019
ms.openlocfilehash: 33823d20e1593323a03da12981c5a4534c4d491a
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/12/2019
ms.locfileid: "73971765"
---
# <a name="migrate-a-wcf-solution-to-grpc"></a>GRPC로 WCF 솔루션 마이그레이션

이 장에서는 ASP.NET Core 3.0 gRPC 프로젝트를 사용 하는 방법을 살펴보고 다양 한 유형의 WCF 서비스를 gRPC로 마이그레이션하는 방법을 보여 줍니다.

- ASP.NET Core 3.0 gRPC 프로젝트를 만듭니다.
- 단순 요청-gRPC 단항 RPC에 대 한 응답 작업입니다.
- 단일 방식으로 Pc 클라이언트 스트리밍 RPC를 수행 합니다.
- 전체 이중 서비스와 gRPC 양방향 스트리밍 RPC.

스트리밍 서비스와 데이터 집합을 반환 하는 데 반복 되는 필드를 사용 하는 것과 챕터의 끝에 클라이언트 라이브러리를 사용 하는 것도 비교 합니다.

샘플 WCF 응용 프로그램은 종속성 주입을 위해 *Autofac* 라는 오픈 소스 IoC (제어의 반전) 컨테이너 라이브러리를 사용 하 여 주식 거래 서비스 집합의 최소 스텁입니다. 각 WCF 서비스 유형에 대해 하나씩 세 개의 서비스를 포함 합니다. 이 서비스는 다음 섹션에서 자세히 설명 합니다. 솔루션은 GitHub의 [dotnet-architecture/grpc-wcf 개발자](https://github.com/dotnet-architecture/grpc-for-wcf-developers) 에서 다운로드할 수 있습니다. 서비스는 가짜 데이터를 사용 하 여 외부 종속성을 최소화 합니다.

샘플에는 각 서비스의 WCF 및 gRPC 구현이 포함 되어 있습니다.

>[!div class="step-by-step"]
>[이전](ws-protocols.md)
>[다음](create-project.md)
