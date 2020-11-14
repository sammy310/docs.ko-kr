---
title: .NET Standard 개체가 직렬화 가능한지 확인하는 방법
description: 런타임에 .NET Standard 형식을 직렬화할 수 있는지 여부를 확인하는 방법을 보여 줍니다.
ms.date: 10/20/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- serializing objects
- objects, serializing steps
ms.openlocfilehash: 9f7ab8a824b9687f68382a5edc342536289c5d09
ms.sourcegitcommit: 74d05613d6c57106f83f82ce8ee71176874ea3f0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2020
ms.locfileid: "93282324"
---
# <a name="how-to-determine-if-a-net-standard-object-is-serializable"></a>.NET Standard 개체가 직렬화 가능한지 확인하는 방법

.NET Standard는 해당 버전의 표준에 맞는 특정 .NET 구현에 반드시 있어야 하는 형식 및 멤버를 정의하는 사양입니다. 그러나 .NET Standard는 형식을 직렬화할 수 있는지 여부를 정의하지 않습니다. .NET Standard 라이브러리에 정의된 형식은 <xref:System.SerializableAttribute> 특성으로 표시되지 않습니다. 대신 .NET Framework 및 .NET Core와 같은 특정 .NET 구현을 사용하여 특정 형식이 직렬화 가능 여부를 확인할 수 있습니다.

.NET Standard를 대상으로 하는 라이브러리를 개발한 경우 .NET Standard를 지원하는 모든 .NET 구현에서 라이브러리를 사용할 수 있습니다. 즉, 특정 형식을 직렬화할 수 있는지 여부를 미리 알 수 없습니다. 런타임에 직렬화 가능 여부를 확인할 수 있습니다.

개체 형식을 나타내는 <xref:System.Type> 개체의 <xref:System.Type.IsSerializable> 속성 값을 검색하여 런타임에 개체를 직렬화할 수 있는지 여부를 확인할 수 있습니다. 다음 예제에서는 한 가지 구현을 제공합니다. 이 구현은 <xref:System.Object> 인스턴스를 직렬화할 수 있는지 여부를 나타내는 `IsSerializable(Object)` 확장 메서드를 정의합니다.

[!code-csharp[is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/csharp/program.cs#2)]
[!code-vb[is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/vb/library.vb#2)]

그러면 다음 예제와 같이 개체를 메서드에 전달하여 현재 .NET 구현에서 직렬화 및 역직렬화할 수 있는지 여부를 확인할 수 있습니다.

[!code-csharp[test-is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/csharp/program.cs#1)]
[!code-vb[test-is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/vb/program.vb#1)]

## <a name="see-also"></a>참조

- [이진 직렬화](binary-serialization.md)
- <xref:System.SerializableAttribute?displayProperty=nameWithType>
- <xref:System.Type.IsSerializable?displayProperty=nameWithType>
