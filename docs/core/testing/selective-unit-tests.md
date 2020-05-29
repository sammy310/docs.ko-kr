---
title: 선택적 단위 테스트 실행
description: 필터 식을 사용하여 .NET Core의 dotnet 테스트 명령을 통해 선택적 단위 테스트를 실행하는 방법입니다.
author: smadala
ms.date: 05/18/2020
zone_pivot_groups: unit-testing-framework-set-one
ms.openlocfilehash: 6a6bbb0687742d1e3288d64fb88f6825dc678e28
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2020
ms.locfileid: "83702987"
---
# <a name="run-selective-unit-tests"></a>선택적 단위 테스트 실행

.NET Core에서 [`dotnet test`](../tools/dotnet-test.md) 명령과 함께 필터 식을 사용하여 선택적 테스트를 실행할 수 있습니다. 이 문서에서는 실행되는 테스트를 필터링하는 방법을 보여 줍니다. 다음 예제에서는 `dotnet test`를 사용합니다. `vstest.console.exe`를 사용하는 경우 `--filter`를 `--testcasefilter:`로 바꾸세요.

## <a name="character-escaping"></a>문자 이스케이프

`*nix`에서 느낌표(`!`)를 포함하는 필터를 사용하려면 이스케이프해야 합니다. `!`가 예약되어 있기 때문입니다. 예를 들어 다음 필터는 네임스페이스에 IntegrationTests가 포함되어 있으면 모든 테스트를 건너뜁니다.

```dotnetcli
dotnet test --filter FullyQualifiedName\!~IntegrationTests
```

> [!IMPORTANT]
> 이스케이프된 문자임을 나타내기 위해 느낌표 앞에 백슬래시가 나옵니다(`\!`).

제네릭 형식 매개 변수의 쉼표를 포함하는 `FullyQualifiedName` 값의 경우 `%2C`를 사용하여 쉼표를 이스케이프합니다. 예를 들어:

```dotnetcli
dotnet test --filter "FullyQualifiedName=MyNamespace.MyTestsClass<ParameterType1%2CParameterType2>.MyTestMethod"
```

:::zone pivot="mstest"

```csharp
using Microsoft.VisualStudio.TestTools.UnitTesting;

namespace MSTestNamespace
{
    [TestClass]
    public class UnitTest1
    {
        [TestMethod, Priority(1), TestCategory("CategoryA")]
        public void TestMethod1()
        {
        }

        [TestMethod, Priority(2)]
        public void TestMethod2()
        {
        }
    }
}
```

| 식 | 결과 |
|--|--|
| `dotnet test --filter Method` | <xref:System.Reflection.Module.FullyQualifiedName>에 `Method`가 포함된 테스트를 실행합니다. `vstest 15.1+`에서 사용 가능합니다. |
| `dotnet test --filter Name~TestMethod1` | 이름에 `TestMethod1`이 포함된 테스트를 실행합니다. |
| `dotnet test --filter ClassName=MSTestNamespace.UnitTest1` | `MSTestNamespace.UnitTest1` 클래스에 있는 테스트를 실행합니다.<br>**참고:** `ClassName` 값에는 네임스페이스가 있어야 하므로, `ClassName=UnitTest1`이 작동하지 않습니다. |
| `dotnet test --filter FullyQualifiedName!=MSTestNamespace.UnitTest1.TestMethod1` | `MSTestNamespace.UnitTest1.TestMethod1`을 제외한 모든 테스트를 실행합니다. |
| `dotnet test --filter TestCategory=CategoryA` | `[TestCategory("CategoryA")]`로 주석이 달린 테스트를 실행합니다. |
| `dotnet test --filter Priority=2` | `[Priority(2)]`로 주석이 달린 테스트를 실행합니다. |

조건부 연산자 `|` 및 `&`를 사용하는 예는 다음과 같습니다.

<xref:System.Reflection.Module.FullyQualifiedName>에 `UnitTest1`가 포함되거나 **또는** <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestCategoryAttribute>가 `"CategoryA"`인 테스트를 실행하는 경우.

```dotnetcli
dotnet test --filter "FullyQualifiedName~UnitTest1|TestCategory=CategoryA"
```

<xref:System.Reflection.Module.FullyQualifiedName>에 `UnitTest1`이 포함**되면서** <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestCategoryAttribute>가 `"CategoryA"`인 테스트를 실행하는 경우.

```dotnetcli
dotnet test --filter "FullyQualifiedName~UnitTest1&TestCategory=CategoryA"
```

<xref:System.Reflection.Module.FullyQualifiedName>에 `UnitTest1`이 포함**되면서** <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestCategoryAttribute>가 `"CategoryA"`이거나, **또는** <xref:Microsoft.VisualStudio.TestTools.UnitTesting.PriorityAttribute>의 우선 순위가 `1`인 테스트를 실행하는 경우.

```dotnetcli
dotnet test --filter "(FullyQualifiedName~UnitTest1&TestCategory=CategoryA)|Priority=1"
```

:::zone-end
:::zone pivot="xunit"

```csharp
using Xunit;

namespace XUnitNamespace
{
    public class TestClass1
    {
        [Fact, Trait("Priority", "1"), Trait("Category", "CategoryA")]
        public void Test1()
        {
        }

        [Fact, Trait("Priority", "2")]
        public void Test2()
        {
        }
    }
}
```

