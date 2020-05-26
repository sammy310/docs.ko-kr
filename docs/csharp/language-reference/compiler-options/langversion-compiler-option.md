---
title: -langversion(C# 컴파일러 옵션)
ms.date: 05/20/2020
f1_keywords:
- /langversion
helpviewer_keywords:
- /langversion compiler option [C#]
- -langversion compiler option [C#]
- langversion compiler option [C#]
ms.assetid: 3fb00b05-a0ff-4782-b313-13a4c0f62d94
ms.openlocfilehash: 408b2fb1f19f872db675321601ebc1b0c921044b
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/22/2020
ms.locfileid: "83802946"
---
# <a name="-langversion-c-compiler-options"></a>-langversion(C# 컴파일러 옵션)

컴파일러가 선택한 C# 언어 사양에 포함된 구문만 허용하도록 합니다.

## <a name="syntax"></a>구문

```console
-langversion:option
```

## <a name="arguments"></a>인수

`option`

유효한 값은 다음과 같습니다.

[!INCLUDE [lang-versions-table](../includes/langversion-table.md)]

기본 언어 버전은 애플리케이션의 대상 프레임워크 및 SDK 또는 Visual Studio의 버전에 따라 다릅니다. 해당 규칙은 [언어 버전 구성](../configure-language-version.md#defaults) 문서에 정의되어 있습니다.

## <a name="remarks"></a>설명

C# 애플리케이션에서 참조된 메타데이터에는 **-langversion** 컴파일러 옵션이 적용되지 않습니다.

각 C# 컴파일러 버전에 언어 사양의 확장이 포함되어 있으므로 **-langversion**은 이전 컴파일러 버전의 동등한 기능을 제공하지 않습니다.

또한 C# 버전 업데이트는 일반적으로 주 .NET Framework 릴리스와 일치하는 반면, 새 구문과 기능이 반드시 특정 프레임워크 버전에 연결되지는 않습니다. 새로운 기능에는 C# 버전과 함께 릴리스된 새 컴파일러 업데이트가 분명히 필요하지만, 각 특정 기능에 고유한 최소 .NET API 또는 공용 언어 런타임 요구 사항이 있으므로 NuGet 패키지 또는 다른 라이브러리를 포함하여 하위 수준 프레임워크에서 실행이 허용될 수도 있습니다.

사용하는 **-langversion** 설정과 관계없이 현재 버전의 공용 언어 런타임을 사용하여 고유한 .exe 또는 .dll을 만듭니다. 한 가지 예외는 friend 어셈블리와 [-moduleassemblyname(C# 컴파일러 옵션)](./moduleassemblyname-compiler-option.md)으로, **-langversion:ISO-1**에서 작동합니다.

C# 언어 버전을 지정하는 다른 방법은 [C# 언어 버전 선택](../configure-language-version.md) 문서를 참조하세요.

이 컴파일러 옵션을 프로그래밍 방식으로 설정하는 방법에 대한 자세한 내용은 <xref:VSLangProj80.CSharpProjectConfigurationProperties3.LanguageVersion%2A>을 참조하십시오.

## <a name="c-language-specification"></a>C# 언어 사양

| 버전          | 링크                       | 설명                                                             |
|------------------|----------------------------|-------------------------------------------------------------------------|
| C# 7.0 이상 |                            | 현재 사용할 수 없음                                                 |
| C# 6.0           | [링크][csharp-6]           | C# 언어 사양 버전 6 - 비공식 초안: .NET Foundation |
| C# 5.0           | [PDF 다운로드][csharp-5]   | 표준 ECMA-334 다섯 번째 버전                                           |
| C# 3.0           | [DOC 다운로드][csharp-3]   | C# 언어 사양 버전 3.0: Microsoft Corporation            |
| C# 2.0           | [PDF 다운로드][csharp-2]   | 표준 ECMA-334 네 번째 버전                                           |
| C# 1.2           | [DOC 다운로드][csharp-1.2] | C# 언어 사양 버전 1.2: Microsoft Corporation            |
| C# 1.0           | [DOC 다운로드][csharp-1]   | C# 언어 사양 버전 1.0: Microsoft Corporation            |

[csharp-6]: /dotnet/csharp/language-reference/language-specification/introduction
[csharp-5]: https://www.ecma-international.org/publications/files/ECMA-ST/ECMA-334.pdf
[csharp-3]: https://download.microsoft.com/download/3/8/8/388e7205-bc10-4226-b2a8-75351c669b09/CSharp%20Language%20Specification.doc
[csharp-2]: https://www.ecma-international.org/publications/files/ECMA-ST-ARCH/ECMA-334%204th%20edition%20June%202006.pdf
[csharp-1.2]: https://www.ecma-international.org/publications/files/ECMA-ST-ARCH/ECMA-334%202nd%20edition%20December%202002.pdf
[csharp-1]: https://www.ecma-international.org/publications/files/ECMA-ST-ARCH/ECMA-334%201st%20edition%20December%202001.pdf

## <a name="minimum-sdk-version-needed-to-support-all-language-features"></a>모든 언어 기능을 지원하는 데 필요한 최소 SDK 버전

다음 표에서는 해당 언어 버전을 지원하는 C# 컴파일러가 포함된 SDK의 최소 버전을 보여줍니다.

| C# 버전 | 최소 SDK 버전                                                                  |
|------------|--------------------------------------------------------------------------------------|
| C# 8.0     | Microsoft Visual Studio/Build Tools 2019, 버전 16.3 또는 .NET Core 3.0 SDK         |
| C# 7.3     | Microsoft Visual Studio/Build Tools 2017 버전 15.7                               |
| C# 7.2     | Microsoft Visual Studio/Build Tools 2017 버전 15.5                               |
| C# 7.1     | Microsoft Visual Studio/Build Tools 2017 버전 15.3                               |
| C# 7.0     | Microsoft Visual Studio/Build Tools 2017                                             |
| C# 6       | Microsoft Visual Studio/Build Tools 2015                                             |
| C# 5       | Microsoft Visual Studio/Build Tools 2012 또는 번들 .NET Framework 4.5 컴파일러      |
| C# 4       | Microsoft Visual Studio/Build Tools 2010 또는 번들 .NET Framework 4.0 컴파일러      |
| C# 3       | Microsoft Visual Studio/Build Tools 2008 또는 번들 .NET Framework 3.5 컴파일러      |
| C# 2       | Microsoft Visual Studio/Build Tools 2005 또는 번들 .NET Framework 2.0 컴파일러      |
| C# 1.0/1.2 | Microsoft Visual Studio/Build Tools .NET 2002 또는 번들된 .NET Framework 1.0 컴파일러 |

## <a name="see-also"></a>참조

- [C# 컴파일러 옵션](index.md)
- [프로젝트 및 솔루션 속성 관리](/visualstudio/ide/managing-project-and-solution-properties)
