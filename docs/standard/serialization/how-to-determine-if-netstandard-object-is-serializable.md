---
title: .NET Standard 개체를 직렬화 할 수 있는지 확인 하는 방법
description: 런타임에 .NET Standard 형식을 serialize 할 수 있는지 여부를 확인 하는 방법을 보여 줍니다.
ms.date: 10/20/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- serializing objects
- objects, serializing steps
ms.openlocfilehash: 87bf863b158fe3b2c03c7a6d23462bc2aabf9966
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73106626"
---
# <a name="how-to-determine-if-a-net-standard-object-is-serializable"></a>.NET Standard 개체를 직렬화 할 수 있는지 확인 하는 방법

.NET Standard는 해당 버전의 표준에 맞는 특정 .NET 구현에 반드시 있어야 하는 형식 및 멤버를 정의 하는 사양입니다. 그러나 .NET Standard는 형식을 serialize 할 수 있는지 여부를 정의 하지 않습니다. .NET Standard 라이브러리에 정의 된 형식은 <xref:System.SerializableAttribute> 특성으로 표시 되지 않습니다. 대신 특정 형식이 serialize 가능한 지 여부를 확인 하기 위해 .NET Framework 및 .NET Core와 같은 특정 .NET 구현을 사용할 수 있습니다. 

.NET Standard를 대상으로 하는 라이브러리를 개발한 경우 .NET Standard를 지 원하는 모든 .NET 구현에서 라이브러리를 사용할 수 있습니다. 즉, 특정 형식을 serialize 할 수 있는지 여부를 미리 알 수 없습니다. 런타임에 serialize 할 수 있는지 여부를 결정할 수 있습니다.

개체의 형식을 나타내는 <xref:System.Type> 개체의 <xref:System.Type.IsSerializable> 속성 값을 검색 하 여 런타임에 개체를 serialize 할 수 있는지 여부를 확인할 수 있습니다. 다음 예제에서는 하나의 구현을 제공 합니다. <xref:System.Object> 인스턴스를 serialize 할 수 있는지 여부를 나타내는 `IsSerializable(Object)` 확장 메서드를 정의 합니다.

[!code-csharp[is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/csharp/program.cs#2)]
[!code-vb[is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/vb/library.vb#2)]

그런 다음, 다음 예제와 같이 개체를 메서드에 전달 하 여 현재 .NET 구현에서 serialize 및 deserialize 할 수 있는지 여부를 확인할 수 있습니다.

[!code-csharp[test-is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/csharp/program.cs#1)]
[!code-vb[test-is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/vb/program.vb#1)]

## <a name="see-also"></a>참조

- [이진 serialization](binary-serialization.md)
- <xref:System.SerializableAttribute?displayProperty=nameWithType>
- <xref:System.Type.IsSerializable?displayProperty=nameWithType>
