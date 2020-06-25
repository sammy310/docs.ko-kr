---
title: -nullable(C# 컴파일러 옵션)
ms.date: 06/04/2020
f1_keywords:
- /nullable
helpviewer_keywords:
- nullable compiler option [C#]
- /nullable compiler option [C#]
- -nullable compiler option [C#]
ms.openlocfilehash: 7454bb316507c3aaea208094127552712421dff6
ms.sourcegitcommit: 45c8eed045779b70a47b23169897459d0323dc89
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/18/2020
ms.locfileid: "84990134"
---
# <a name="-nullable-c-compiler-options"></a>-nullable(C# 컴파일러 옵션)

**-nullable** 옵션을 사용하여 원하는 null 허용 컨텍스트를 지정할 수 있습니다.

## <a name="syntax"></a>구문

```console
-nullable[+ | -]
-nullable:{enable | disable | warnings | annotations}
```

## <a name="arguments"></a>인수

`+` &#124; `-`  
`+` 또는 **-nullable**을 지정하면 컴파일러에서 null 허용 컨텍스트를 사용하도록 설정합니다. `-`를 지정하면, 즉 실제로 **-nullable**을 지정하지 않으면 null 허용 컨텍스트를 사용하지 않도록 설정합니다.

`enable` &#124; `disable` &#124; `warnings` &#124; `annotations`  
null 허용 컨텍스트 옵션을 지정합니다. `+` 또는 `-`와 비슷하게, 사용하거나 사용하지 않도록 설정하지만 null 허용 컨텍스트 특정성을 더 세분화할 수 있습니다. `enable` 인수를 사용하면 실제로 **-nullable**을 지정하는 것과 동일하며 null 허용 컨텍스트를 사용하도록 설정합니다. `disable`을 지정하면 null 허용 컨텍스트를 사용하지 않도록 설정합니다. `warnings` 인수를 제공하면( **-nullable:warnings**) null 허용 경고 컨텍스트가 사용하도록 설정됩니다. `annotations` 인수를 지정하면 **-nullable:annotations**면 null 허용 주석 컨텍스트가 사용하도록 설정됩니다.

## <a name="remarks"></a>설명

흐름 분석은 실행 코드 내에서 변수의 Null 허용 여부를 유추하는 데 사용됩니다. 변수의 유추된 Null 허용 여부는 변수의 선언된 Null 허용 여부와 관계가 없습니다. 메서드 호출은 조건부로 생략된 경우에도 분석됩니다. 예를 들어 릴리스 모드의 <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>입니다.

다음 특성으로 주석이 지정된 메서드를 호출하면 흐름 분석에도 영향을 줍니다.

- 간단한 사전 조건: <xref:System.Diagnostics.CodeAnalysis.AllowNullAttribute> 및 <xref:System.Diagnostics.CodeAnalysis.DisallowNullAttribute>
- 간단한 사후 조건: <xref:System.Diagnostics.CodeAnalysis.MaybeNullAttribute> 및 <xref:System.Diagnostics.CodeAnalysis.NotNullAttribute>
- 조건부 사후 조건: <xref:System.Diagnostics.CodeAnalysis.MaybeNullWhenAttribute> 및 <xref:System.Diagnostics.CodeAnalysis.NotNullWhenAttribute>
- <xref:System.Diagnostics.CodeAnalysis.DoesNotReturnIfAttribute>(예: <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>에 대한 `DoesNotReturnIf(false)`) 및 <xref:System.Diagnostics.CodeAnalysis.DoesNotReturnAttribute>
- <xref:System.Diagnostics.CodeAnalysis.NotNullIfNotNullAttribute>
- 멤버 사후 조건: <xref:System.Diagnostics.CodeAnalysis.MemberNotNullAttribute.%23ctor(System.String)> 및 <xref:System.Diagnostics.CodeAnalysis.MemberNotNullAttribute.%23ctor(System.String[])>

### <a name="to-set-this-compiler-option-in-a-project"></a>프로젝트에서 이 컴파일러 옵션을 설정하는 방법

다음과 같이 *.csproj* 파일을 편집하여 `Project/PropertyGroup` 계층 구조 내에 `<Nullable>` 태그를 추가합니다.

```xml
<Project Sdk="...">

  <PropertyGroup>
    <Nullable>enable</Nullable>
  </PropertyGroup>

</Project>
```

## <a name="see-also"></a>참조

- [C# 컴파일러 옵션](./index.md)
- [nullable 참조 형식](../../nullable-references.md)
