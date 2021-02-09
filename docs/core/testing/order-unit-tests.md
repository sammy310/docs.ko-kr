---
title: 단위 테스트 순서 지정
description: .NET Core를 사용하여 단위 테스트의 순서를 지정하는 방법을 알아봅니다.
author: IEvangelist
ms.author: dapine
ms.date: 05/18/2020
zone_pivot_groups: unit-testing-framework-set-one
ms.openlocfilehash: a7b6b66e4cc865d4ec6b7cfc31ac79767935df2f
ms.sourcegitcommit: f2ab02d9a780819ca2e5310bbcf5cfe5b7993041
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/03/2021
ms.locfileid: "99506385"
---
# <a name="order-unit-tests"></a>단위 테스트 순서 지정

경우에 따라 단위 테스트를 특정 순서로 실행해야 할 수도 있습니다. 이상적으로는 단위 테스트가 실행되는 순서가 중요하지 _않아야_ 하며 단위 테스트 순서를 사용하지 않는 것이 [모범 사례](unit-testing-best-practices.md)입니다. 그럼에도 단위 테스트를 수행해야 할 수도 있습니다. 이 문서에서는 그러한 경우 테스트를 실행하는 순서를 지정하는 방법을 보여 줍니다.

소스 코드를 찾아보려면 [.NET Core 단위 테스트 순서 지정](/samples/dotnet/samples/order-unit-tests-cs) 샘플 리포지토리를 참조하세요.

> [!TIP]
> 이 문서에서 설명하는 순서 지정 기능 외에 [Visual Studio를 사용하여 사용자 지정 재생 목록 만들기](/visualstudio/test/run-unit-tests-with-test-explorer?view=vs-2019#create-custom-playlists)를 대안으로 고려할 수도 있습니다.

:::zone pivot="mstest"

## <a name="order-alphabetically"></a>사전순으로 순서 지정

MSTest를 사용하면 테스트 순서가 테스트 이름을 기준으로 자동으로 지정됩니다.

> [!NOTE]
> `2`가 `14`보다 작지만 `Test14`라는 테스트는 `Test2`보다 먼저 실행됩니다. 이는 테스트 이름 순서 지정이 테스트의 텍스트 이름을 사용하기 때문입니다.

:::code language="csharp" source="snippets/order-unit-tests/csharp/MSTest.Project/ByAlphabeticalOrder.cs":::

:::zone-end
:::zone pivot="xunit"

xUnit 테스트 프레임워크를 사용하면 테스트 실행 순서를 보다 세밀하게 제어할 수 있습니다. 클래스 또는 테스트 컬렉션에 대한 테스트 사례의 순서를 제어하려면 `ITestCaseOrderer` 및 `ITestCollectionOrderer` 인터페이스를 구현합니다.

## <a name="order-by-test-case-alphabetically"></a>사전순으로 테스트 사례 순서 지정

테스트 사례를 해당 메서드 이름에 따라 순서를 지정하려면 `ITestCaseOrderer`를 구현하고 순서 지정 메커니즘을 제공합니다.

:::code language="csharp" source="snippets/order-unit-tests/csharp/XUnit.TestProject/Orderers/AlphabeticalOrderer.cs":::

그런 다음 테스트 클래스에서 `TestCaseOrdererAttribute`를 사용하여 테스트 사례 순서를 설정합니다.

:::code language="csharp" source="snippets/order-unit-tests/csharp/XUnit.TestProject/ByAlphabeticalOrder.cs":::

## <a name="order-by-collection-alphabetically"></a>사전순으로 컬렉션 순서 지정

테스트 컬렉션을 해당 표시 이름에 따라 순서를 지정하려면 `ITestCollectionOrderer`을 구현하고 순서 지정 메커니즘을 제공합니다.

:::code language="csharp" source="snippets/order-unit-tests/csharp/XUnit.TestProject/Orderers/DisplayNameOrderer.cs":::

테스트 컬렉션은 잠재적으로 병렬로 실행되므로 `CollectionBehaviorAttribute`를 사용하여 컬렉션의 테스트 병렬 처리를 명시적으로 사용하지 않도록 설정해야 합니다. 그런 다음 `TestCollectionOrdererAttribute`에 대한 구현을 지정합니다.

:::code language="csharp" source="snippets/order-unit-tests/csharp/XUnit.TestProject/ByDisplayName.cs":::

## <a name="order-by-custom-attribute"></a>사용자 지정 특성별로 순서 지정

사용자 지정 특성을 사용하는 xUnit 테스트의 순서를 지정하려면 먼저 사용할 특성이 필요합니다. 다음과 같이 `TestPriorityAttribute`를 정의합니다.

:::code language="csharp" source="snippets/order-unit-tests/csharp/XUnit.TestProject/Attributes/TestPriorityAttribute.cs":::

다음으로 `ITestCaseOrderer` 인터페이스의 다음 `PriorityOrderer` 구현을 고려합니다.

:::code language="csharp" source="snippets/order-unit-tests/csharp/XUnit.TestProject/Orderers/PriorityOrderer.cs":::

그런 다음 테스트 클래스에서 `TestCaseOrdererAttribute`를 `PriorityOrderer`로 지정하여 테스트 사례 순서를 설정합니다.

:::code language="csharp" source="snippets/order-unit-tests/csharp/XUnit.TestProject/ByPriorityOrder.cs":::

:::zone-end
:::zone pivot="nunit"

## <a name="order-by-priority"></a>우선 순위로 순서 지정

명시적으로 테스트의 순서를 지정하기 위해 NUnit은 [`OrderAttribute`](https://github.com/nunit/docs/wiki/Order-Attribute)를 제공합니다. 이 특성이 지정된 테스트는 그렇지 않은 테스트보다 먼저 시작합니다. 순서 값은 단위 테스트를 실행하는 순서를 결정하는 데 사용됩니다.

:::code language="csharp" source="snippets/order-unit-tests/csharp/NUnit.TestProject/ByOrder.cs":::

:::zone-end

## <a name="next-steps"></a>다음 단계

> [!div class="nextstepaction"]
> [단위 테스트 코드 검사](unit-testing-code-coverage.md)
