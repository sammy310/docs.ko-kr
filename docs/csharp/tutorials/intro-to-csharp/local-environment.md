---
title: C# 소개 - 개발 도구 익히기
description: 이 문서에서는 머신에서 C# 및 .NET 애플리케이션을 개발하는 데 사용할 도구의 기본 사항을 소개합니다.
ms.date: 02/02/2021
ms.openlocfilehash: d5fbd23679fc11f4e4c207c59858a71ab753c038
ms.sourcegitcommit: 65af0f0ad316858882845391d60ef7e303b756e8
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/05/2021
ms.locfileid: "99585327"
---
# <a name="set-up-your-local-environment"></a>로컬 환경 설정

머신에서 자습서를 실행하는 첫 번째 단계는 개발 환경을 설정하는 것입니다. 다음 대체 방법 중 하나를 선택합니다.

* .NET CLI와 원하는 텍스트 또는 코드 편집기를 사용하려면 .NET 자습서 [Hello World 10분 완성](https://dotnet.microsoft.com/learn/dotnet/hello-world-tutorial/intro)을 참조하세요. 이 자습서에는 Windows, Linux 또는 macOS에서 개발 환경을 설정하기 위한 지침이 포함되어 있습니다.
* .NET CLI와 Visual Studio Code를 사용하려면 [.NET SDK](https://dotnet.microsoft.com/download)와 [Visual Studio Code](https://code.visualstudio.com/)를 설치합니다.
* Windows에서 Visual Studio 2019를 사용하려면 [자습서: Visual Studio에서 간단한 C# 콘솔 앱 만들기](/visualstudio/get-started/csharp/tutorial-console)를 참조하세요.

## <a name="basic-application-development-flow"></a>기본 애플리케이션 개발 흐름

이러한 자습서의 지침에서는 .NET CLI를 사용하여 애플리케이션을 만들고, 빌드하고, 실행한다고 가정합니다. 다음 명령을 사용합니다.

* [`dotnet new`](../../../core/tools/dotnet-new.md)는 애플리케이션 로더를 만듭니다. 이 명령은 애플리케이션에 필요한 파일과 자산을 생성합니다. C# 소개 자습서에서는 모두 `console` 애플리케이션 유형을 모두 사용합니다. 기본 사항을 알고 나면 다른 애플리케이션 유형으로 확장할 수 있습니다.
* [`dotnet build`](../../../core/tools/dotnet-build.md)는 실행 파일을 빌드합니다.
* [`dotnet run`](../../../core/tools/dotnet-run.md)은 실행 파일을 실행합니다.

이러한 자습서를 위해 Visual Studio 2019을 사용하는 경우 자습서에서 다음 CLI 명령 중 하나를 실행하도록 지시하는 경우 Visual Studio 메뉴 선택을 선택합니다.

* **파일** > **새로 만들기** > **프로젝트** 는 애플리케이션을 만듭니다.
* **빌드** >  **솔루션 빌드** 는 실행 파일을 빌드합니다.
* **디버그** > **디버깅하지 않고 시작** 은 실행 파일을 실행합니다.

## <a name="pick-your-tutorial"></a>자습서 선택

다음과 같은 자습서 중 하나를 시작할 수 있습니다.

## <a name="numbers-in-c"></a>C\#의 숫자

[C#의 숫자](numbers-in-csharp-local.md) 자습서에서는 컴퓨터가 숫자를 저장하는 방법과 여러 숫자 형식으로 계산을 수행하는 방법을 알아봅니다. 반올림의 기본 사항과 C#을 사용하여 수학 계산을 수행하는 방법을 알아봅니다.

이 자습서에서는 [Hello World](hello-world.yml) 단원을 완료했다고 가정합니다.

## <a name="branches-and-loops"></a>분기 및 루프

[분기 및 루프](branches-and-loops-local.md) 자습서에서는 변수에 저장된 값에 따라 코드 실행의 여러 경로를 선택하는 기본 사항을 설명합니다. 프로그램에서 결정하고 여러 작업을 선택하는 방법에 대한 기본 사항인 제어 흐름의 기본 사항에 대해 알아봅니다.

이 자습서에서는 [Hello World](hello-world.yml) 및 [C#의 숫자](numbers-in-csharp-local.md) 단원을 완료했다고 가정합니다.

## <a name="list-collection"></a>목록 컬렉션

[목록 컬렉션](arrays-and-collections.md) 단원에서는 데이터 시퀀스를 저장하는 목록 컬렉션 형식을 살펴봅니다. 항목을 추가 및 제거하고, 항목을 검색하고, 목록을 정렬하는 방법을 배웁니다. 여러 종류의 목록을 살펴봅니다.

이 자습서에서는 위에 나열된 단원을 완료했다고 가정합니다.

## <a name="introduction-to-classes"></a>클래스 소개

[클래스 소개](introduction-to-classes.md)에서는 콘솔 애플리케이션을 빌드하고 C# 언어의 일부인 기본 개체 지향 기능을 확인합니다. C# 자습서에 대한 마지막 소개입니다. 이 자습서는 자체 로컬 개발 환경 및 .NET을 사용하여 컴퓨터에서만 실행할 수 있습니다.
