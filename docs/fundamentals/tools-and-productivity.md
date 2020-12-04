---
title: .NET의 도구 및 진단
author: IEvangelist
description: .NET 개발자가 사용할 수 있는 개발 및 진단 도구에 대해 알아봅니다.
ms.author: dapine
ms.date: 10/21/2020
ms.topic: overview
ms.openlocfilehash: 07c1a161a0bb429403db6852fe77749d83c19ec0
ms.sourcegitcommit: 98d20cb038669dca4a195eb39af37d22ea9d008e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2020
ms.locfileid: "96593835"
---
# <a name="tools-and-diagnostics-in-net"></a>.NET의 도구 및 진단

이 문서에서는 .NET 개발자가 사용할 수 있는 다양 한 도구에 대해 알아봅니다. .NET을 사용 하면 CLI (명령줄 인터페이스)를 포함 하는 강력한 SDK (소프트웨어 개발 키트)를 사용할 수 있습니다. .NET CLI는 전체에서 다양 한 기능을 사용할 수 있도록 합니다. NET ready Ide (통합 개발 환경)를 지원 합니다. 이 문서에서는 성능 문제를 진단 하기 위한 .NET CLI 도구, 메모리 누수, 높은 CPU, 교착 상태 및 코드 분석을 위한 도구 지원과 같은 생산성 기능에도 리소스를 제공 합니다.

## <a name="net-sdk"></a>.NET SDK

.Net SDK에는 .NET 런타임과 .NET CLI가 모두 포함 되어 있습니다. Windows, Linux, macOS 또는 Docker 용 [.NET SDK](https://dotnet.microsoft.com/download) 를 다운로드할 수 있습니다. 자세한 내용은 [.NET SDK 개요](../core/sdk.md)를 참조 하세요.

## <a name="net-cli"></a>.NET CLI

.NET CLI는 .NET 응용 프로그램을 개발, 빌드, 실행 및 게시 하기 위한 플랫폼 간 도구 체인. .NET CLI는 .NET SDK에 포함되어 있습니다. 자세한 내용은 [.NET CLI 개요](../core/tools/index.md)를 참조 하세요.

## <a name="ides"></a>IDE

[Visual Studio Code](https://code.visualstudio.com/docs), [Visual Studio](/visualstudio/windows)또는 [Mac용 Visual Studio](/visualstudio/mac)에서 .net 응용 프로그램을 작성할 수 있습니다. 클라우드 기반 개발 환경에 대 한 자세한 내용은 [Visual Studio Codespaces](/visualstudio/codespaces/overview/what-is-vsonline)를 참조 하세요.

## <a name="additional-tools"></a>추가 도구

.NET은 보다 일반적인 도구 외에도 특정 시나리오에 대 한 도구를 제공 합니다. 일부 사용 사례에는 .NET SDK 또는 .NET 런타임을 제거 하 고, WCF (Windows Communication Foundation) 메타 데이터를 검색 하 고, 프록시 소스 코드를 생성 하 고, XML을 serialize 하는 작업이 포함 됩니다. 자세한 내용은 [.net 추가 도구 개요](../core/additional-tools/index.md)를 참조 하세요.

## <a name="diagnostics-and-instrumentation"></a>진단 및 계측

.NET 개발자는 일반적인 성능 진단 도구를 사용 하 여 응용 프로그램 성능을 모니터링 하 고, 추적을 사용 하 여 앱을 프로 파일링 하 고, 성능 메트릭을 수집 하 고, 덤프 파일을 분석할 수 있습니다. 이벤트 카운터를 사용 하 여 성능 메트릭을 수집 하 고 프로 파일링 도구를 사용 하 여 앱의 작동 방식에 대 한 정보를 얻습니다. 자세한 내용은 [.net 진단 도구](../core/diagnostics/index.md)를 참조 하세요.

## <a name="code-analysis"></a>코드 분석

Roslyn (.NET 컴파일러 플랫폼) 분석기는 c # 또는 Visual Basic 코드에서 코드 품질 및 코드 스타일 문제를 검사 합니다. 자세한 내용은 [.net 소스 코드 분석 개요](code-analysis/overview.md)를 참조 하세요.
