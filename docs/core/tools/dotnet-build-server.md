---
title: dotnet build-server 명령
description: dotnet build-server 명령은 빌드에서 시작된 서버와 상호 작용합니다.
ms.date: 04/24/2019
ms.openlocfilehash: b2dfd5f317466f18d9246bd1fb281a92c42f6d9d
ms.sourcegitcommit: 1b020356e421a9314dd525539da12463d980ce7a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/30/2019
ms.locfileid: "70168104"
---
# <a name="dotnet-build-server"></a>dotnet build-server

**이 문서 적용 대상: ✓** .NET Core 2.1 SDK 이상 버전

<!-- todo: uncomment when all CLI commands are reviewed
[!INCLUDE [topic-appliesto-net-core-21plus](../../../includes/topic-appliesto-net-core-21plus.md)]
-->

## <a name="name"></a>name

`dotnet build-server` - 빌드에서 시작된 서버와 상호 작용합니다.

## <a name="synopsis"></a>개요

```console
dotnet build-server shutdown [--msbuild] [--razor] [--vbcscompiler]
dotnet build-server shutdown [-h|--help]
dotnet build-server [-h|--help]
```

## <a name="commands"></a>명령

* **`shutdown`**

  Dotnet에서 시작된 빌드 서버를 종료합니다. 기본적으로 모든 서버가 종료됩니다.

## <a name="options"></a>옵션

* **`-h|--help`**

  명령에 대한 간단한 도움말을 출력합니다.

* **`--msbuild`**

  MSBuild 빌드 서버를 종료합니다.

* **`--razor`**

  Razor 빌드 서버를 종료합니다.

* **`--vbcscompiler`**

  VB/C# 컴파일러 빌드 서버를 종료합니다.
