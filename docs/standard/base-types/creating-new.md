---
title: .NET에서 새 문자열 만들기
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- CopyTo method
- Join method
- Format method
- Concat method
- strings [.NET Framework], creating
- Insert method
ms.assetid: 06fdf123-2fac-4459-8904-eb48ab908a30
ms.openlocfilehash: a5dfe6429ac135202874f0524a252a7af900bd8d
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/02/2020
ms.locfileid: "84279014"
---
# <a name="creating-new-strings-in-net"></a><span data-ttu-id="7f007-102">.NET에서 새 문자열 만들기</span><span class="sxs-lookup"><span data-stu-id="7f007-102">Creating New Strings in .NET</span></span>
<span data-ttu-id="7f007-103">.NET Framework에서는 간단한 할당을 사용하여 문자열을 만들 수 있으며, 클래스 생성자를 오버로드하여 여러 다양한 매개 변수를 사용한 문자열 생성도 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="7f007-103">The .NET Framework allows strings to be created using simple assignment, and also overloads a class constructor to support string creation using a number of different parameters.</span></span> <span data-ttu-id="7f007-104">또한 .NET Framework에서는 여러 문자열, 문자열 배열 또는 개체를 결합하여 새 문자열 개체를 만드는 여러 메서드를 <xref:System.String?displayProperty=nameWithType> 클래스에서 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="7f007-104">The .NET Framework also provides several methods in the <xref:System.String?displayProperty=nameWithType> class that create new string objects by combining several strings, arrays of strings, or objects.</span></span>  
  
## <a name="creating-strings-using-assignment"></a><span data-ttu-id="7f007-105">할당을 사용하여 문자열 만들기</span><span class="sxs-lookup"><span data-stu-id="7f007-105">Creating Strings Using Assignment</span></span>  
 <span data-ttu-id="7f007-106">새 <xref:System.String> 개체를 만드는 가장 쉬운 방법은 간단히 <xref:System.String> 개체에 문자열 리터럴을 할당하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="7f007-106">The easiest way to create a new <xref:System.String> object is simply to assign a string literal to a <xref:System.String> object.</span></span>  
  
## <a name="creating-strings-using-a-class-constructor"></a><span data-ttu-id="7f007-107">클래스 생성자를 사용하여 문자열 만들기</span><span class="sxs-lookup"><span data-stu-id="7f007-107">Creating Strings Using a Class Constructor</span></span>  
 <span data-ttu-id="7f007-108"><xref:System.String> 클래스 생성자의 오버로드를 사용하여 문자 배열에서 문자열을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f007-108">You can use overloads of the <xref:System.String> class constructor to create strings from character arrays.</span></span> <span data-ttu-id="7f007-109">특정 문자를 지정된 횟수만큼 복제하여 새 문자열을 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f007-109">You can also create a new string by duplicating a particular character a specified number of times.</span></span>  
  
## <a name="methods-that-return-strings"></a><span data-ttu-id="7f007-110">문자열을 반환하는 메서드</span><span class="sxs-lookup"><span data-stu-id="7f007-110">Methods that Return Strings</span></span>  
 <span data-ttu-id="7f007-111">다음 표에서는 새 문자열 개체를 반환하는 여러 유용한 메서드를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7f007-111">The following table lists several useful methods that return new string objects.</span></span>  
  
|<span data-ttu-id="7f007-112">메서드 이름</span><span class="sxs-lookup"><span data-stu-id="7f007-112">Method name</span></span>|<span data-ttu-id="7f007-113">사용</span><span class="sxs-lookup"><span data-stu-id="7f007-113">Use</span></span>|  
|-----------------|---------|  
|<xref:System.String.Format%2A?displayProperty=nameWithType>|<span data-ttu-id="7f007-114">입력 개체 집합에서 형식이 지정된 문자열을 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="7f007-114">Builds a formatted string from a set of input objects.</span></span>|  
|<xref:System.String.Concat%2A?displayProperty=nameWithType>|<span data-ttu-id="7f007-115">둘 이상의 문자열에서 문자열을 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="7f007-115">Builds strings from two or more strings.</span></span>|  
|<xref:System.String.Join%2A?displayProperty=nameWithType>|<span data-ttu-id="7f007-116">문자열 배열을 결합하여 새 문자열을 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="7f007-116">Builds a new string by combining an array of strings.</span></span>|  
|<xref:System.String.Insert%2A?displayProperty=nameWithType>|<span data-ttu-id="7f007-117">기존 문자열의 지정된 인덱스에 문자열을 삽입하여 새 문자열을 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="7f007-117">Builds a new string by inserting a string into the specified index of an existing string.</span></span>|  
|<xref:System.String.CopyTo%2A?displayProperty=nameWithType>|<span data-ttu-id="7f007-118">문자열의 지정된 문자를 문자 배열의 지정된 위치에 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="7f007-118">Copies specified characters in a string into a specified position in an array of characters.</span></span>|  
  
