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
ms.openlocfilehash: b6791ae0666aeb0ac02d8a38ca419d7de2b263cf
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "84289605"
---
# <a name="how-to-determine-if-a-net-standard-object-is-serializable"></a><span data-ttu-id="1a611-103">.NET Standard 개체가 직렬화 가능한지 확인하는 방법</span><span class="sxs-lookup"><span data-stu-id="1a611-103">How to determine if a .NET Standard object is serializable</span></span>

<span data-ttu-id="1a611-104">.NET Standard는 해당 버전의 표준에 맞는 특정 .NET 구현에 반드시 있어야 하는 형식 및 멤버를 정의하는 사양입니다.</span><span class="sxs-lookup"><span data-stu-id="1a611-104">The .NET Standard is a specification that defines the types and members that must be present on specific .NET implementations that conform to that version of the standard.</span></span> <span data-ttu-id="1a611-105">그러나 .NET Standard는 형식을 직렬화할 수 있는지 여부를 정의하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1a611-105">However, the .NET Standard does not define whether a type is serializable.</span></span> <span data-ttu-id="1a611-106">.NET Standard 라이브러리에 정의된 형식은 <xref:System.SerializableAttribute> 특성으로 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1a611-106">The types defined in the .NET Standard Library are not marked with the <xref:System.SerializableAttribute> attribute.</span></span> <span data-ttu-id="1a611-107">대신 .NET Framework 및 .NET Core와 같은 특정 .NET 구현을 사용하여 특정 형식이 직렬화 가능한지 여부를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1a611-107">Instead, specific .NET implementations, such as the .NET Framework and .NET Core, are free to determine whether a particular type is serializable.</span></span>

<span data-ttu-id="1a611-108">.NET Standard를 대상으로 하는 라이브러리를 개발한 경우 .NET Standard를 지원하는 모든 .NET 구현에서 라이브러리를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1a611-108">If you've developed a library that targets the .NET Standard, your library can be consumed by any .NET implementation that supports the .NET Standard.</span></span> <span data-ttu-id="1a611-109">즉, 특정 형식을 직렬화할 수 있는지 여부를 미리 알 수 없습니다. 런타임에 직렬화 가능 여부를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1a611-109">This means that you cannot know in advance whether a particular type is serializable; you can only determine whether it is serializable at run time.</span></span>

<span data-ttu-id="1a611-110">개체 형식을 나타내는 <xref:System.Type> 개체의 <xref:System.Type.IsSerializable> 속성 값을 검색하여 런타임에 개체를 직렬화할 수 있는지 여부를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1a611-110">You can determine whether an object is serializable at run time by retrieving the value of the <xref:System.Type.IsSerializable> property of a <xref:System.Type> object that represents that object's type.</span></span> <span data-ttu-id="1a611-111">다음 예제에서는 한 가지 구현을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="1a611-111">The following example provides one implementation.</span></span> <span data-ttu-id="1a611-112">이 구현은 <xref:System.Object> 인스턴스를 직렬화할 수 있는지 여부를 나타내는 `IsSerializable(Object)` 확장 메서드를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="1a611-112">It defines an `IsSerializable(Object)` extension method that indicates whether any <xref:System.Object> instance can be serialized.</span></span>

[!code-csharp[is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/csharp/program.cs#2)]
[!code-vb[is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/vb/library.vb#2)]

<span data-ttu-id="1a611-113">그러면 다음 예제와 같이 개체를 메서드에 전달하여 현재 .NET 구현에서 직렬화 및 역직렬화할 수 있는지 여부를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1a611-113">You can then pass any object to the method to determine whether it can be serialized and deserialized on the current .NET implementation, as the following example shows:</span></span>

[!code-csharp[test-is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/csharp/program.cs#1)]
[!code-vb[test-is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/vb/program.vb#1)]

## <a name="see-also"></a><span data-ttu-id="1a611-114">참조</span><span class="sxs-lookup"><span data-stu-id="1a611-114">See also</span></span>

- [<span data-ttu-id="1a611-115">이진 직렬화</span><span class="sxs-lookup"><span data-stu-id="1a611-115">Binary serialization</span></span>](binary-serialization.md)
- <xref:System.SerializableAttribute?displayProperty=nameWithType>
- <xref:System.Type.IsSerializable?displayProperty=nameWithType>
