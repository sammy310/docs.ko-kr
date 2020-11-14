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
# <a name="how-to-determine-if-a-net-standard-object-is-serializable"></a><span data-ttu-id="a28e1-103">.NET Standard 개체가 직렬화 가능한지 확인하는 방법</span><span class="sxs-lookup"><span data-stu-id="a28e1-103">How to determine if a .NET Standard object is serializable</span></span>

<span data-ttu-id="a28e1-104">.NET Standard는 해당 버전의 표준에 맞는 특정 .NET 구현에 반드시 있어야 하는 형식 및 멤버를 정의하는 사양입니다.</span><span class="sxs-lookup"><span data-stu-id="a28e1-104">.NET Standard is a specification that defines the types and members that must be present on specific .NET implementations that conform to that version of the standard.</span></span> <span data-ttu-id="a28e1-105">그러나 .NET Standard는 형식을 직렬화할 수 있는지 여부를 정의하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a28e1-105">However, .NET Standard does not define whether a type is serializable.</span></span> <span data-ttu-id="a28e1-106">.NET Standard 라이브러리에 정의된 형식은 <xref:System.SerializableAttribute> 특성으로 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a28e1-106">The types defined in the .NET Standard Library are not marked with the <xref:System.SerializableAttribute> attribute.</span></span> <span data-ttu-id="a28e1-107">대신 .NET Framework 및 .NET Core와 같은 특정 .NET 구현을 사용하여 특정 형식이 직렬화 가능 여부를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a28e1-107">Instead, specific .NET implementations, such as .NET Framework and .NET Core, are free to determine whether a particular type is serializable.</span></span>

<span data-ttu-id="a28e1-108">.NET Standard를 대상으로 하는 라이브러리를 개발한 경우 .NET Standard를 지원하는 모든 .NET 구현에서 라이브러리를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a28e1-108">If you've developed a library that targets .NET Standard, your library can be consumed by any .NET implementation that supports .NET Standard.</span></span> <span data-ttu-id="a28e1-109">즉, 특정 형식을 직렬화할 수 있는지 여부를 미리 알 수 없습니다. 런타임에 직렬화 가능 여부를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a28e1-109">This means that you cannot know in advance whether a particular type is serializable; you can only determine whether it is serializable at run time.</span></span>

<span data-ttu-id="a28e1-110">개체 형식을 나타내는 <xref:System.Type> 개체의 <xref:System.Type.IsSerializable> 속성 값을 검색하여 런타임에 개체를 직렬화할 수 있는지 여부를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a28e1-110">You can determine whether an object is serializable at run time by retrieving the value of the <xref:System.Type.IsSerializable> property of a <xref:System.Type> object that represents that object's type.</span></span> <span data-ttu-id="a28e1-111">다음 예제에서는 한 가지 구현을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a28e1-111">The following example provides one implementation.</span></span> <span data-ttu-id="a28e1-112">이 구현은 <xref:System.Object> 인스턴스를 직렬화할 수 있는지 여부를 나타내는 `IsSerializable(Object)` 확장 메서드를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="a28e1-112">It defines an `IsSerializable(Object)` extension method that indicates whether any <xref:System.Object> instance can be serialized.</span></span>

[!code-csharp[is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/csharp/program.cs#2)]
[!code-vb[is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/vb/library.vb#2)]

<span data-ttu-id="a28e1-113">그러면 다음 예제와 같이 개체를 메서드에 전달하여 현재 .NET 구현에서 직렬화 및 역직렬화할 수 있는지 여부를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a28e1-113">You can then pass any object to the method to determine whether it can be serialized and deserialized on the current .NET implementation, as the following example shows:</span></span>

[!code-csharp[test-is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/csharp/program.cs#1)]
[!code-vb[test-is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/vb/program.vb#1)]

## <a name="see-also"></a><span data-ttu-id="a28e1-114">참조</span><span class="sxs-lookup"><span data-stu-id="a28e1-114">See also</span></span>

- [<span data-ttu-id="a28e1-115">이진 직렬화</span><span class="sxs-lookup"><span data-stu-id="a28e1-115">Binary serialization</span></span>](binary-serialization.md)
- <xref:System.SerializableAttribute?displayProperty=nameWithType>
- <xref:System.Type.IsSerializable?displayProperty=nameWithType>
