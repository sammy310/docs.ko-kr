---
description: C#의 기본 제공 nint 및 nuint 형식에 대해 알아봅니다.
title: nint 및 nuint 형식 - C# 참조
ms.date: 03/15/2021
f1_keywords:
- nint_CSharpKeyword
- nuint_CSharpKeyword
helpviewer_keywords:
- nint data type [C#]
- nuint data type [C#]
ms.openlocfilehash: fc779731d7f67fd0239f095d1dd17217a56622f6
ms.sourcegitcommit: 20b4565974d185c7716656a6c63e3cfdbdf4bf41
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/20/2021
ms.locfileid: "104760825"
---
# <a name="nint-and-nuint-types-c-reference"></a>`nint` 및 `nuint` 형식(C# 참조)

C# 9.0부터 `nint` 및 `nuint` 키워드를 사용하여 기본 크기 정수를 정의할 수 있습니다. 이러한 정수는 32비트 프로세스에서 실행되는 경우 32비트 정수이고 64비트 프로세스에서 실행되는 경우 64비트 정수입니다. 이들은 상호 운용성 시나리오, 하위 수준 라이브러리에 사용할 수 있고 정수 연산이 광범위하게 사용되는 시나리오에서 성능을 최적화하는 데 사용할 수 있습니다.

기본 크기 정수 형식은 내부적으로 .NET 형식 <xref:System.IntPtr?displayProperty=nameWithType> 및 <xref:System.UIntPtr?displayProperty=nameWithType>로 표시됩니다. 다른 숫자 형식과 달리 키워드는 형식에 대한 별칭일 뿐입니다. 다음 문은 서로 같지 않습니다.

```csharp
nint a = 1;
System.IntPtr a = 1;
```

컴파일러는 `nint` 및 `nuint`에 대해 정수 형식에 적합한 작업 및 변환을 제공합니다.

## <a name="run-time-native-integer-size"></a>런타임 기본 정수 크기

런타임에 기본 크기 정수의 크기를 가져오려면 `sizeof()`를 사용할 수 있습니다. 그러나 안전하지 않은 컨텍스트에서는 코드를 컴파일해야 합니다. 예를 들면 다음과 같습니다.

:::code language="csharp" source="snippets/shared/NativeIntegerTypes.cs" id="SizeOf":::

정적 <xref:System.IntPtr.Size?displayProperty=nameWithType> 및 <xref:System.UIntPtr.Size?displayProperty=nameWithType> 속성에서 동등한 값을 가져올 수도 있습니다.

## <a name="minvalue-and-maxvalue"></a>MinValue 및 MaxValue

런타임에 기본 크기 정수의 최소값 및 최대값을 가져오려면 다음 예제와 같이 `MinValue` 및 `MaxValue`를 `nint` 및 `nuint` 키워드를 포함하는 정적 속성으로 사용합니다.

:::code language="csharp" source="snippets/shared/NativeIntegerTypes.cs" id="MinMax":::

## <a name="constants"></a>상수

다음 범위에서 상수 값을 사용할 수 있습니다.

* `nint`: <xref:System.Int32.MinValue?displayProperty=nameWithType>~<xref:System.Int32.MaxValue?displayProperty=nameWithType>.
* `nuint`: <xref:System.UInt32.MinValue?displayProperty=nameWithType>~<xref:System.UInt32.MaxValue?displayProperty=nameWithType>.

## <a name="conversions"></a>변환

컴파일러는 다른 숫자 형식으로 암시적 변환과 명시적 변환을 제공합니다. 자세한 내용은 [기본 제공 숫자 변환](numeric-conversions.md)을 참조하세요.

## <a name="literals"></a>리터럴

기본 크기 정수 리터럴에 대한 직접 구문은 없습니다. `L`이 `long`을 나타내는 것과 같이 리터럴이 기본 크기 정수임을 나타내는 접미사는 없습니다. 대신 다른 정수 값의 암시적 또는 명시적 캐스트를 사용할 수 있습니다. 예를 들면 다음과 같습니다.

```csharp
nint a = 42
nint a = (nint)42;
```

## <a name="unsupported-intptruintptr-members"></a>지원되지 않는 IntPtr/UIntPtr 멤버

<xref:System.IntPtr> 및 <xref:System.UIntPtr>의 다음 멤버는 `nint` 및 `nuint` 형식에 대해 지원되지 않습니다.

* 매개 변수 있는 생성자
* <xref:System.IntPtr.Add(System.IntPtr,System.Int32)>
* <xref:System.IntPtr.CompareTo%2A>
* <xref:System.IntPtr.Size> - 대신 [sizeOf()](#run-time-native-integer-size)를 사용합니다. `nint.Size`는 지원되지 않지만 `IntPtr.Size`를 사용하여 동등한 값을 가져올 수 있습니다.
* <xref:System.IntPtr.Subtract(System.IntPtr,System.Int32)>
* <xref:System.IntPtr.ToInt32%2A>
* <xref:System.IntPtr.ToInt64%2A>
* <xref:System.IntPtr.ToPointer%2A>
* <xref:System.IntPtr.Zero> - 대신 0을 사용합니다.

## <a name="c-language-specification"></a>C# 언어 사양

자세한 내용은 [C# 언어 사양](~/_csharplang/spec/introduction.md) 및 C# 9.0 기능 제안 노트의 [기본 크기 정수](~/_csharplang/proposals/csharp-9.0/native-integers.md) 섹션을 참조하세요.

## <a name="see-also"></a>참고 항목

- [C# 참조](../index.md)
- [값 형식](value-types.md)
- [정수 숫자 형식](integral-numeric-types.md)
- [기본 제공 숫자 변환](numeric-conversions.md)
