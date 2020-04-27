---
title: C# 프로그램 구조 - C# 언어 둘러보기
description: C# 프로그램의 기본 구성 요소에 대해 알아보기
ms.date: 02/25/2020
ms.assetid: 984f0314-507f-47a0-af56-9011243f5e65
ms.openlocfilehash: c0a4dcaed7b53a7da7008d6000b3bec2ffe3ee7b
ms.sourcegitcommit: 839777281a281684a7e2906dccb3acd7f6a32023
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/24/2020
ms.locfileid: "82141021"
---
# <a name="program-structure"></a>프로그램 구조

C#의 핵심적인 조직 개념은 ***프로그램***, ***네임스페이스***, ***형식***, ***멤버*** 및 ***어셈블리***입니다. C# 프로그램은 하나 이상의 소스 파일로 구성됩니다. 프로그램은 멤버를 포함하고 네임스페이스로 구성될 수 있는 형식을 선언합니다. 클래스와 인터페이스는 형식의 예입니다. 필드, 메서드, 속성 및 이벤트는 멤버의 예입니다. C# 프로그램을 컴파일하면 실제로 어셈블리로 패키지됩니다. 어셈블리는 일반적으로 ***애플리케이션***을 구현하는지 또는 ***라이브러리***를 구현하는지에 따라 각각 파일 확장명 `.exe` 또는 `.dll`을 갖습니다.

`dotnet new` 명령을 사용하여 이름이 *acme*인 라이브러리 프로젝트를 만들 수 있습니다.

```dotnetcli
dotnet new classlib -o acme
```

이 프로젝트에서 `Acme.Collections`라는 네임스페이스에 이름이 `Stack`인 클래스를 선언합니다.

[!code-csharp[Stack](../../../samples/snippets/csharp/tour/program-structure/program.cs#L1-L34)]

이 클래스의 정규화된 이름은 `Acme.Collections.Stack`입니다. 클래스에는 필드 `top`, 2개의 메서드 `Push` 및 `Pop`, 중첩된 클래스 `Entry` 등의 여러 멤버가 포함됩니다. `Entry` 클래스는 필드 `next` 및 필드 `data`, 생성자의 세 멤버가 포함됩니다. 다음 명령은

```dotnetcli
dotnet build
```

예제를 라이브러리(`Main` 진입점이 없는 코드)를 컴파일하고 `acme.dll`이라는 어셈블리를 생성합니다.

어셈블리에는 IL(중간 언어) 명령 형식의 실행 코드와 메타데이터 형식의 기호 정보가 포함됩니다. 어셈블리가 실행되기 전에, .NET 공용 언어 런타임의 JIT(Just-In-Time) 컴파일러가 어셈블리 안의 IL 코드를 해당 프로세서에 맞는 코드로 변환합니다.

어셈블리는 코드와 메타데이터를 모두 포함하는 기능의 자체 설명 단위이므로 C#에서는 `#include` 지시문과 헤더 파일이 필요하지 않습니다. 특정 어셈블리에 포함된 공용 형식 및 멤버는 프로그램을 컴파일할 때 해당 어셈블리를 참조하는 것만으로 C# 프로그램에서 사용 가능해집니다. 예를 들어 이 프로그램에서는 `acme.dll` 어셈블리의 `Acme.Collections.Stack` 클래스를 사용합니다.

[!code-csharp[UsingStack](../../../samples/snippets/csharp/tour/program-structure/Program.cs#L38-L52)]

앞에 나온 프로그램 프로젝트의 *csproj* 파일은 C# 컴파일러에 대한 참조 노드를 포함해야 `acme.dll` 어셈블리에 있는 클래스에 대한 참조를 확인할 수 있습니다.

```xml
  <ItemGroup>
    <ProjectReference Include="..\acme\acme.csproj" />
  </ItemGroup>
```

위와 같이 추가한 후에, `dotnet build`는 이름이 `example.exe`인 실행 가능한 어셈블리를 만들고, 이 어셈블리가 실행되면 다음과 같은 출력이 생성됩니다.

```dotnetcli
100
10
1
```

C#은 프로그램의 소스 텍스트가 여러 소스 파일에 저장되도록 허용합니다. 다중 파일 C# 프로그램이 컴파일되면 모든 소스 파일이 함께 처리되고 소스 파일은 서로 자유롭게 참조될 수 있습니다. 개념적으로는 마치 모든 소스 파일이 처리되기 전에 하나의 큰 파일로 연결되는 것처럼 보입니다. 소수의 경우를 제외하고 선언 순서는 중요하지 않으므로 C#에서는 정방향 선언이 필요한 경우가 없습니다. C#은 소스 파일을 하나의 공용 형식만 선언하도록 제한하거나 소스 파일 이름이 소스 파일에 선언된 형식과 일치하도록 요구하지 않습니다.

>[!div class="step-by-step"]
>[이전](index.md)
>[다음](types-and-variables.md)