| 식 | 결과 |
|--|--|
| `dotnet test --filter DisplayName=XUnitNamespace.TestClass1.Test1` | `XUnitNamespace.TestClass1.Test1` 테스트를 하나만 실행합니다. |
| `dotnet test --filter FullyQualifiedName!=XUnitNamespace.TestClass1.Test1` | `XUnitNamespace.TestClass1.Test1`을 제외한 모든 테스트를 실행합니다. |
| `dotnet test --filter DisplayName~TestClass1` | 표시 이름에 `TestClass1`이 포함된 테스트를 실행합니다. |

코드 예제에서 `"Category"` 및 `"Priority"` 키로 정의된 특성은 필터링에 사용할 수 있습니다.

| 식 | 결과 |
|--|--|
| `dotnet test --filter XUnit` | <xref:System.Reflection.Module.FullyQualifiedName>에 `XUnit`가 포함된 테스트를 실행합니다.  `vstest 15.1+`에서 사용 가능합니다. |
| `dotnet test --filter Category=CategoryA` | `[Trait("Category", "CategoryA")]`가 있는 테스트를 실행합니다. |

조건부 연산자 `|` 및 `&`를 사용하는 예는 다음과 같습니다.

<xref:System.Reflection.Module.FullyQualifiedName>에 `TestClass1`이 포함되거나 **또는** `"Category"` 키의 값이 `"CategoryA"`인 `Trait`가 있는 테스트를 실행하는 경우.

```dotnetcli
dotnet test --filter "FullyQualifiedName~TestClass1|Category=CategoryA"
```

<xref:System.Reflection.Module.FullyQualifiedName>에 `TestClass1`이 포함**되면서** `"Category"` 키의 값이 `"CategoryA"`인 `Trait`가 있는 테스트를 실행하는 경우.

```dotnetcli
dotnet test --filter "FullyQualifiedName~TestClass1&Category=CategoryA"
```

<xref:System.Reflection.Module.FullyQualifiedName>에 `TestClass1`이 포함**되면서** `"Category"` 키의 값이 `"CategoryA"`인 `Trait`가 있거나, **또는** `"Priority"` 키의 값이 `1`인 `Trait`가 있는 테스트를 실행하는 경우.

```dotnetcli
dotnet test --filter "(FullyQualifiedName~TestClass1&Category=CategoryA)|Priority=1"
```

:::zone-end
:::zone pivot="nunit"

```csharp
using NUnit.Framework;

namespace NUnitNamespace
{
    public class UnitTest1
    {
        [Test, Property("Priority", 1), Category("CategoryA")]
        public void TestMethod1()
        {
        }

        [Test, Property("Priority", 2)]
        public void TestMethod2()
        {
        }
    }
}
```

| 식 | 결과 |
|--|--|
| `dotnet test --filter Method` | <xref:System.Reflection.Module.FullyQualifiedName>에 `Method`가 포함된 테스트를 실행합니다. `vstest 15.1+`에서 사용 가능합니다. |
| `dotnet test --filter Name~TestMethod1` | 이름에 `TestMethod1`이 포함된 테스트를 실행합니다. |
| `dotnet test --filter FullyQualifiedName~NUnitNamespace.UnitTest1` | `NUnitNamespace.UnitTest1` 클래스에 있는 테스트를 실행합니다. |
| `dotnet test --filter FullyQualifiedName!=NUnitNamespace.UnitTest1.TestMethod1` | `NUnitNamespace.UnitTest1.TestMethod1`을 제외한 모든 테스트를 실행합니다. |
| `dotnet test --filter TestCategory=CategoryA` | `[Category("CategoryA")]`로 주석이 달린 테스트를 실행합니다. |
| `dotnet test --filter Priority=2` | `[Priority(2)]`로 주석이 달린 테스트를 실행합니다. |

조건부 연산자 `|` 및 `&`를 사용하는 예는 다음과 같습니다.

<xref:System.Reflection.Module.FullyQualifiedName>에 `UnitTest1`이 포함되거나 **또는** `Category`가 `"CategoryA"`인 테스트를 실행하는 경우.

```dotnetcli
dotnet test --filter "FullyQualifiedName~UnitTest1|TestCategory=CategoryA"
```

<xref:System.Reflection.Module.FullyQualifiedName>에 `UnitTest1`이 포함**되면서** `Category`가 `"CategoryA"`인 테스트를 실행하는 경우.

```dotnetcli
dotnet test --filter "FullyQualifiedName~UnitTest1&TestCategory=CategoryA"
```

<xref:System.Reflection.Module.FullyQualifiedName>에 `UnitTest1`이 포함**되면서** `Category`가 `"CategoryA"`이거나, **또는** `"Priority"`의 값이 `1`인 `Property`가 있는 테스트를 실행하는 경우.

```dotnetcli
dotnet test --filter "(FullyQualifiedName~UnitTest1&TestCategory=CategoryA)|Priority=1"
```

자세한 내용은 [TestCase 필터](https://github.com/Microsoft/vstest-docs/blob/master/docs/filter.md)를 참조하세요.

:::zone-end

## <a name="see-also"></a>참조

- [dotnet test](../tools/dotnet-test.md)
- [dotnet test --filter](../tools/dotnet-test.md#filter-option-details)

## <a name="next-steps"></a>다음 단계

> [!div class="nextstepaction"]
> [단위 테스트 순서 지정](order-unit-tests.md)
