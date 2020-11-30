---
title: .NET에서 StringBuilder 클래스 사용
description: .NET에서 StringBuilder 클래스를 사용하는 방법을 알아봅니다. 이 클래스를 사용하면 새 개체를 만들지 않고 문자열을 수정합니다.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Remove method
- strings [.NET], capacities
- StringBuilder object
- Replace method
- AppendFormat method
- Append method
- Insert method
- strings [.NET], StringBuilder object
ms.assetid: 5c14867c-9a99-45bc-ae7f-2686700d377a
ms.openlocfilehash: 54878f737faaedf4c9a176719f4ff83813a80201
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95734220"
---
# <a name="using-the-stringbuilder-class-in-net"></a><span data-ttu-id="20936-104">.NET에서 StringBuilder 클래스 사용</span><span class="sxs-lookup"><span data-stu-id="20936-104">Using the StringBuilder Class in .NET</span></span>

<span data-ttu-id="20936-105"><xref:System.String> 개체는 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="20936-105">The <xref:System.String> object is immutable.</span></span> <span data-ttu-id="20936-106"><xref:System.String?displayProperty=nameWithType> 클래스에서 메서드 중 하나를 사용할 때마다 메모리에 새 문자열 개체가 생성되므로, 새 개체에 대한 공간을 새로 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="20936-106">Every time you use one of the methods in the <xref:System.String?displayProperty=nameWithType> class, you create a new string object in memory, which requires a new allocation of space for that new object.</span></span> <span data-ttu-id="20936-107">문자열을 반복적으로 수정해야 하는 경우 새로운 <xref:System.String> 개체 생성과 관련된 오버헤드로 인해 비용이 증가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20936-107">In situations where you need to perform repeated modifications to a string, the overhead associated with creating a new <xref:System.String> object can be costly.</span></span> <span data-ttu-id="20936-108">새 개체를 만들지 않고 문자열을 수정하려는 경우 <xref:System.Text.StringBuilder?displayProperty=nameWithType> 클래스를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20936-108">The <xref:System.Text.StringBuilder?displayProperty=nameWithType> class can be used when you want to modify a string without creating a new object.</span></span> <span data-ttu-id="20936-109">예를 들어 <xref:System.Text.StringBuilder> 클래스를 사용하면 루프에서 많은 문자열을 연결할 때 성능이 향상될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20936-109">For example, using the <xref:System.Text.StringBuilder> class can boost performance when concatenating many strings together in a loop.</span></span>  
  
