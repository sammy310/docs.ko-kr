---
title: .NET에서 테스트
description: 이 문서에서는 .NET에서 테스트하기 위한 테스트 개념, 용어 및 도구에 대한 간략한 개요를 제공합니다.
author: IEvangelist
ms.author: dapine
ms.date: 10/19/2020
ms.openlocfilehash: 36e88cc059447a98931593e0535c70cbc92a2cf4
ms.sourcegitcommit: 67ebdb695fd017d79d9f1f7f35d145042d5a37f7
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/20/2020
ms.locfileid: "92223470"
---
# <a name="testing-in-net"></a>.NET에서 테스트

이 문서에서는 테스트 개념을 소개하고 다양한 종류의 테스트를 사용하여 코드의 유효성을 검사하는 방법을 보여줍니다. [.NET CLI](#net-cli) 또는 [IDE(통합 개발 환경)](#ide)와 같이 .NET 애플리케이션을 테스트하는 데 사용할 수 있는 다양한 도구가 있습니다.

## <a name="test-types"></a>테스트 형식

자동화된 테스트를 사용하는 것이 애플리케이션 코드가 작성자가 의도한 대로 수행되는지 확인하는 좋은 방법입니다. 이 문서에서는 단위 테스트, 통합 테스트 및 부하 테스트에 대해 설명합니다.

### <a name="unit-tests"></a>단위 테스트

*단위 테스트*는 "작업 단위"라고도 하는 개별 소프트웨어 구성 요소 또는 메서드를 실행하는 테스트입니다. 단위 테스트는 개발자의 제어 내에서만 코드를 테스트해야 합니다. 인프라 문제를 테스트하지 않습니다. 인프라 문제에는 데이터베이스, 파일 시스템 및 네트워크 리소스와의 상호 작용이 포함됩니다.

단위 테스트를 만드는 방법에 대한 자세한 내용은 [테스트 도구](#testing-tools)를 참조하세요.

### <a name="integration-tests"></a>통합 테스트

*통합 테스트*는 "통합"이라고도 하는 둘 이상의 소프트웨어 구성 요소가 함께 작동하는 기능을 실행한다는 점에서 단위 테스트와 다릅니다. 이러한 테스트는 테스트 중인 시스템의 광범위한 스펙트럼에서 작동하는 반면 단위 테스트는 개별 구성 요소에 중점을 둡니다. 종종 통합 테스트에는 인프라 문제가 포함됩니다.

### <a name="load-tests"></a>부하 테스트

*부하 테스트*는 시스템에서 지정된 부하를 처리할 수 있는지 여부(예: 애플리케이션을 사용하는 동시 사용자 수와 상호 작용 반응을 처리하는 앱의 기능)를 결정하는 것을 목표로 합니다. 웹 애플리케이션의 부하 테스트에 대한 자세한 내용은 [ASP.NET Core 부하/스트레스 테스트](/aspnet/core/test/load-tests)를 참조하세요.

## <a name="test-considerations"></a>테스트 고려 사항

테스트를 작성하는 [모범 사례](unit-testing-best-practices.md)가 있습니다. 예를 들어 [TDD(테스트 기반 개발)](https://deviq.com/test-driven-development)는 확인하려는 코드보다 단위 테스트를 먼저 작성한 경우입니다. TDD는 책을 작성하기 전에 책에 대한 개요를 만드는 것과 같습니다. 이 기능을 통해 개발자가 간단하고 읽을 수 있고 효율적인 코드를 작성할 수 있습니다.

## <a name="testing-tools"></a>테스트 도구

.NET은 다중 언어 개발 플랫폼이며, [C#](../../csharp/index.yml), [F#](../../fsharp/index.yml) 및 [Visual Basic](../../visual-basic/index.yml)에 대한 다양한 테스트 형식을 작성할 수 있습니다. 이러한 각 언어에 대해 여러 테스트 프레임워크 중에서 선택할 수 있습니다.

### <a name="xunit"></a>xUnit

[xUnit](https://xunit.net)은 무료로 제공되는 .NET용 오픈 소스 커뮤니티 중심 유닛 테스트 도구입니다. NUnit v2의 원본 발명가가 작성한 xUnit.net은 .NET 앱을 단위 테스트하기 위한 최신 기술입니다. xUnit.net은 ReSharper, CodeRush, TestDriven.NET 및 [Xamarin](/apps/xamarin)에서 작동합니다. [.NET Foundation](https://dotnetfoundation.org)의 프로젝트이며, 해당 사용 규정에 따라 작동합니다.

자세한 내용은 다음 자료를 참조하세요.

- [C#을 사용한 단위 테스트](unit-testing-with-dotnet-test.md)
- [F#을 사용한 단위 테스트](unit-testing-fsharp-with-dotnet-test.md)
- [Visual Basic을 사용한 단위 테스트](unit-testing-visual-basic-with-dotnet-test.md)

### <a name="nunit"></a>NUnit

[NUnit](https://nunit.org)은 모든 .NET 언어에 대한 단위 테스트 프레임워크입니다. 처음에 JUnit에서 이식된 현재 프로덕션 릴리스는 다양한 .NET 플랫폼에 대한 많은 새로운 기능과 지원으로 다시 작성되었습니다. [.NET Foundation](https://dotnetfoundation.org)의 프로젝트입니다.

자세한 내용은 다음 자료를 참조하세요.

- [C#을 사용한 단위 테스트](unit-testing-with-nunit.md)
- [F#을 사용한 단위 테스트](unit-testing-fsharp-with-nunit.md)
- [Visual Basic을 사용한 단위 테스트](unit-testing-visual-basic-with-nunit.md)

### <a name="mstest"></a>MSTest

[MSTest](https://github.com/Microsoft/testfx-docs)는 모든 .NET 언어에 대한 Microsoft 테스트 프레임워크입니다. 확장 가능하며 .NET CLI와 Visual Studio 모두에서 작동합니다. 자세한 내용은 다음 자료를 참조하세요.

- [C#을 사용한 단위 테스트](unit-testing-with-mstest.md)
- [F#을 사용한 단위 테스트](unit-testing-fsharp-with-mstest.md)
- [Visual Basic을 사용한 단위 테스트](unit-testing-visual-basic-with-mstest.md)

### <a name="net-cli"></a>.NET CLI

[dotnet test](../tools/dotnet-test.md) 명령을 사용하여 [.NET CLI](../tools/index.md)에서 솔루션 단위 테스트를 실행할 수 있습니다. .NET CLI는 [IDE(통합 개발 환경)](#ide)에서 사용자 인터페이스를 통해 사용할 수 있는 대부분의 기능을 제공합니다. .NET CLI는 교차 플랫폼이며 연속 통합 및 지속적인 전달 파이프라인의 일부로 사용할 수 있습니다. .NET CLI는 일반적인 작업을 자동화하기 위해 스크립팅된 프로세스와 함께 사용됩니다.

### <a name="ide"></a>IDE

Visual Studio, Mac용 Visual Studio 또는 Visual Studio Code 사용 여부와 상관없이 기능 테스트를 위한 그래픽 사용자 인터페이스가 있습니다. CLI보다 IDE에서 더 많은 기능을 사용할 수 있습니다(예: [Live Unit Testing](/visualstudio/test/live-unit-testing)). 자세한 내용은 [Visual Studio를 사용하는 테스트 포함 및 제외](/visualstudio/test/live-unit-testing#include-and-exclude-test-projects-and-test-methods)를 참조하세요.

## <a name="see-also"></a>참고 항목

자세한 내용은 다음 아티클을 참조하세요.

- [.NET을 사용한 단위 테스트 모범 사례](unit-testing-best-practices.md)
- [ASP.NET Core의 통합 테스트](/aspnet/core/test/integration-tests#test-app-prerequisites)
- [선택적 단위 테스트 실행](selective-unit-tests.md)
- [유닛 테스트에 코드 검사 사용](unit-testing-code-coverage.md)