### <a name="format"></a><span data-ttu-id="7f007-119">형식</span><span class="sxs-lookup"><span data-stu-id="7f007-119">Format</span></span>  
 <span data-ttu-id="7f007-120">**String.Format** 메서드를 사용하여 서식이 지정된 문자열을 만들고 여러 개체를 나타내는 문자열을 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f007-120">You can use the **String.Format** method to create formatted strings and concatenate strings representing multiple objects.</span></span> <span data-ttu-id="7f007-121">이 메서드는 전달된 모든 개체를 문자열로 자동으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="7f007-121">This method automatically converts any passed object into a string.</span></span> <span data-ttu-id="7f007-122">예를 들어 애플리케이션이 **Int32** 값과 **DateTime** 값을 사용자에게 표시해야 하는 경우 **Format** 메서드를 사용하여 이러한 값을 나타내는 문자열을 쉽게 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f007-122">For example, if your application must display an **Int32** value and a **DateTime** value to the user, you can easily construct a string to represent these values using the **Format** method.</span></span> <span data-ttu-id="7f007-123">이 메서드에서 사용되는 형식 지정 규칙에 대한 자세한 내용은 [복합 형식 지정](composite-formatting.md) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7f007-123">For information about formatting conventions used with this method, see the section on [composite formatting](composite-formatting.md).</span></span>  
  
 <span data-ttu-id="7f007-124">다음 예제에서는 **Format** 메서드를 통해 정수 변수를 사용하는 문자열을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7f007-124">The following example uses the **Format** method to create a string that uses an integer variable.</span></span>  
  
 [!code-csharp[Strings.Creating#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Strings.Creating/cs/Example.cs#1)]
 [!code-vb[Strings.Creating#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Strings.Creating/vb/Example.vb#1)]  
  
 <span data-ttu-id="7f007-125">이 예제에서 <xref:System.DateTime.Now%2A?displayProperty=nameWithType>는 현재 스레드와 연결된 문화권에서 지정된 방식으로 현재 날짜와 시간을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="7f007-125">In this example,<xref:System.DateTime.Now%2A?displayProperty=nameWithType> displays the current date and time in a manner specified by the culture associated with the current thread.</span></span>  
  
### <a name="concat"></a><span data-ttu-id="7f007-126">Concat</span><span class="sxs-lookup"><span data-stu-id="7f007-126">Concat</span></span>  
 <span data-ttu-id="7f007-127">**String.Concat** 메서드를 사용하여 둘 이상의 기존 개체에서 새 문자열 개체를 쉽게 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f007-127">The **String.Concat** method can be used to easily create a new string object from two or more existing objects.</span></span> <span data-ttu-id="7f007-128">문자열을 연결하는 언어 독립적인 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="7f007-128">It provides a language-independent way to concatenate strings.</span></span> <span data-ttu-id="7f007-129">이 메서드는 **System.Object**에서 파생된 모든 클래스를 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="7f007-129">This method accepts any class that derives from **System.Object**.</span></span> <span data-ttu-id="7f007-130">다음 예제에서는 두 개의 기존 문자열 개체와 구분 문자에서 문자열을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7f007-130">The following example creates a string from two existing string objects and a separating character.</span></span>  
  
 [!code-csharp[Strings.Creating#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Strings.Creating/cs/Example.cs#2)]
 [!code-vb[Strings.Creating#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Strings.Creating/vb/Example.vb#2)]  
  
### <a name="join"></a><span data-ttu-id="7f007-131">Join</span><span class="sxs-lookup"><span data-stu-id="7f007-131">Join</span></span>  
 <span data-ttu-id="7f007-132">**String.Join** 메서드는 문자열 배열 및 구분 기호 문자열에서 새 문자열을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7f007-132">The **String.Join** method creates a new string from an array of strings and a separator string.</span></span> <span data-ttu-id="7f007-133">이 메서드는 여러 문자열을 함께 연결하여 쉼표 등으로 구분된 목록을 만들려는 경우에 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="7f007-133">This method is useful if you want to concatenate multiple strings together, making a list perhaps separated by a comma.</span></span>  
  
 <span data-ttu-id="7f007-134">다음 예제에서는 공백을 사용하여 문자열 배열을 바인딩합니다.</span><span class="sxs-lookup"><span data-stu-id="7f007-134">The following example uses a space to bind a string array.</span></span>  
  
 [!code-csharp[Strings.Creating#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Strings.Creating/cs/Example.cs#3)]
 [!code-vb[Strings.Creating#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Strings.Creating/vb/Example.vb#3)]  
  
### <a name="insert"></a><span data-ttu-id="7f007-135">Insert</span><span class="sxs-lookup"><span data-stu-id="7f007-135">Insert</span></span>  
 <span data-ttu-id="7f007-136">**String.Insert** 메서드는 다른 문자열의 지정된 위치에 문자열을 삽입하여 새 문자열을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7f007-136">The **String.Insert** method creates a new string by inserting a string into a specified position in another string.</span></span> <span data-ttu-id="7f007-137">이 메서드는 0부터 시작하는 인덱스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7f007-137">This method uses a zero-based index.</span></span> <span data-ttu-id="7f007-138">다음 예제에서는 `MyString`의 다섯 번째 인덱스 위치에 문자열을 삽입하고 이 값으로 새 문자열을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7f007-138">The following example inserts a string into the fifth index position of `MyString` and creates a new string with this value.</span></span>  
  
 [!code-csharp[Strings.Creating#4](../../../samples/snippets/csharp/VS_Snippets_CLR/Strings.Creating/cs/Example.cs#4)]
 [!code-vb[Strings.Creating#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Strings.Creating/vb/Example.vb#4)]  
  
### <a name="copyto"></a><span data-ttu-id="7f007-139">CopyTo</span><span class="sxs-lookup"><span data-stu-id="7f007-139">CopyTo</span></span>  
 <span data-ttu-id="7f007-140">**String.CopyTo** 메서드는 문자열의 일부를 문자 배열에 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="7f007-140">The **String.CopyTo** method copies portions of a string into an array of characters.</span></span> <span data-ttu-id="7f007-141">기존 문자열의 시작 인덱스와 복사할 문자 수를 둘 다 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f007-141">You can specify both the beginning index of the string and the number of characters to be copied.</span></span> <span data-ttu-id="7f007-142">이 메서드는 소스 인덱스, 문자 배열, 대상 인덱스 및 복사할 문자 수를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7f007-142">This method takes the source index, an array of characters, the destination index, and the number of characters to copy.</span></span> <span data-ttu-id="7f007-143">모든 인덱스는 0부터 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="7f007-143">All indexes are zero-based.</span></span>  
  
 <span data-ttu-id="7f007-144">다음 예제에서는 **CopyTo** 메서드를 사용하여 “Hello” 단어의 문자를 문자열 개체에서 문자 배열의 첫 번째 인덱스 위치로 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="7f007-144">The following example uses the **CopyTo** method to copy the characters of the word "Hello" from a string object to the first index position of an array of characters.</span></span>  
  
 [!code-csharp[Strings.Creating#5](../../../samples/snippets/csharp/VS_Snippets_CLR/Strings.Creating/cs/Example.cs#5)]
 [!code-vb[Strings.Creating#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Strings.Creating/vb/Example.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="7f007-145">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7f007-145">See also</span></span>

- [<span data-ttu-id="7f007-146">기본적인 문자열 작업</span><span class="sxs-lookup"><span data-stu-id="7f007-146">Basic String Operations</span></span>](basic-string-operations.md)
- [<span data-ttu-id="7f007-147">복합 형식 지정</span><span class="sxs-lookup"><span data-stu-id="7f007-147">Composite Formatting</span></span>](composite-formatting.md)