## <a name="importing-the-systemtext-namespace"></a><span data-ttu-id="20936-110">System.Text 네임스페이스 가져오기</span><span class="sxs-lookup"><span data-stu-id="20936-110">Importing the System.Text Namespace</span></span>  

 <span data-ttu-id="20936-111"><xref:System.Text.StringBuilder> 클래스는 <xref:System.Text> 네임스페이스에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20936-111">The <xref:System.Text.StringBuilder> class is found in the <xref:System.Text> namespace.</span></span>  <span data-ttu-id="20936-112">코드에서 정규화된 형식 이름을 제공할 필요가 없도록 하려면 <xref:System.Text> 네임스페이스를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20936-112">To avoid having to provide a fully qualified type name in your code,  you can import the <xref:System.Text> namespace:</span></span>  
  
 [!code-cpp[Conceptual.StringBuilder#11](../../../samples/snippets/cpp/VS_Snippets_CLR/Conceptual.StringBuilder/cpp/example.cpp#11)]
 [!code-csharp[Conceptual.StringBuilder#11](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/Example.cs#11)]
 [!code-vb[Conceptual.StringBuilder#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/Example.vb#11)]  
  
## <a name="instantiating-a-stringbuilder-object"></a><span data-ttu-id="20936-113">StringBuilder 개체 인스턴스화</span><span class="sxs-lookup"><span data-stu-id="20936-113">Instantiating a StringBuilder Object</span></span>  

 <span data-ttu-id="20936-114">다음 예제와 같이 오버로드된 생성자 메서드 중 하나로 변수를 초기화하여 <xref:System.Text.StringBuilder> 클래스의 새 인스턴스를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20936-114">You can create a new instance of the <xref:System.Text.StringBuilder> class by initializing your variable with one of the overloaded constructor methods, as illustrated in the following example.</span></span>  
  
 [!code-cpp[Conceptual.StringBuilder#1](../../../samples/snippets/cpp/VS_Snippets_CLR/Conceptual.StringBuilder/cpp/example.cpp#1)]
 [!code-csharp[Conceptual.StringBuilder#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/Example.cs#1)]
 [!code-vb[Conceptual.StringBuilder#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/Example.vb#1)]  
  
## <a name="setting-the-capacity-and-length"></a><span data-ttu-id="20936-115">용량 및 길이 설정</span><span class="sxs-lookup"><span data-stu-id="20936-115">Setting the Capacity and Length</span></span>  

 <span data-ttu-id="20936-116"><xref:System.Text.StringBuilder>는 캡슐화되는 문자열에서 문자 수를 확장할 수 있는 동적 개체이지만, 보관할 수 있는 최대 문자 수 값을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20936-116">Although the <xref:System.Text.StringBuilder> is a dynamic object that allows you to expand the number of characters in the string that it encapsulates, you can specify a value for the maximum number of characters that it can hold.</span></span> <span data-ttu-id="20936-117">이 값을 개체의 용량이라고 하며, 현재 <xref:System.Text.StringBuilder>에 보관된 문자열의 길이와 혼동해서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="20936-117">This value is called the capacity of the object and should not be confused with the length of the string that the current <xref:System.Text.StringBuilder> holds.</span></span> <span data-ttu-id="20936-118">예를 들어 길이가 5인 “Hello” 문자열을 사용하여 <xref:System.Text.StringBuilder> 클래스의 새 인스턴스를 만들고 개체의 최대 용량을 25로 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20936-118">For example, you might create a new instance of the <xref:System.Text.StringBuilder> class with the string "Hello", which has a length of 5, and you might specify that the object has a maximum capacity of 25.</span></span> <span data-ttu-id="20936-119"><xref:System.Text.StringBuilder>를 수정할 경우 용량에 도달할 때까지 자체 크기를 다시 할당할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="20936-119">When you modify the <xref:System.Text.StringBuilder>, it does not reallocate size for itself until the capacity is reached.</span></span> <span data-ttu-id="20936-120">이 경우 새 공간이 자동으로 할당되고 용량이 두 배로 증가합니다.</span><span class="sxs-lookup"><span data-stu-id="20936-120">When this occurs, the new space is allocated automatically and the capacity is doubled.</span></span> <span data-ttu-id="20936-121">오버로드된 생성자 중 하나를 사용하여 <xref:System.Text.StringBuilder> 클래스의 용량을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20936-121">You can specify the capacity of the <xref:System.Text.StringBuilder> class using one of the overloaded constructors.</span></span> <span data-ttu-id="20936-122">다음 예에서는 `myStringBuilder` 개체를 최대 25개 공간으로 확장할 수 있도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="20936-122">The following example specifies that the `myStringBuilder` object can be expanded to a maximum of 25 spaces.</span></span>  
  
 [!code-cpp[Conceptual.StringBuilder#2](../../../samples/snippets/cpp/VS_Snippets_CLR/Conceptual.StringBuilder/cpp/example.cpp#2)]
 [!code-csharp[Conceptual.StringBuilder#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/Example.cs#2)]
 [!code-vb[Conceptual.StringBuilder#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/Example.vb#2)]  
  
 <span data-ttu-id="20936-123">또한 읽기/쓰기 <xref:System.Text.StringBuilder.Capacity%2A> 속성을 사용하여 개체의 최대 길이를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20936-123">Additionally, you can use the read/write <xref:System.Text.StringBuilder.Capacity%2A> property to set the maximum length of your object.</span></span> <span data-ttu-id="20936-124">다음 예에서는 **Capacity** 속성을 사용하여 최대 개체 길이를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="20936-124">The following example uses the **Capacity** property to define the maximum object length.</span></span>  
  
 [!code-cpp[Conceptual.StringBuilder#3](../../../samples/snippets/cpp/VS_Snippets_CLR/Conceptual.StringBuilder/cpp/example.cpp#3)]
 [!code-csharp[Conceptual.StringBuilder#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/Example.cs#3)]
 [!code-vb[Conceptual.StringBuilder#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/Example.vb#3)]  
  
 <span data-ttu-id="20936-125"><xref:System.Text.StringBuilder.EnsureCapacity%2A> 메서드를 사용하여 현재 **StringBuilder** 의 용량을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20936-125">The <xref:System.Text.StringBuilder.EnsureCapacity%2A> method can be used to check the capacity of the current **StringBuilder**.</span></span> <span data-ttu-id="20936-126">용량이 전달된 값보다 크면 변경되지 않고, 용량이 전달된 값보다 작으면 현재 용량이 전달된 값과 일치하도록 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="20936-126">If the capacity is greater than the passed value, no change is made; however, if the capacity is smaller than the passed value, the current capacity is changed to match the passed value.</span></span>  
  
 <span data-ttu-id="20936-127"><xref:System.Text.StringBuilder.Length%2A> 속성을 보거나 설정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20936-127">The <xref:System.Text.StringBuilder.Length%2A> property can also be viewed or set.</span></span> <span data-ttu-id="20936-128">**Length** 속성을 **Capacity** 속성보다 큰 값으로 설정하면 **Capacity** 속성이 **Length** 속성과 동일한 값으로 자동으로 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="20936-128">If you set the **Length** property to a value that is greater than the **Capacity** property, the **Capacity** property is automatically changed to the same value as the **Length** property.</span></span> <span data-ttu-id="20936-129">**Length** 속성을 현재 **StringBuilder** 내의 문자열 길이보다 작은 값으로 설정하면 문자열이 단축됩니다.</span><span class="sxs-lookup"><span data-stu-id="20936-129">Setting the **Length** property to a value that is less than the length of the string within the current **StringBuilder** shortens the string.</span></span>  
  
## <a name="modifying-the-stringbuilder-string"></a><span data-ttu-id="20936-130">StringBuilder 문자열 수정</span><span class="sxs-lookup"><span data-stu-id="20936-130">Modifying the StringBuilder String</span></span>  

 <span data-ttu-id="20936-131">다음 표에서는 **StringBuilder** 의 내용을 수정하는 데 사용할 수 있는 메서드를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="20936-131">The following table lists the methods you can use to modify the contents of a **StringBuilder**.</span></span>  
  
|<span data-ttu-id="20936-132">메서드 이름</span><span class="sxs-lookup"><span data-stu-id="20936-132">Method name</span></span>|<span data-ttu-id="20936-133">기능</span><span class="sxs-lookup"><span data-stu-id="20936-133">Use</span></span>|  
|-----------------|---------|  
|<xref:System.Text.StringBuilder.Append%2A?displayProperty=nameWithType>|<span data-ttu-id="20936-134">현재 **StringBuilder** 의 끝에 정보를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="20936-134">Appends information to the end of the current **StringBuilder**.</span></span>|  
|<xref:System.Text.StringBuilder.AppendFormat%2A?displayProperty=nameWithType>|<span data-ttu-id="20936-135">문자열에 전달된 서식 지정자를 서식 있는 텍스트로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="20936-135">Replaces a format specifier passed in a string with formatted text.</span></span>|  
|<xref:System.Text.StringBuilder.Insert%2A?displayProperty=nameWithType>|<span data-ttu-id="20936-136">현재 **StringBuilder** 의 지정된 인덱스에 문자열 또는 개체를 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="20936-136">Inserts a string or object into the specified index of the current **StringBuilder**.</span></span>|  
|<xref:System.Text.StringBuilder.Remove%2A?displayProperty=nameWithType>|<span data-ttu-id="20936-137">현재 **StringBuilder** 에서 지정된 수의 문자를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="20936-137">Removes a specified number of characters from the current **StringBuilder**.</span></span>|  
|<xref:System.Text.StringBuilder.Replace%2A?displayProperty=nameWithType>|<span data-ttu-id="20936-138">현재 **StringBuilder** 에서 발견되는 지정된 문자 또는 문자열을 지정된 다른 문자 또는 문자열로 모두 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="20936-138">Replaces all occurrences of a specified character or string in the current **StringBuilder** with another specified character or string.</span></span>|  
  
### <a name="append"></a><span data-ttu-id="20936-139">추가</span><span class="sxs-lookup"><span data-stu-id="20936-139">Append</span></span>  

 <span data-ttu-id="20936-140">**Append** 메서드를 사용하여 현재 **StringBuilder** 에 표시되는 문자열의 끝에 개체의 문자열 표현이나 텍스트를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20936-140">The **Append** method can be used to add text or a string representation of an object to the end of a string represented by the current **StringBuilder**.</span></span> <span data-ttu-id="20936-141">다음 예에서는 **StringBuilder** 를 "Hello World"로 초기화한 다음 개체의 끝에 일부 텍스트를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="20936-141">The following example initializes a **StringBuilder** to "Hello World" and then appends some text to the end of the object.</span></span> <span data-ttu-id="20936-142">필요한 경우 공간이 자동으로 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="20936-142">Space is allocated automatically as needed.</span></span>  
  
 [!code-cpp[Conceptual.StringBuilder#4](../../../samples/snippets/cpp/VS_Snippets_CLR/Conceptual.StringBuilder/cpp/example.cpp#4)]
 [!code-csharp[Conceptual.StringBuilder#4](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/Example.cs#4)]
 [!code-vb[Conceptual.StringBuilder#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/Example.vb#4)]  
  
### <a name="appendformat"></a><span data-ttu-id="20936-143">AppendFormat</span><span class="sxs-lookup"><span data-stu-id="20936-143">AppendFormat</span></span>  

 <span data-ttu-id="20936-144"><xref:System.Text.StringBuilder.AppendFormat%2A?displayProperty=nameWithType> 메서드는 <xref:System.Text.StringBuilder> 개체의 끝에 텍스트를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="20936-144">The <xref:System.Text.StringBuilder.AppendFormat%2A?displayProperty=nameWithType> method adds text to the end of the <xref:System.Text.StringBuilder> object.</span></span> <span data-ttu-id="20936-145">또한 서식 지정할 개체의 <xref:System.IFormattable> 구현을 호출하여 복합 서식 지정 기능을 지원합니다. 자세한 내용은 [복합 서식 지정](composite-formatting.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="20936-145">It supports the composite formatting feature (for more information, see [Composite Formatting](composite-formatting.md)) by calling the <xref:System.IFormattable> implementation of the object or objects to be formatted.</span></span> <span data-ttu-id="20936-146">따라서 숫자, 날짜 및 시간, 열거형 값에 대한 표준 서식 문자열, 숫자, 날짜 및 시간 값에 대한 사용자 지정 서식 문자열, 사용자 지정 형식에 대해 정의된 서식 문자열을 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="20936-146">Therefore, it accepts the standard format strings for numeric, date and time, and enumeration values, the custom format strings for numeric and date and time values, and the format strings defined for custom types.</span></span> <span data-ttu-id="20936-147">서식 지정에 대한 자세한 내용은 [서식 지정 형식](formatting-types.md)을 참조하세요. 이 메서드를 사용하여 변수의 서식을 사용자 지정하고 해당 값을 <xref:System.Text.StringBuilder>에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20936-147">(For information about formatting, see [Formatting Types](formatting-types.md).) You can use this method to customize the format of variables and append those values to a <xref:System.Text.StringBuilder>.</span></span> <span data-ttu-id="20936-148">다음 예에서는 <xref:System.Text.StringBuilder.AppendFormat%2A> 메서드를 사용하여 통화 값으로 서식 지정된 정수 값을 <xref:System.Text.StringBuilder> 개체의 끝에 배치합니다.</span><span class="sxs-lookup"><span data-stu-id="20936-148">The following example uses the <xref:System.Text.StringBuilder.AppendFormat%2A> method to place an integer value formatted as a currency value at the end of a <xref:System.Text.StringBuilder> object.</span></span>  
  
 [!code-cpp[Conceptual.StringBuilder#5](../../../samples/snippets/cpp/VS_Snippets_CLR/Conceptual.StringBuilder/cpp/example.cpp#5)]
 [!code-csharp[Conceptual.StringBuilder#5](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/Example.cs#5)]
 [!code-vb[Conceptual.StringBuilder#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/Example.vb#5)]  
  
### <a name="insert"></a><span data-ttu-id="20936-149">Insert</span><span class="sxs-lookup"><span data-stu-id="20936-149">Insert</span></span>  

 <span data-ttu-id="20936-150"><xref:System.Text.StringBuilder.Insert%2A> 메서드는 현재 <xref:System.Text.StringBuilder> 개체의 지정된 위치에 문자열 또는 개체를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="20936-150">The <xref:System.Text.StringBuilder.Insert%2A> method adds a string or object to a specified position in the current <xref:System.Text.StringBuilder> object.</span></span> <span data-ttu-id="20936-151">다음 예에서는 이 메서드를 사용하여 <xref:System.Text.StringBuilder> 개체의 여섯 번째 위치에 단어를 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="20936-151">The following example uses this method to insert a word into the sixth position of a <xref:System.Text.StringBuilder> object.</span></span>  
  
 [!code-cpp[Conceptual.StringBuilder#6](../../../samples/snippets/cpp/VS_Snippets_CLR/Conceptual.StringBuilder/cpp/example.cpp#6)]
 [!code-csharp[Conceptual.StringBuilder#6](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/Example.cs#6)]
 [!code-vb[Conceptual.StringBuilder#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/Example.vb#6)]  
  
### <a name="remove"></a><span data-ttu-id="20936-152">제거</span><span class="sxs-lookup"><span data-stu-id="20936-152">Remove</span></span>  

 <span data-ttu-id="20936-153">**Remove** 메서드를 사용하여 지정된 0부터 시작하는 인덱스를 기준으로 현재 <xref:System.Text.StringBuilder> 개체에서 지정된 수의 문자를 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20936-153">You can use the **Remove** method to remove a specified number of characters from the current <xref:System.Text.StringBuilder> object, beginning at a specified zero-based index.</span></span> <span data-ttu-id="20936-154">다음 예에서는 **Remove** 메서드를 사용하여 <xref:System.Text.StringBuilder> 개체를 단축합니다.</span><span class="sxs-lookup"><span data-stu-id="20936-154">The following example uses the **Remove** method to shorten a <xref:System.Text.StringBuilder> object.</span></span>  
  
 [!code-cpp[Conceptual.StringBuilder#7](../../../samples/snippets/cpp/VS_Snippets_CLR/Conceptual.StringBuilder/cpp/example.cpp#7)]
 [!code-csharp[Conceptual.StringBuilder#7](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/Example.cs#7)]
 [!code-vb[Conceptual.StringBuilder#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/Example.vb#7)]  
  
### <a name="replace"></a><span data-ttu-id="20936-155">Replace</span><span class="sxs-lookup"><span data-stu-id="20936-155">Replace</span></span>  

 <span data-ttu-id="20936-156">**Replace** 메서드는 <xref:System.Text.StringBuilder> 개체 내의 문자를 다른 지정된 문자로 바꾸는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20936-156">The **Replace** method can be used to replace characters within the <xref:System.Text.StringBuilder> object with another specified character.</span></span> <span data-ttu-id="20936-157">다음 예에서는 **Replace** 메서드를 사용하여 <xref:System.Text.StringBuilder> 개체에서 느낌표 문자(!)의 모든 인스턴스를 검색한 다음, 물음표 문자(?)로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="20936-157">The following example uses the **Replace** method to search a <xref:System.Text.StringBuilder> object for all instances of the exclamation point character (!) and replace them with the question mark character (?).</span></span>  
  
 [!code-cpp[Conceptual.StringBuilder#8](../../../samples/snippets/cpp/VS_Snippets_CLR/Conceptual.StringBuilder/cpp/example.cpp#8)]
 [!code-csharp[Conceptual.StringBuilder#8](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/Example.cs#8)]
 [!code-vb[Conceptual.StringBuilder#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/Example.vb#8)]  
  
## <a name="converting-a-stringbuilder-object-to-a-string"></a><span data-ttu-id="20936-158">StringBuilder 개체를 문자열로 변환</span><span class="sxs-lookup"><span data-stu-id="20936-158">Converting a StringBuilder Object to a String</span></span>  

 <span data-ttu-id="20936-159"><xref:System.Text.StringBuilder> 개체에 표시되는 문자열을 <xref:System.String> 매개 변수를 가진 메서드에 전달하거나 사용자 인터페이스에 표시하려면 <xref:System.Text.StringBuilder> 개체를 <xref:System.String> 개체로 변환해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="20936-159">You must convert the <xref:System.Text.StringBuilder> object to a <xref:System.String> object before you can pass the string represented by the <xref:System.Text.StringBuilder> object to a method that has a <xref:System.String> parameter or display it in the user interface.</span></span> <span data-ttu-id="20936-160"><xref:System.Text.StringBuilder.ToString%2A?displayProperty=nameWithType> 메서드를 호출하여 이 변환을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="20936-160">You do this conversion by calling the <xref:System.Text.StringBuilder.ToString%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="20936-161">다음 예에서는 다양한 <xref:System.Text.StringBuilder> 메서드를 호출한 다음, <xref:System.Text.StringBuilder.ToString?displayProperty=nameWithType> 메서드를 호출하여 문자열을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="20936-161">The following example calls a number of <xref:System.Text.StringBuilder> methods and then calls the <xref:System.Text.StringBuilder.ToString?displayProperty=nameWithType> method to display the string.</span></span>  
  
 [!code-csharp[Conceptual.StringBuilder#10](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/tostringexample1.cs#10)]
 [!code-vb[Conceptual.StringBuilder#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/tostringexample1.vb#10)]  
  
## <a name="see-also"></a><span data-ttu-id="20936-162">참조</span><span class="sxs-lookup"><span data-stu-id="20936-162">See also</span></span>

- <xref:System.Text.StringBuilder?displayProperty=nameWithType>
- [<span data-ttu-id="20936-163">기본적인 문자열 작업</span><span class="sxs-lookup"><span data-stu-id="20936-163">Basic String Operations</span></span>](basic-string-operations.md)
- [<span data-ttu-id="20936-164">형식 서식 지정</span><span class="sxs-lookup"><span data-stu-id="20936-164">Formatting Types</span></span>](formatting-types.md)
