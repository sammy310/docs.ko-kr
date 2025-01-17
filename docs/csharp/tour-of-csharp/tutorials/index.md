---
title: C# 소개 - 대화형 자습서
description: 브라우저에서 C#에 대해 알아보고 사용자만의 개발 환경을 시작합니다.
ms.date: 02/02/2021
ms.custom: mvc
ms.openlocfilehash: ed869271cd6f4ec13f769f46d41aefae9e1dad8d
ms.sourcegitcommit: c7f0beaa2bd66ebca86362ca17d673f7e8256ca6
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "104872420"
---
# <a name="introduction-to-c"></a>C\# 소개

C# 소개 자습서를 시작합니다. 이 단원은 브라우저에서 실행할 수 있는 대화형 코드로 시작됩니다. 해당 대화형 단원을 시작하기 전에 [C# 101 동영상 시리즈](https://aka.ms/dotnet3-csharp)에서 C#의 기본 사항을 학습할 수 있습니다.

<!--markdownlint-disable MD034 -->
> [!VIDEO https://channel9.msdn.com/Series/CSharp-101/What-is-C/player]

첫 번째 단원에서는 작은 코드 조각을 사용하여 C# 개념을 설명합니다. C# 구문의 기본 사항과 문자열, 숫자 및 부울과 같은 데이터 형식을 사용하는 방법에 대해 학습합니다. 모두 대화형이며, 몇 분 내에 코드를 작성하여 실행할 수 있습니다. 이 첫 번째 단원에서는 프로그래밍이나 C# 언어에 대한 사전 지식이 없다고 가정합니다.

다양한 환경에서 이 자습서를 사용해 볼 수 있습니다. 학습할 개념은 같습니다. 차이점은 선호하는 환경입니다.

- [브라우저의 docs 플랫폼](hello-world.yml). 이 환경에는 실행 가능한 C# 코드 창이 docs 페이지에 포함되어 있습니다. 브라우저에서 C# 코드를 작성하고 실행합니다.
- [Microsoft Learn 환경](/learn/paths/csharp-first-steps/). 이 학습 경로에는 C#의 기본 사항을 설명하는 여러 모듈이 포함되어 있습니다.
- [Binder의 Jupyter](https://mybinder.org/v2/gh/dotnet/try-samples/master?filepath=hello-csharp%2Fhello-world.ipynb). Binder의 Jupyter Notebook에서 C# 코드를 시험해 볼 수 있습니다.
- [로컬 머신](numbers-in-csharp-local.md). 온라인에서 살펴본 후 머신에 .NET Core SDK를 [다운로드](https://dotnet.microsoft.com/download)하고 프로그램을 빌드할 수 있습니다.

Hello World 단원 다음에 나오는 모든 소개 자습서는 온라인 브라우저 환경이나 [자체 로컬 개발 환경](local-environment.md)을 사용하여 볼 수 있습니다. 각 자습서가 끝날 때 다음 단원을 온라인으로 진행할지, 사용자 머신에서 진행할지 결정합니다. 환경을 설정하고 사용자 머신에서 다음 자습서를 진행하는 데 유용한 링크가 있습니다.

## <a name="hello-world"></a>[Hello World](hello-world.yml)

[Hello World](hello-world.yml) 자습서에서는 가장 기본적인 C# 프로그램을 만듭니다. `string` 형식을 살펴보고 텍스트를 사용하는 방법을 살펴봅니다. 또한 [Microsoft Learn](/learn/paths/csharp-first-steps/) 또는 [Binder의 Jupyter](https://mybinder.org/v2/gh/dotnet/try-samples/master?filepath=hello-csharp%2Fhello-world.ipynb) 경로를 사용할 수 있습니다.

## <a name="numbers-in-c"></a>[C#의 숫자](numbers-in-csharp.yml)

[C#의 숫자](numbers-in-csharp.yml) 자습서에서는 컴퓨터가 숫자를 저장하는 방법과 여러 숫자 형식으로 계산을 수행하는 방법을 알아봅니다. 반올림의 기본 사항과 C#을 사용하여 수학 계산을 수행하는 방법에 대해 학습합니다. 이 자습서는 [머신에서 로컬로 실행](numbers-in-csharp-local.md)할 수도 있습니다.

이 자습서에서는 [Hello World](hello-world.yml) 단원을 완료했다고 가정합니다.

## <a name="branches-and-loops"></a>[분기 및 루프](branches-and-loops.yml)

[분기 및 루프](branches-and-loops.yml) 자습서에서는 변수에 저장된 값에 따라 코드 실행의 여러 경로를 선택하는 기본 사항을 설명합니다. 프로그램에서 결정하고 여러 작업을 선택하는 방법에 대한 기본 사항인 제어 흐름의 기본 사항에 대해 알아봅니다. 이 자습서는 [머신에서 로컬로 실행](branches-and-loops-local.md)할 수도 있습니다.

이 자습서에서는 [Hello World](hello-world.yml) 및 [C#의 숫자](numbers-in-csharp.yml) 단원을 완료했다고 가정합니다.

## <a name="list-collection"></a>[목록 컬렉션](list-collection.yml)

[목록 컬렉션](list-collection.yml) 단원에서는 데이터 시퀀스를 저장하는 목록 컬렉션 형식을 살펴봅니다. 항목을 추가 및 제거하고, 항목을 검색하고, 목록을 정렬하는 방법을 배웁니다. 여러 종류의 목록을 살펴봅니다. 이 자습서는 [머신에서 로컬로 실행](arrays-and-collections.md)할 수도 있습니다.

이 자습서에서는 위에 나열된 단원을 완료했다고 가정합니다.

## <a name="101-linq-samples"></a>[101 LINQ 샘플](https://github.com/dotnet/try-samples/tree/main/101-linq-samples)

이 샘플을 사용하려면 [dotnet-try](https://github.com/dotnet/try/blob/main/README.md#setup) 전역 도구가 필요합니다. 도구를 설치하고 [try-samples](https://github.com/dotnet/try-samples) 리포지토리를 복제한 후에는 대화형으로 실행할 수 있는 101개 샘플의 세트를 통해 LINQ(Language Integrated Query)를 배울 수 있습니다. 데이터 시퀀스를 쿼리, 탐색 및 변환하는 다양한 방법을 탐색할 수 있습니다.
