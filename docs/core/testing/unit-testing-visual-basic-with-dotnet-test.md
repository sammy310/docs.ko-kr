---
title: dotnet test 및 xUnit을 사용하여 .NET Core에서 Visual Basic 단위 테스트
description: dotnet test 및 xUnit을 사용하여 샘플 Visual Basic 솔루션을 단계별로 빌드하는 대화형 환경을 통해 .NET Core의 단위 테스트 개념을 알아봅니다.
author: billwagner
ms.author: wiwagn
ms.date: 05/18/2020
ms.openlocfilehash: d384bf08f0b6031a519a8430c876eafc05d03a2e
ms.sourcegitcommit: c4a15c6c4ecbb8a46ad4e67d9b3ab9b8b031d849
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/20/2020
ms.locfileid: "88656425"
---
# <a name="unit-testing-visual-basic-net-core-libraries-using-dotnet-test-and-xunit"></a>dotnet test 및 xUnit을 사용하여 Visual Basic .NET Core 라이브러리 유닛 테스트

이 자습서에서는 단위 테스트 프로젝트 및 라이브러리 프로젝트를 포함하는 솔루션을 빌드하는 방법을 보여줍니다. 미리 빌드된 솔루션을 사용하여 이 자습서를 진행하려면 [샘플 코드를 보거나 다운로드](https://github.com/dotnet/samples/tree/master/core/getting-started/unit-testing-using-dotnet-test/)합니다. 다운로드 지침은 [샘플 및 자습서](../../samples-and-tutorials/index.md#view-and-download-samples)를 참조하세요.

## <a name="create-the-solution"></a>솔루션 만들기

이 섹션에서는 원본 및 테스트 프로젝트를 포함하는 솔루션을 만듭니다. 완료된 솔루션은 다음과 같은 디렉터리 구조를 갖습니다.

```
/unit-testing-using-dotnet-test
    unit-testing-using-dotnet-test.sln
    /PrimeService
        PrimeService.vb
        PrimeService.vbproj
    /PrimeService.Tests
        PrimeService_IsPrimeShould.vb
        PrimeServiceTests.vbproj
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
  dotnet new classlib -o PrimeService --lang VB
  ```

   [`dotnet new classlib`](../tools/dotnet-new.md) 명령은 *PrimeService* 폴더에 새 클래스 라이브러리 프로젝트를 만듭니다. 새 클래스 라이브러리에는 테스트할 코드가 포함됩니다.
* *Class1.vb*의 이름을 *PrimeService.vb*로 바꿉니다.
* *PrimeService.vb*의 코드를 다음 코드로 바꿉니다.
  
  ```vb
  Imports System
  
  Namespace Prime.Services
      Public Class PrimeService
          Public Function IsPrime(candidate As Integer) As Boolean
              Throw New NotImplementedException("Not implemented.")
          End Function
      End Class
  End Namespace
  ```

* 위의 코드는
  * 구현되지 않았음을 나타내는 메시지와 함께 <xref:System.NotImplementedException>을 throw합니다.
  * 자습서의 뒷부분에서 업데이트됩니다.

<!-- preceding code shows an english bias. Message makes no sense outside english -->

* *unit-testing-using-dotnet-test* 디렉터리에서 다음 명령을 실행하여 클래스 라이브러리 프로젝트를 솔루션에 추가합니다.

  ```dotnetcli
  dotnet sln add ./PrimeService/PrimeService.vbproj
  ```

* 다음 명령을 실행하여 *PrimeService.Tests* 프로젝트를 만듭니다.

  ```dotnetcli
  dotnet new xunit -o PrimeService.Tests
  ```

* 이전 명령은
  * *PrimeService.Tests* 디렉터리에 *PrimeService.Tests* 프로젝트를 만듭니다. 테스트 프로젝트는 [xUnit](https://xunit.net/)을 테스트 라이브러리로 사용합니다.
  * 프로젝트 파일에 다음 `<PackageReference />` 요소를 추가하여 Test Runner를 구성합니다.
    * "Microsoft.NET.Test.Sdk"
    * "xunit"
    * "xunit.runner.visualstudio"

* 다음 명령을 실행하여 솔루션 파일에 테스트 프로젝트를 추가합니다.

  ```dotnetcli
  dotnet sln add ./PrimeService.Tests/PrimeService.Tests.vbproj
  ```

* `PrimeService` 클래스 라이브러리를 *PrimeService.Tests* 프로젝트에 대한 종속성으로 추가합니다.

  ```dotnetcli
  dotnet add ./PrimeService.Tests/PrimeService.Tests.vbproj reference ./PrimeService/PrimeService.vbproj  
  ```

<a name="create-test-cmd"></a>

### <a name="commands-to-create-the-solution"></a>솔루션을 만드는 명령

이 섹션에는 이전 섹션의 모든 명령이 요약되어 있습니다. 이전 섹션의 단계를 완료한 경우에는 이 섹션을 건너뜁니다.

다음 명령은 Windows 머신에서 테스트 솔루션을 만듭니다. macOS 및 Unix의 경우 `ren` 명령을 `ren` OS 버전으로 업데이트하여 파일 이름을 바꿉니다.

```dotnetcli
dotnet new sln -o unit-testing-using-dotnet-test
cd unit-testing-using-dotnet-test
dotnet new classlib -o PrimeService
ren .\PrimeService\Class1.vb PrimeService.vb
dotnet sln add ./PrimeService/PrimeService.vbproj
dotnet new xunit -o PrimeService.Tests
dotnet add ./PrimeService.Tests/PrimeService.Tests.vbproj reference ./PrimeService/PrimeService.vbproj
dotnet sln add ./PrimeService.Tests/PrimeService.Tests.vbproj
```

이전 섹션에 있는 "*PrimeService.vb*의 코드를 다음 코드로 바꾸기" 지침을 따릅니다.

## <a name="create-a-test"></a>테스트 만들기

TDD(테스트 기반 개발)에서 널리 사용되는 방식은 대상 코드를 구현하기 전에 테스트를 작성하는 것입니다. 이 자습서에서는 TDD 방식을 사용합니다. `IsPrime` 메서드는 호출할 수 있지만 구현되지 않습니다. `IsPrime`에 대한 테스트 호출이 실패합니다. TDD를 사용하면 실패하는 것으로 알려진 테스트가 작성됩니다. 테스트가 통과하도록 대상 코드가 업데이트됩니다. 이 방식을 계속 반복하여 실패한 테스트를 작성한 후 대상 코드를 업데이트하여 통과합니다.

*PrimeService.Tests* 프로젝트 업데이트:

* *PrimeService.Tests/UnitTest1.vb*를 삭제합니다.
* *PrimeService.Tests/PrimeService_IsPrimeShould.vb* 파일을 만듭니다.
* *PrimeService_IsPrimeShould.vb*의 코드를 다음 코드로 바꿉니다.

```vb
Imports Xunit

Namespace PrimeService.Tests
    Public Class PrimeService_IsPrimeShould
        Private ReadOnly _primeService As Prime.Services.PrimeService

        Public Sub New()
            _primeService = New Prime.Services.PrimeService()
        End Sub


        <Fact>
        Sub IsPrime_InputIs1_ReturnFalse()
            Dim result As Boolean = _primeService.IsPrime(1)

            Assert.False(result, "1 should not be prime")
        End Sub

    End Class
End Namespace
```

`[Fact]` 특성은 Test Runner에서 실행하는 테스트 메서드를 선언합니다. *Primeservice.tests* 폴더에서 `dotnet test`를 실행합니다. [dotnet test](../tools/dotnet-test.md) 명령은 두 프로젝트를 모두 빌드하고 테스트를 실행합니다. xUnit Test Runner에는 테스트를 실행할 프로그램 진입점이 포함되어 있습니다. `dotnet test`는 단위 테스트 프로젝트를 사용하여 Test Runner를 시작합니다.

`IsPrime`이 구현되지 않았기 때문에 테스트가 실패합니다. TDD 방식을 사용하여 이 테스트가 통과할 수 있는 코드만 작성합니다. 다음 코드를 사용하여 `IsPrime`을 업데이트합니다.

```vb
Public Function IsPrime(candidate As Integer) As Boolean
    If candidate = 1 Then
        Return False
    End If
    Throw New NotImplementedException("Not implemented.")
End Function
```

`dotnet test`를 실행합니다. 테스트가 통과됩니다.

### <a name="add-more-tests"></a>더 많은 테스트 추가

0 및 -1에 대한 소수 테스트를 추가합니다. 이전 테스트를 복사하고 다음 코드를 변경하여 0 및 -1을 사용할 수 있습니다.

```vb
Dim result As Boolean = _primeService.IsPrime(1)

Assert.False(result, "1 should not be prime")
```

매개 변수만 변경될 때 테스트 코드를 복사하면 코드 중복 및 테스트 블로트가 발생합니다. 다음 xUnit 특성은 유사한 테스트 모음을 작성하는 데 사용할 수 있습니다.

- `[Theory]`는 같은 코드를 실행하지만, 다른 입력 인수가 포함된 테스트 모음을 나타냅니다.
- `[InlineData]` 특성은 해당 입력에 대한 값을 지정합니다.

새 테스트를 만들지 않고 앞의 xUnit 특성을 적용하여 단일 이론을 만듭니다. 코드 바꾸기 대상:

```vb
<Fact>
Sub IsPrime_InputIs1_ReturnFalse()
    Dim result As Boolean = _primeService.IsPrime(1)

    Assert.False(result, "1 should not be prime")
End Sub
```

다음 코드로 바꾸기:

```vb
<Theory>
<InlineData(-1)>
<InlineData(0)>
<InlineData(1)>
Sub IsPrime_ValuesLessThan2_ReturnFalse(ByVal value As Integer)
    Dim result As Boolean = _primeService.IsPrime(value)

    Assert.False(result, $"{value} should not be prime")
End Sub
```

앞의 코드에서 `[Theory]` 및 `[InlineData]`를 사용하여 2보다 작은 몇 가지 값을 테스트할 수 있습니다. 2는 가장 작은 소수입니다.

`dotnet test`를 실행하면 두 가지 테스트가 실패합니다. 모든 테스트를 통과하도록 하려면 다음 코드를 사용하여 `IsPrime` 메서드를 업데이트합니다.

```vb
Public Function IsPrime(candidate As Integer) As Boolean
    If candidate < 2 Then
        Return False
    End If
    Throw New NotImplementedException("Not fully implemented.")
End Function
```

TDD 방식에 따라 실패하는 테스트를 더 추가한 후 대상 코드를 업데이트합니다. [테스트의 완료된 버전](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-vb-dotnet-test/PrimeService.Tests/PrimeService_IsPrimeShould.vb) 및 [라이브러리의 완전한 구현](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-vb-dotnet-test/PrimeService/PrimeService.vb)을 참조하세요.

완료된 `IsPrime` 메서드는 소수판별 테스트를 위한 효율적인 알고리즘이 아닙니다.

### <a name="additional-resources"></a>추가 자료

- [xUnit.net 공식 사이트](https://xunit.net/)
- [ASP.NET Core에서 컨트롤러 논리 테스트](/aspnet/core/mvc/controllers/testing)
- [`dotnet add reference`](../tools/dotnet-add-reference.md)
