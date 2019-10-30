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
# <a name="how-to-determine-if-a-net-standard-object-is-serializable"></a><span data-ttu-id="ab4cc-103">.NET Standard 개체를 직렬화 할 수 있는지 확인 하는 방법</span><span class="sxs-lookup"><span data-stu-id="ab4cc-103">How to determine if a .NET Standard object is serializable</span></span>

<span data-ttu-id="ab4cc-104">.NET Standard는 해당 버전의 표준에 맞는 특정 .NET 구현에 반드시 있어야 하는 형식 및 멤버를 정의 하는 사양입니다.</span><span class="sxs-lookup"><span data-stu-id="ab4cc-104">The .NET Standard is a specification that defines the types and members that must be present on specific .NET implementations that conform to that version of the standard.</span></span> <span data-ttu-id="ab4cc-105">그러나 .NET Standard는 형식을 serialize 할 수 있는지 여부를 정의 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ab4cc-105">However, the .NET Standard does not define whether a type is serializable.</span></span> <span data-ttu-id="ab4cc-106">.NET Standard 라이브러리에 정의 된 형식은 <xref:System.SerializableAttribute> 특성으로 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ab4cc-106">The types defined in the .NET Standard Library are not marked with the <xref:System.SerializableAttribute> attribute.</span></span> <span data-ttu-id="ab4cc-107">대신 특정 형식이 serialize 가능한 지 여부를 확인 하기 위해 .NET Framework 및 .NET Core와 같은 특정 .NET 구현을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab4cc-107">Instead, specific .NET implementations, such as the .NET Framework and .NET Core, are free to determine whether a particular type is serializable.</span></span> 

<span data-ttu-id="ab4cc-108">.NET Standard를 대상으로 하는 라이브러리를 개발한 경우 .NET Standard를 지 원하는 모든 .NET 구현에서 라이브러리를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab4cc-108">If you've developed a library that targets the .NET Standard, your library can be consumed by any .NET implementation that supports the .NET Standard.</span></span> <span data-ttu-id="ab4cc-109">즉, 특정 형식을 serialize 할 수 있는지 여부를 미리 알 수 없습니다. 런타임에 serialize 할 수 있는지 여부를 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab4cc-109">This means that you cannot know in advance whether a particular type is serializable; you can only determine whether it is serializable at run time.</span></span>

<span data-ttu-id="ab4cc-110">개체의 형식을 나타내는 <xref:System.Type> 개체의 <xref:System.Type.IsSerializable> 속성 값을 검색 하 여 런타임에 개체를 serialize 할 수 있는지 여부를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab4cc-110">You can determine whether an object is serializable at runtime by retrieving the value of the <xref:System.Type.IsSerializable> property of a <xref:System.Type> object that represents that object's type.</span></span> <span data-ttu-id="ab4cc-111">다음 예제에서는 하나의 구현을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab4cc-111">The following example provides one implementation.</span></span> <span data-ttu-id="ab4cc-112"><xref:System.Object> 인스턴스를 serialize 할 수 있는지 여부를 나타내는 `IsSerializable(Object)` 확장 메서드를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab4cc-112">It defines an `IsSerializable(Object)` extension method that indicates whether any <xref:System.Object> instance can be serialized.</span></span>

[!code-csharp[is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/csharp/program.cs#2)]
[!code-vb[is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/vb/library.vb#2)]

<span data-ttu-id="ab4cc-113">그런 다음, 다음 예제와 같이 개체를 메서드에 전달 하 여 현재 .NET 구현에서 serialize 및 deserialize 할 수 있는지 여부를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab4cc-113">You can then pass any object to the method to determine whether it can be serialized and deserialized on the current .NET implementation, as the following example shows:</span></span>

[!code-csharp[test-is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/csharp/program.cs#1)]
[!code-vb[test-is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/vb/program.vb#1)]

## <a name="see-also"></a><span data-ttu-id="ab4cc-114">참조</span><span class="sxs-lookup"><span data-stu-id="ab4cc-114">See also</span></span>

- [<span data-ttu-id="ab4cc-115">이진 serialization</span><span class="sxs-lookup"><span data-stu-id="ab4cc-115">Binary serialization</span></span>](binary-serialization.md)
- <xref:System.SerializableAttribute?displayProperty=nameWithType>
- <xref:System.Type.IsSerializable?displayProperty=nameWithType>
