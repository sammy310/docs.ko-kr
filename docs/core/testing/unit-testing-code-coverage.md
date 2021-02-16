---
title: 유닛 테스트에 코드 검사 사용
description: .NET 단위 테스트에 코드 검사 기능을 사용하는 방법을 알아봅니다.
author: IEvangelist
ms.author: dapine
ms.date: 02/10/2021
ms.openlocfilehash: 492e036593dcdc81f8256b05183c8f0a9e13b414
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100432662"
---
# <a name="use-code-coverage-for-unit-testing"></a>유닛 테스트에 코드 검사 사용

기능을 확인하는 데 도움이 되는 단위 테스트를 통해 리팩터링 활동을 확인할 수 있습니다. 코드 검사는 단위 테스트에서 실행되는 코드(줄, 분기 또는 메서드)의 양을 측정합니다. 예를 들어 조건부 코드 분기가 두 개(‘분기 a’와 ‘분기 b’)만 포함된 단순한 애플리케이션이 있는 경우 조건부 ‘분기 a’를 확인하는 단위 테스트는 분기 코드 검사 50%를 보고합니다.  

이 문서에서는 Coverlet을 통한 유닛 테스트에 코드 검사 사용과 ReportGenerator를 사용한 보고서 생성을 설명합니다. 이 문서에서는 테스트 프레임워크로 C# 및 xUnit에 초점을 두고 설명하지만 MSTest와 NUnit도 모두 작동합니다. Coverlet은 C#용 플랫폼 간 코드 검사 프레임워크를 제공하는 [GitHub의 오픈 소스 프로젝트](https://github.com/coverlet-coverage/coverlet)입니다. [Coverlet](https://dotnetfoundation.org/projects/coverlet)은 .NET Foundation의 일부입니다. Coverlet은 Cobertura 검사 테스트 실행 데이터를 수집하고, 이 데이터는 보고서 생성에 사용됩니다.

