---
description: C# 컴파일러 옵션. C# 컴파일러의 동작을 제어하는 옵션에 대해 알아봅니다.
title: C# 컴파일러 옵션
ms.date: 03/12/2021
f1_keywords:
- cs.build.options
helpviewer_keywords:
- compiler options [C#]
- csc.exe
- cl.exe compiler, C# options
- Visual C# compiler
- Visual C#, compiler options
ms.assetid: d3403556-1816-4546-a782-e8223a772e44
ms.openlocfilehash: e9fc2fccdb48ab8646cdbf02db14b6ec1b9842df
ms.sourcegitcommit: 5ce37699c2a51ed173171813be68ef7577b1aba5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "104881161"
---
# <a name="c-compiler-options"></a>C# 컴파일러 옵션

이 섹션에서는 C# 컴파일러에서 해석되는 옵션에 대해 설명합니다. .NET 프로젝트에서 컴파일러 옵션을 설정하는 방법에는 두 가지가 있습니다.

- ***\*.csproj 파일에서 옵션 지정***: *\*.csproj* 파일의 모든 컴파일러 옵션에 대해 XML 요소를 추가할 수 있습니다. 요소 이름은 컴파일러 옵션과 동일합니다. XML 요소의 값은 컴파일러 옵션의 값을 설정합니다. 프로젝트 파일에서 옵션을 설정하는 방법에 대한 자세한 내용은 [.NET SDK 프로젝트용 MSBuild 속성](../../../core/project-sdk/msbuild-props.md) 문서를 참조하세요.
- ***Visual Studio 속성 페이지 사용***: Visual Studio는 빌드 속성을 편집할 수 있는 속성 페이지를 제공합니다. 자세히 알아보려면 [프로젝트 및 솔루션 속성 관리 - Windows](/visualstudio/ide/managing-project-and-solution-properties#c-visual-basic-and-f-projects) 또는 [프로젝트 및 솔루션 속성 관리 - Mac](/visualstudio/mac/managing-solutions-and-project-properties)을 참조하세요.

## <a name="net-framework-projects"></a>.NET Framework 프로젝트

> [!IMPORTANT]
> 이 섹션은 .NET Framework 프로젝트에만 적용됩니다.

위에서 설명한 메커니즘 외에도 .NET Framework 프로젝트에 대한 두 가지 추가 메서드를 사용하여 컴파일러 옵션을 설정할 수 있습니다.

- **.NET Framework 프로젝트의 명령줄 인수**: .NET Framework 프로젝트는 프로젝트를 빌드하는 데 `dotnet build` 대신 *csc.exe* 를 사용합니다. .NET Framework 프로젝트에 대한 *csc.exe* 명령줄 인수를 지정할 수 있습니다.
- **컴파일된 ASP.NET 페이지**: .NET Framework 프로젝트는 *web.config* 파일의 섹션을 사용하여 페이지를 컴파일합니다. 새로운 빌드 시스템과 ASP.NET Core 프로젝트의 경우, 프로젝트 파일에서 옵션을 가져옵니다.

일부 컴파일러 옵션의 단어는 *csc.exe* 및 .NET Framework 프로젝트에서 새 MSBuild 시스템으로 변경되었습니다. 이 섹션에서는 새로운 구문이 사용됩니다. 두 버전은 각 페이지의 맨 위에 나열됩니다. *csc.exe* 의 경우, 옵션과 콜론 뒤에 모든 인수가 나열됩니다. 예를 들어 `-doc` 옵션은 다음과 같습니다.

```console
-doc:DocFile.xml
```

명령 프롬프트에서 실행 파일(*csc.exe*)의 이름을 입력하여 C# 컴파일러를 호출할 수 있습니다.

.NET Framework 프로젝트의 경우 명령줄에서 *csc.exe* 를 실행할 수도 있습니다. 모든 컴파일러 옵션은 **-옵션** 및 **/옵션** 의 두 가지 형태로 사용할 수 있습니다. .NET Framework 웹 프로젝트에서는 *web.config* 파일에서 코드 숨김으로 컴파일하는 옵션을 지정합니다. 자세한 내용은 [\<compiler> 요소](../../../framework/configure-apps/file-schema/compiler/compiler-element.md)를 참조하세요.

**Visual Studio용 개발자 명령 프롬프트** 창을 사용하는 경우 필요한 환경 변수가 모두 설정됩니다. 이 도구에 액세스하는 방법에 대한 자세한 내용은 [Visual Studio용 개발자 명령 프롬프트](/visualstudio/ide/reference/command-prompt-powershell)를 참조하세요.

*csc.exe* 실행 파일은 대개 *Windows* 디렉터리 아래의 Microsoft.NET\Framework\\ *\<Version>* 폴더에 있습니다. 이 위치는 개별 컴퓨터의 구성에 따라 다를 수 있습니다. 컴퓨터에 .NET Framework 버전이 두 개 이상 설치된 경우 이 파일의 여러 버전을 찾을 수 있습니다. 해당 설치에 대한 자세한 내용은 [방법: 설치된 .NET Framework 버전 확인](../../../framework/migration-guide/how-to-determine-which-versions-are-installed.md)을 참조하세요.
