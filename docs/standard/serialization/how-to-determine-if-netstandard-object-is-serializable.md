---
title: .NET Standard 개체를 직렬화 가능 인지 확인 하는 방법
description: .NET 표준 형식이 런타임에 serialize 할 수 있는지 여부를 확인 하는 방법을 보여 줍니다.
ms.date: 10/20/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- serializing objects
- objects, serializing steps
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 196e99ab1f1a0baae53c6a1dc295b135e36fbfe0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62018764"
---
# <a name="how-to-determine-if-a-net-standard-object-is-serializable"></a><span data-ttu-id="551e0-103">.NET Standard 개체를 직렬화 가능 인지 확인 하는 방법</span><span class="sxs-lookup"><span data-stu-id="551e0-103">How to determine if a .NET Standard object is serializable</span></span>

<span data-ttu-id="551e0-104">.NET Standard는 형식 및 해당 버전의 표준 준수 하는 특정.NET 구현에 있어야 하는 멤버를 정의 하는 사양입니다.</span><span class="sxs-lookup"><span data-stu-id="551e0-104">The .NET Standard is a specification that defines the types and members that must be present on specific .NET implementations that conform to that version of the standard.</span></span> <span data-ttu-id="551e0-105">그러나.NET Standard 정의 하지 않습니다는 형식이 직렬화 가능 인지 합니다.</span><span class="sxs-lookup"><span data-stu-id="551e0-105">However, the .NET Standard does not define whether a type is serializable.</span></span> <span data-ttu-id="551e0-106">.NET 표준 라이브러리에서 정의 된 형식으로 표시 되어 있지는 <xref:System.SerializableAttribute> 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="551e0-106">The types defined in the .NET Standard Library are not marked with the <xref:System.SerializableAttribute> attribute.</span></span> <span data-ttu-id="551e0-107">대신.NET Framework 및.NET Core와 같은 특정.NET 구현에는 특정 형식의 직렬화 가능 인지 여부를 확인 무료입니다.</span><span class="sxs-lookup"><span data-stu-id="551e0-107">Instead, specific .NET implementations, such as the .NET Framework and .NET Core, are free to determine whether a particular type is serializable.</span></span> 

<span data-ttu-id="551e0-108">개발한 경우 라이브러리를 대상으로 하는.NET Standard,.NET Standard를 지 원하는 모든.NET 구현에서 라이브러리를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="551e0-108">If you've developed a library that targets the .NET Standard, your library can be consumed by any .NET implementation that supports the .NET Standard.</span></span> <span data-ttu-id="551e0-109">즉,는 알 수 없습니다 사전에 특정 형식 인지 직렬화 할 수 있습니다. 만 런타임에 직렬화 될 지 여부를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="551e0-109">This means that you cannot know in advance whether a particular type is serializable; you can only determine whether it is serializable at run time.</span></span>

<span data-ttu-id="551e0-110">개체의 값을 검색 하 여 런타임 시 직렬화 가능 인지 여부를 확인할 수 있습니다 합니다 <xref:System.Type.IsSerializable> 의 속성을 <xref:System.Type> 해당 개체의 형식을 나타내는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="551e0-110">You can determine whether an object is serializable at runtime by retrieving the value of the <xref:System.Type.IsSerializable> property of a <xref:System.Type> object that represents that object's type.</span></span> <span data-ttu-id="551e0-111">다음 예제에는 하나의 구현을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="551e0-111">The following example provides one implementation.</span></span> <span data-ttu-id="551e0-112">정의 `IsSerializable(Object)` 확장 메서드를 나타내는 있는지 여부를 <xref:System.Object> 인스턴스를 serialize 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="551e0-112">It defines an `IsSerializable(Object)` extension method that indicates whether any <xref:System.Object> instance can be serialized.</span></span>

[!code-csharp[is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/csharp/program.cs#2)]
[!code-vb[is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/vb/library.vb#2)]

<span data-ttu-id="551e0-113">그런 다음 여부를 고 수 serialize 및 deserialize 될 현재.NET 구현에서 다음 예와 같이 결정할 메서드에 개체를 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="551e0-113">You can then pass any object to the method to determine whether it can be serialized and deserialized on the current .NET implementation, as the following example shows:</span></span>

[!code-csharp[test-is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/csharp/program.cs#1)]
[!code-vb[test-is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/vb/program.vb#1)]

## <a name="see-also"></a><span data-ttu-id="551e0-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="551e0-114">See also</span></span>

- [<span data-ttu-id="551e0-115">이진 serialization</span><span class="sxs-lookup"><span data-stu-id="551e0-115">Binary serialization</span></span>](binary-serialization.md)
- <xref:System.SerializableAttribute?displayProperty=nameWithType>
- <xref:System.Type.IsSerializable?displayProperty=nameWithType>