또한 이 문서에서는 Coverlet 테스트 실행에서 수집된 코드 검사 정보를 사용하여 보고서를 생성하는 방법도 자세히 설명합니다. 보고서 생성은 [GitHub의 또 다른 오픈 소스 프로젝트인 ReportGenerator](https://github.com/danielpalme/ReportGenerator)를 사용하여 가능합니다. ReportGenerator는 무엇보다 Cobertura에서 생성된 검사 보고서를 사람이 읽을 수 있는 다양한 형식의 보고서로 변환합니다.

이 문서는 샘플 브라우저에서 사용할 수 있는 [샘플 소스 코드 프로젝트](/samples/dotnet/samples/unit-testing-code-coverage-cs)에 대해 설명합니다.

## <a name="system-under-test"></a>테스트 중인 시스템

“테스트 중인 시스템”은 단위 테스트 작성의 대상 코드를 의미하며 개체, 서비스 또는 테스트 가능한 기능을 노출하는 기타 항목일 수 있습니다. 이 문서의 목적을 위해 테스트 중인 시스템이 될 클래스 라이브러리와 해당하는 두 개의 단위 테스트 프로젝트를 만듭니다.

### <a name="create-a-class-library"></a>클래스 라이브러리 만들기

명령 프롬프트에서 `UnitTestingCodeCoverage`라는 새 디렉터리에 [`dotnet new classlib`](../tools/dotnet-new.md#classlib) 명령을 사용하여 새 .NET 표준 클래스 라이브러리를 만듭니다.

```dotnetcli
dotnet new classlib -n Numbers
```

아래 코드 조각은 숫자가 소수인지 확인하는 기능을 제공하는 단순한 `PrimeService` 클래스를 정의합니다. 아래 코드 조각을 복사하고 *Numbers* 디렉터리에 자동으로 생성된 *Class1.cs* 파일의 내용을 이 코드로 바꿉니다. *Class1.cs* 파일의 이름을 *PrimeService.cs* 로 바꿉니다.

```csharp
namespace System.Numbers
{
    public class PrimeService
    {
        public bool IsPrime(int candidate)
        {
            if (candidate < 2)
            {
                return false;
            }

            for (int divisor = 2; divisor <= Math.Sqrt(candidate); ++divisor)
            {
                if (candidate % divisor == 0)
                {
                    return false;
                }
            }
            return true;
        }
    }
}
```

> [!TIP]
> `Numbers` 클래스 라이브러리는 `System` 네임스페이스에 의도적으로 추가한 것입니다. 이렇게 해야 `using System;` 네임스페이스 선언 없이 <xref:System.Math?displayProperty=fullName>에 액세스할 수 있기 때문입니다. 자세한 내용은 [네임스페이스(C# 참조)](../../csharp/language-reference/keywords/namespace.md)를 참조하세요.

### <a name="create-test-projects"></a>테스트 프로젝트 만들기

동일한 명령 프롬프트에서 [`dotnet new xunit`](../tools/dotnet-new.md#test) 명령을 사용하여 두 개의 새 **xUnit 테스트 프로젝트(.NET Core)** 템플릿을 만듭니다.

```dotnetcli
dotnet new xunit -n XUnit.Coverlet.Collector
```

```dotnetcli
dotnet new xunit -n XUnit.Coverlet.MSBuild
```

새로 만든 xUnit 테스트 프로젝트 둘 다에 *Numbers* 클래스 라이브러리의 프로젝트 참조를 추가해야 합니다. 이렇게 해야만 테스트 프로젝트에서 테스트를 위해 *PrimeService* 에 액세스할 수 있습니다. 명령 프롬프트에서 [`dotnet add`](../tools/dotnet-add-reference.md) 명령을 사용합니다.

```dotnetcli
dotnet add XUnit.Coverlet.Collector\XUnit.Coverlet.Collector.csproj reference Numbers\Numbers.csproj
```

```dotnetcli
dotnet add XUnit.Coverlet.MSBuild\XUnit.Coverlet.MSBuild.csproj reference Numbers\Numbers.csproj
```

*MSBuild* 프로젝트의 이름을 [coverlet.msbuild](https://www.nuget.org/packages/coverlet.msbuild) NuGet 패키지에 따라 적절하게 지정합니다. [`dotnet add package`](../tools/dotnet-add-package.md) 명령을 실행하여 이 패키지 종속성을 추가합니다.

```dotnetcli
cd XUnit.Coverlet.MSBuild && dotnet add package coverlet.msbuild && cd ..
```

이전 명령은 디렉터리를 변경하여 결과적으로 범위를 *MSBuild* 테스트 프로젝트로 지정한 다음 NuGet 패키지를 추가했습니다. 그런 다음 디렉터리를 한 수준 위로 변경했습니다.

*UnitTest1.cs* 파일을 모두 열고 내용을 다음 코드 조각으로 바꿉니다. *UnitTest1.cs* 파일의 이름을 *PrimeServiceTests.cs* 로 바꿉니다.

```csharp
using System.Numbers;
using Xunit;

namespace XUnit.Coverlet
{
    public class PrimeServiceTests
    {
        readonly PrimeService _primeService;

        public PrimeServiceTests() => _primeService = new PrimeService();

        [
            Theory,
            InlineData(-1), InlineData(0), InlineData(1)
        ]
        public void IsPrime_ValuesLessThan2_ReturnFalse(int value) =>
            Assert.False(_primeService.IsPrime(value), $"{value} should not be prime");

        [
            Theory,
            InlineData(2), InlineData(3), InlineData(5), InlineData(7)
        ]
        public void IsPrime_PrimesLessThan10_ReturnTrue(int value) =>
            Assert.True(_primeService.IsPrime(value), $"{value} should be prime");

        [
            Theory,
            InlineData(4), InlineData(6), InlineData(8), InlineData(9)
        ]
        public void IsPrime_NonPrimesLessThan10_ReturnFalse(int value) =>
            Assert.False(_primeService.IsPrime(value), $"{value} should not be prime");
    }
}
```

### <a name="create-a-solution"></a>솔루션 만들기

명령 프롬프트에서 위 클래스 라이브러리와 두 개의 테스트 프로젝트를 캡슐화할 새 솔루션을 만듭니다. 다음과 같이 [`dotnet sln`](../tools/dotnet-sln.md) 명령을 사용합니다.

```dotnetcli
dotnet new sln -n XUnit.Coverage
```

그러면 *UnitTestingCodeCoverage* 디렉터리에 `XUnit.Coverage`라는 새 솔루션 파일 이름이 만들어집니다. 솔루션의 루트에 프로젝트를 추가합니다.

## <a name="linux"></a>[Linux](#tab/linux)

```dotnetcli
dotnet sln XUnit.Coverage.sln add **/*.csproj --in-root
```

## <a name="windows"></a>[Windows](#tab/windows)

```dotnetcli
dotnet sln XUnit.Coverage.sln add (ls **/*.csproj) --in-root
```

---

[`dotnet build`](../tools/dotnet-build.md) 명령을 사용하여 솔루션을 빌드합니다.

```dotnetcli
dotnet build
```

빌드가 성공하면 세 개의 프로젝트를 만들고, 프로젝트와 패키지를 적절히 참조하고, 소스 코드를 올바로 업데이트한 것입니다. 훌륭합니다!

## <a name="tooling"></a>도구

코드 검사 도구의 두 가지 유형은 다음과 같습니다.

- **DataCollectors:** DataCollectors는 테스트 실행을 모니터링하고 테스트 실행에 관한 정보를 수집합니다. 수집한 정보는 XML 및 JSON과 같은 다양한 출력 형식으로 보고합니다. 자세한 내용은 [your first DataCollector](https://github.com/Microsoft/vstest-docs/blob/master/docs/extensions/datacollector.md)(첫 번째 DataCollector)를 참조하세요.
- **보고서 생성기:** 테스트 실행에서 수집된 데이터를 사용하여 보고서를 생성합니다. 주로 HTML 스타일의 보고서를 생성합니다.

이 섹션에서는 데이터 수집기 도구를 주로 설명합니다. 코드 검사에 Coverlet을 사용하려면 기존 단위 테스트 프로젝트에 적절한 패키지 종속성이 있어야 하거나 [.NET 전역 도구](../tools/global-tools.md)와 해당하는 [coverlet.console](https://www.nuget.org/packages/coverlet.console) NuGet 패키지를 사용해야 합니다.

## <a name="integrate-with-net-test"></a>.NET 테스트와 통합

xUnit 테스트 프로젝트 템플릿은 기본적으로 [coverlet.collector](https://www.nuget.org/packages/coverlet.collector)와 이미 통합되어 있습니다.
명령 프롬프트에서 디렉터리를 *XUnit.Coverlet.Collector* 프로젝트로 변경하고 [`dotnet test`](../tools/dotnet-test.md) 명령을 실행합니다.

```dotnetcli
cd XUnit.Coverlet.Collector && dotnet test --collect:"XPlat Code Coverage"
```

> [!NOTE]
> `"XPlat Code Coverage"` 인수는 Coverlet의 데이터 수집기에 해당하는 식별 이름입니다. 이 이름은 필수이지만 대/소문자를 구분하지 않습니다.

`dotnet test` 실행의 일부로 결과 *coverage.cobertura.xml* 파일이 *TestResults* 디렉터리에 출력됩니다. 이 XML 파일에 결과가 포함됩니다. 이 플랫폼 간 옵션은 .NET Core CLI를 사용하므로 MSBuild를 사용할 수 없는 빌드 시스템에 유용합니다.

다음은 예제 *coverage.cobertura.xml* 파일입니다.

```xml
<?xml version="1.0" encoding="utf-8"?>
<coverage line-rate="1" branch-rate="1" version="1.9" timestamp="1592248008"
          lines-covered="12" lines-valid="12" branches-covered="6" branches-valid="6">
  <sources>
    <source>C:\</source>
  </sources>
  <packages>
    <package name="Numbers" line-rate="1" branch-rate="1" complexity="6">
      <classes>
        <class name="Numbers.PrimeService" line-rate="1" branch-rate="1" complexity="6"
               filename="Numbers\PrimeService.cs">
          <methods>
            <method name="IsPrime" signature="(System.Int32)" line-rate="1"
                    branch-rate="1" complexity="6">
              <lines>
                <line number="8" hits="11" branch="False" />
                <line number="9" hits="11" branch="True" condition-coverage="100% (2/2)">
                  <conditions>
                    <condition number="7" type="jump" coverage="100%" />
                  </conditions>
                </line>
                <line number="10" hits="3" branch="False" />
                <line number="11" hits="3" branch="False" />
                <line number="14" hits="22" branch="True" condition-coverage="100% (2/2)">
                  <conditions>
                    <condition number="57" type="jump" coverage="100%" />
                  </conditions>
                </line>
                <line number="15" hits="7" branch="False" />
                <line number="16" hits="7" branch="True" condition-coverage="100% (2/2)">
                  <conditions>
                    <condition number="27" type="jump" coverage="100%" />
                  </conditions>
                </line>
                <line number="17" hits="4" branch="False" />
                <line number="18" hits="4" branch="False" />
                <line number="20" hits="3" branch="False" />
                <line number="21" hits="4" branch="False" />
                <line number="23" hits="11" branch="False" />
              </lines>
            </method>
          </methods>
          <lines>
            <line number="8" hits="11" branch="False" />
            <line number="9" hits="11" branch="True" condition-coverage="100% (2/2)">
              <conditions>
                <condition number="7" type="jump" coverage="100%" />
              </conditions>
            </line>
            <line number="10" hits="3" branch="False" />
            <line number="11" hits="3" branch="False" />
            <line number="14" hits="22" branch="True" condition-coverage="100% (2/2)">
              <conditions>
                <condition number="57" type="jump" coverage="100%" />
              </conditions>
            </line>
            <line number="15" hits="7" branch="False" />
            <line number="16" hits="7" branch="True" condition-coverage="100% (2/2)">
              <conditions>
                <condition number="27" type="jump" coverage="100%" />
              </conditions>
            </line>
            <line number="17" hits="4" branch="False" />
            <line number="18" hits="4" branch="False" />
            <line number="20" hits="3" branch="False" />
            <line number="21" hits="4" branch="False" />
            <line number="23" hits="11" branch="False" />
          </lines>
        </class>
      </classes>
    </package>
  </packages>
</coverage>
```

> [!TIP]
> 또는 빌드 시스템에서 이미 MSBuild를 사용하는 경우 MSBuild 패키지를 사용할 수도 있습니다. 명령 프롬프트에서 디렉터리를 *XUnit.Coverlet.MSBuild* 프로젝트로 변경하고 `dotnet test` 명령을 실행합니다.
>
> ```dotnetcli
> dotnet test /p:CollectCoverage=true /p:CoverletOutputFormat=cobertura
> ```
>
> 결과 *coverage.cobertura.xml* 파일이 출력됩니다.
> [여기](https://github.com/coverlet-coverage/coverlet/blob/master/Documentation/MSBuildIntegration.md)에서 msbuild 통합 가이드를 따르면 됩니다.

## <a name="generate-reports"></a>보고서 생성

이제 단위 테스트 실행에서 데이터를 수집할 수 있으므로 [ReportGenerator](https://github.com/danielpalme/ReportGenerator)를 사용하여 보고서를 생성할 수 있습니다. [ReportGenerator](https://www.nuget.org/packages/dotnet-reportgenerator-globaltool) NuGet 패키지를 [.NET 전역 도구](../tools/global-tools.md)로 설치하려면 [`dotnet tool install`](../tools/dotnet-tool-install.md) 명령을 사용합니다.

```dotnetcli
dotnet tool install -g dotnet-reportgenerator-globaltool
```

이전 테스트 실행에서 *coverage.cobertura.xml* 파일이 출력된 경우 도구를 실행하고 원하는 옵션을 제공합니다.

```console
reportgenerator
"-reports:Path\To\TestProject\TestResults\{guid}\coverage.cobertura.xml"
"-targetdir:coveragereport"
-reporttypes:Html
```

이 명령을 실행한 후의 HTML 파일이 생성되는 보고서입니다.

:::image type="content" source="media/test-report.png" lightbox="media/test-report.png" alt-text="단위 테스트 생성 보고서":::

## <a name="see-also"></a>참조

- [Visual Studio 단위 테스트 코드 검사](/visualstudio/test/using-code-coverage-to-determine-how-much-code-is-being-tested)
- [GitHub - Coverlet repository](https://github.com/coverlet-coverage/coverlet)(GitHub - Coverlet 리포지토리)
- [GitHub - ReportGenerator repository](https://github.com/danielpalme/ReportGenerator)(GitHub - ReportGenerator 리포지토리)
- [ReportGenerator 프로젝트 사이트](https://danielpalme.github.io/ReportGenerator)
- [.NET Core CLI 테스트 명령](../tools/dotnet-test.md)
- [샘플 소스 코드](/samples/dotnet/samples/unit-testing-code-coverage-cs)

## <a name="next-steps"></a>다음 단계

> [!div class="nextstepaction"]
> [단위 테스트 모범 사례](unit-testing-best-practices.md)
