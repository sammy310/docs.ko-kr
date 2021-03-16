---
title: .NET에서 사용자 지정 구성 공급자 구현
description: .NET 애플리케이션에서 사용자 지정 구성 공급자를 구현하는 방법을 알아봅니다.
author: IEvangelist
ms.author: dapine
ms.date: 12/04/2020
ms.topic: how-to
ms.openlocfilehash: 22e46b7df8b02421633d6be251d990879baa8b2b
ms.sourcegitcommit: ecd9e9bb2225eb76f819722ea8b24988fe46f34c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/05/2020
ms.locfileid: "102402108"
---
# <a name="implement-a-custom-configuration-provider-in-net"></a>.NET에서 사용자 지정 구성 공급자 구현

JSON, XML 및 INI 파일과 같은 일반적인 구성 소스에 사용할 수 있는 여러 [구성 공급자](configuration-providers.md)가 있습니다. 사용 가능한 공급자 중 하나가 애플리케이션 요구 사항에 맞지 않는 경우 사용자 지정 구성 공급자를 구현해야 할 수 있습니다. 이 문서에서는 데이터베이스를 구성 소스로 사용하는 사용자 지정 구성 공급자를 구현하는 방법을 알아봅니다.

## <a name="custom-configuration-provider"></a>사용자 지정 구성 공급자

샘플 앱에서는 [EF(Entity Framework) Core](/ef/core)를 사용하여 데이터베이스에서 구성 키-값 쌍을 읽는 기본 구성 공급자를 만드는 방법을 보여 줍니다.

이 공급자의 특징은 다음과 같습니다.

- 데모용으로 EF 메모리 내 데이터베이스를 사용합니다. 연결 문자열이 필요한 데이터베이스를 사용하려면 보조 `ConfigurationBuilder`를 구현하여 다른 구성 공급자에서 연결 문자열을 제공하세요.
- 이 공급자는 시작 시 데이터베이스 테이블을 구성으로 읽어 들입니다. 이 공급자는 키별 기준으로 데이터베이스를 쿼리하지 않습니다.
- 변경 시 다시 로드가 구현되지 않으므로 앱 시작 후 데이터베이스를 업데이트해도 앱 구성에 영향을 주지 않습니다.

데이터베이스에 구성 값을 저장하는 `Settings` 레코드 형식 엔터티를 정의합니다. 예를 들어 *Models* 폴더에 *Settings.cs* 파일을 추가할 수 있습니다.

:::code language="csharp" source="snippets/configuration/custom-provider/Models/Settings.cs":::

레코드 형식에 관한 자세한 내용은 [C# 9의 레코드 형식](../../csharp/whats-new/csharp-9.md#record-types)를 참조하세요.

구성된 값을 저장 및 액세스하는 `EntityConfigurationContext`를 추가합니다.

*Providers/EntityConfigurationContext.cs*:

:::code language="csharp" source="snippets/configuration/custom-provider/Providers/EntityConfigurationContext.cs":::

<xref:Microsoft.Extensions.Configuration.IConfigurationSource>를 구현하는 클래스를 만듭니다.

*Providers/EntityConfigurationSource.cs*:

:::code language="csharp" source="snippets/configuration/custom-provider/Providers/EntityConfigurationSource.cs":::

<xref:Microsoft.Extensions.Configuration.ConfigurationProvider>에서 상속하여 사용자 지정 구성 공급자를 만듭니다. 구성 공급자는 비어 있는 데이터베이스를 초기화합니다. 구성 키는 대/소문자를 구분하지 않으므로 데이터베이스를 초기화하는 데 사용되는 사전은 대/소문자를 구분하지 않는 비교자([StringComparer.OrdinalIgnoreCase](xref:System.StringComparer.OrdinalIgnoreCase))를 사용하여 생성됩니다.

*Providers/EntityConfigurationProvider.cs*:

:::code language="csharp" source="snippets/configuration/custom-provider/Providers/EntityConfigurationProvider.cs":::

`AddEntityConfiguration` 확장 메서드를 사용하여 구성 소스를 <xref:Microsoft.Extensions.Configuration.IConfigurationBuilder> 인스턴스에 추가할 수 있습니다.

*Extensions/ConfigurationBuilderExtensions.cs*:

:::code language="csharp" source="snippets/configuration/custom-provider/Extensions/ConfigurationBuilderExtensions.cs":::

다음 코드는 *Program.cs* 에서 사용자 지정 `EntityConfigurationProvider`를 사용하는 방법을 보여 줍니다.

:::code language="csharp" source="snippets/configuration/custom-provider/Program.cs" highlight="27-28":::

## <a name="see-also"></a>참고 항목

- [.NET의 구성](configuration.md)
- [.NET의 구성 공급자](configuration-providers.md)
