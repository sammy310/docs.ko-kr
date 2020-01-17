---
title: dotnet test 및 xUnit을 사용하여 .NET Core에서 C# 코드 유닛 테스트
description: dotnet test 및 xUnit을 사용하여 샘플 솔루션을 단계별로 빌드하는 대화형 환경을 통해 C# 및 .NET Core의 단위 테스트 개념을 알아봅니다.
author: ardalis
ms.author: wiwagn
ms.date: 12/04/2019
ms.openlocfilehash: 226db54047747fbd065c64f5e4812094921c7f62
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/07/2020
ms.locfileid: "75714231"
---
# <a name="unit-testing-c-in-net-core-using-dotnet-test-and-xunit"></a>dotnet 테스트 및 xUnit을 사용하여 .NET Core에서 C# 단위 테스트

이 자습서에서는 단위 테스트 프로젝트 및 소스 코드 프로젝트를 포함하는 솔루션을 빌드하는 방법을 보여줍니다. 미리 빌드된 솔루션을 사용하여 이 자습서를 진행하려면 [샘플 코드를 보거나 다운로드](https://github.com/dotnet/samples/tree/master/core/getting-started/unit-testing-using-dotnet-test/)합니다. 다운로드 지침은 [샘플 및 자습서](../../samples-and-tutorials/index.md#viewing-and-downloading-samples)를 참조하세요.

## <a name="create-the-solution"></a>솔루션 만들기

이 섹션에서는 원본 및 테스트 프로젝트를 포함하는 솔루션을 만듭니다. 완료된 솔루션은 다음과 같은 디렉터리 구조를 갖습니다.

```
/unit-testing-using-dotnet-test
    unit-testing-using-dotnet-test.sln
    /PrimeService
        PrimeService.cs
        PrimeService.csproj
    /PrimeService.Tests
        PrimeService_IsPrimeShould.cs
        PrimeServiceTests.csproj
```

다음 지침에서는 테스트 솔루션을 만드는 단계를 제공합니다. 한 단계로 테스트 솔루션을 만드는 방법에 대한 지침은 [테스트 솔루션을 만드는 명령](#create-test-cmd)을 참조하세요.

* 셸 창을 엽니다.
* 다음 명령을 실행합니다.

  ```dotnetcli
  dotnet new sln -o unit-testing-using-dotnet-test
  ```

  [`dotnet new sln`](../tools/dotnet-new.md) 명령은 *unit-testing-using-dotnet-test* 디렉터리에서 새 솔루션을 만듭니다.
* 디렉터리를 *unit-testing-using-dotnet-test* 폴더로 변경합니다.
* 다음 명령을 실행합니다.

  ```dotnetcli
  dotnet new classlib -o PrimeService
  ```

   [`dotnet new classlib`](../tools/dotnet-new.md) 명령은 *PrimeService* 폴더에 새 클래스 라이브러리 프로젝트를 만듭니다. 새 클래스 라이브러리에는 테스트할 코드가 포함됩니다.
* *Class1.cs*의 이름을 *PrimeService.cs*로 바꿉니다.
* *PrimeService.cs*의 코드를 다음 코드로 바꿉니다.
  
  ```csharp
    using System;

    namespace Prime.Services
    {
        public class PrimeService
        {
            public bool IsPrime(int candidate)
            {
                throw new NotImplementedException("Not implemented.");
            }
        }
    }
  ```

* 위의 코드는
  * 구현되지 않았음을 나타내는 메시지와 함께 <xref:System.NotImplementedException>을 throw합니다.
  * 자습서의 뒷부분에서 업데이트됩니다.

<!-- preceding code shows an english bias. Message makes no sense outside english -->

* *unit-testing-using-dotnet-test* 디렉터리에서 다음 명령을 실행하여 클래스 라이브러리 프로젝트를 솔루션에 추가합니다.

  ```dotnetcli
  dotnet sln add ./PrimeService/PrimeService.csproj
  ```

* 다음 명령을 실행하여 *PrimeService.Tests* 프로젝트를 만듭니다.

  ```dotnetcli
  dotnet new xunit -o PrimeService.Tests
  ```

* 이전 명령은
  * *PrimeService.Tests* 디렉터리에 *PrimeService.Tests* 프로젝트를 만듭니다. 테스트 프로젝트는 [xUnit](https://xunit.github.io/)을 테스트 라이브러리로 사용합니다.
  * 프로젝트 파일에 다음 `<PackageReference />` 요소를 추가하여 Test Runner를 구성합니다.
    * "Microsoft.NET.Test.Sdk"
    * "xunit"
    * "xunit.runner.visualstudio"

* 다음 명령을 실행하여 솔루션 파일에 테스트 프로젝트를 추가합니다.

  ```dotnetcli
  dotnet sln add ./PrimeService.Tests/PrimeService.Tests.csproj
  ```

* `PrimeService` 클래스 라이브러리를 *PrimeService.Tests* 프로젝트에 대한 종속성으로 추가합니다.

  ```dotnetcli
  dotnet add ./PrimeService.Tests/PrimeService.Tests.csproj reference ./PrimeService/PrimeService.csproj  
  ```

<a name="create-test-cmd"></a>

### <a name="commands-to-create-the-solution"></a>솔루션을 만드는 명령

이 섹션에는 이전 섹션의 모든 명령이 요약되어 있습니다. 이전 섹션의 단계를 완료한 경우에는 이 섹션을 건너뜁니다.

다음 명령은 Windows 머신에서 테스트 솔루션을 만듭니다. macOS 및 Unix의 경우 `ren` 명령을 `ren` OS 버전으로 업데이트하여 파일 이름을 바꿉니다.

```dotnetcli
dotnet new sln -o unit-testing-using-dotnet-test
cd unit-testing-using-dotnet-test
dotnet new classlib -o PrimeService
ren .\PrimeService\Class1.cs PrimeService.cs
dotnet sln add ./PrimeService/PrimeService.csproj
dotnet new xunit -o PrimeService.Tests
dotnet add ./PrimeService.Tests/PrimeService.Tests.csproj reference ./PrimeService/PrimeService.csproj
dotnet sln add ./PrimeService.Tests/PrimeService.Tests.csproj
```

이전 섹션에 있는 "*PrimeService.cs*의 코드를 다음 코드로 바꾸기" 지침을 따릅니다.

## <a name="create-a-test"></a>테스트 만들기

TDD(테스트 기반 개발)에서 널리 사용되는 방식은 대상 코드를 구현하기 전에 테스트를 작성하는 것입니다. 이 자습서에서는 TDD 방식을 사용합니다. `IsPrime` 메서드는 호출할 수 있지만 구현되지 않습니다. `IsPrime`에 대한 테스트 호출이 실패합니다. TDD를 사용하면 실패하는 것으로 알려진 테스트가 작성됩니다. 테스트가 통과하도록 대상 코드가 업데이트됩니다. 이 방식을 계속 반복하여 실패한 테스트를 작성한 후 대상 코드를 업데이트하여 통과합니다.

*PrimeService.Tests* 프로젝트 업데이트:

* *PrimeService.Tests/UnitTest1.cs*를 삭제합니다.
* *PrimeService.Tests/PrimeService_IsPrimeShould.cs* 파일을 만듭니다.
* *PrimeService_IsPrimeShould.cs*의 코드를 다음 코드로 바꿉니다.

```csharp
using Xunit;
using Prime.Services;

namespace Prime.UnitTests.Services
{
    public class PrimeService_IsPrimeShould
    {
        private readonly PrimeService _primeService;

        public PrimeService_IsPrimeShould()
        {
            _primeService = new PrimeService();
        }

        [Fact]
        public void IsPrime_InputIs1_ReturnFalse()
        {
            var result = _primeService.IsPrime(1);

            Assert.False(result, "1 should not be prime");
        }
    }
}
```

`[Fact]` 특성은 Test Runner에서 실행하는 테스트 메서드를 선언합니다. *Primeservice.tests* 폴더에서 `dotnet test`를 실행합니다. [dotnet test](../tools/dotnet-test.md) 명령은 두 프로젝트를 모두 빌드하고 테스트를 실행합니다. xUnit Test Runner에는 테스트를 실행할 프로그램 진입점이 포함되어 있습니다. `dotnet test`는 단위 테스트 프로젝트를 사용하여 Test Runner를 시작합니다.

`IsPrime`이 구현되지 않았기 때문에 테스트가 실패합니다. TDD 방식을 사용하여 이 테스트가 통과할 수 있는 코드만 작성합니다. 다음 코드를 사용하여 `IsPrime`을 업데이트합니다.

```csharp
public bool IsPrime(int candidate)
{
    if (candidate == 1)
    {
        return false;
    }
    throw new NotImplementedException("Not fully implemented.");
}
```

`dotnet test`를 실행합니다. 테스트가 통과됩니다.

### <a name="add-more-tests"></a>더 많은 테스트 추가

0 및 -1에 대한 소수 테스트를 추가합니다. 이전 테스트를 복사하고 다음 코드를 변경하여 0 및 -1을 사용할 수 있습니다.

```csharp
var result = _primeService.IsPrime(1);

Assert.False(result, "1 should not be prime");
```

매개 변수만 변경될 때 테스트 코드를 복사하면 코드 중복 및 테스트 블로트가 발생합니다. 다음 xUnit 특성은 유사한 테스트 모음을 작성하는 데 사용할 수 있습니다.

- `[Theory]`는 같은 코드를 실행하지만, 다른 입력 인수가 포함된 테스트 모음을 나타냅니다.

- `[InlineData]` 특성은 해당 입력에 대한 값을 지정합니다.

새 테스트를 만들지 않고 앞의 xUnit 특성을 적용하여 단일 이론을 만듭니다. 코드 바꾸기 대상:

```csharp
[Fact]
public void IsPrime_InputIs1_ReturnFalse()
{
    var result = _primeService.IsPrime(1);

    Assert.False(result, "1 should not be prime");
}
```

다음 코드로 바꾸기:

[!code-csharp[Sample_TestCode](../../../samples/core/getting-started/unit-testing-using-dotnet-test/PrimeService.Tests/PrimeService_IsPrimeShould.cs?name=Sample_TestCode)]

앞의 코드에서 `[Theory]` 및 `[InlineData]`를 사용하여 2보다 작은 몇 가지 값을 테스트할 수 있습니다. 2는 가장 작은 소수입니다.

`dotnet test`를 실행하면 두 가지 테스트가 실패합니다. 모든 테스트를 통과하도록 하려면 다음 코드를 사용하여 `IsPrime` 메서드를 업데이트합니다.

```csharp
public bool IsPrime(int candidate)
{
    if (candidate < 2)
    {
        return false;
    }
    throw new NotImplementedException("Not fully implemented.");
}
```

TDD 방식에 따라 실패하는 테스트를 더 추가한 후 대상 코드를 업데이트합니다. [테스트의 완료된 버전](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-dotnet-test/PrimeService.Tests/PrimeService_IsPrimeShould.cs) 및 [라이브러리의 완전한 구현](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-dotnet-test/PrimeService/PrimeService.cs)을 참조하세요.

완료된 `IsPrime` 메서드는 소수판별 테스트를 위한 효율적인 알고리즘이 아닙니다.

### <a name="additional-resources"></a>추가 자료

- [xUnit.net 공식 사이트](https://xunit.github.io)
- [ASP.NET Core에서 컨트롤러 논리 테스트](/aspnet/core/mvc/controllers/testing)
- [`dotnet add reference`](../tools/dotnet-add-reference.md)
