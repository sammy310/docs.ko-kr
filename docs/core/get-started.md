---
title: .NET 시작
description: Hello World .NET 앱을 만듭니다.
author: adegeo
ms.author: adegeo
ms.date: 09/29/2020
ms.custom: vs-dotnet
ms.openlocfilehash: 6ad2b96e668c52ee80b707e31a63eac2433f3c9e
ms.sourcegitcommit: a8a205034eeffc7c3e1bdd6f506a75b0f7099ebf
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2020
ms.locfileid: "91756093"
---
# <a name="get-started-with-net"></a>.NET 시작

이 문서에서는 “Hello World!” .NET 앱을 만들고 실행하는 방법을 알아봅니다.

.NET이 무엇인지 잘 모른다면 [.NET 소개](introduction.md)에서 시작합니다.

## <a name="create-an-application"></a>애플리케이션 만들기

먼저 컴퓨터에 [.NET SDK](https://dotnet.microsoft.com/download/dotnet-core)를 다운로드하여 설치합니다.

다음으로 **PowerShell**, **명령 프롬프트** 또는 **Bash**와 같은 터미널을 엽니다. 다음 `dotnet` 명령을 입력하여 C# 애플리케이션을 만들고 실행합니다.

```dotnetcli
dotnet new console --output sample1
dotnet run --project sample1
```

다음 출력이 표시됩니다.

```output
Hello World!
```

축하합니다! 간단한 .NET 애플리케이션을 만들었습니다.

## <a name="next-steps"></a>다음 단계

[단계별 자습서](../standard/get-started.md)를 따르거나 YouTube에서 [.NET 101 동영상](https://www.youtube.com/playlist?list=PLdo4fOcmZ0oWoazjhXQzBKMrFuArxpW80)을 보면서 .NET 애플리케이션 개발을 시작합니다.
