---
title: 열거형 형식 문자열
description: .NET에서 Enum.ToString 메서드를 사용하여 열거형 형식 문자열을 만듭니다. 열거형 멤버의 숫자, 16진수 또는 문자열 값의 형식을 지정합니다.
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- format specifiers, enumeration format strings
- enumeration format strings
- formatting [.NET Framework], enumeration
ms.assetid: dd1ff672-1052-42cf-8666-4924fb6cd1a1
ms.openlocfilehash: 825357cf4a56132dae0870972d316eff89b0c94f
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84583429"
---
# <a name="enumeration-format-strings"></a><span data-ttu-id="eee81-104">열거형 형식 문자열</span><span class="sxs-lookup"><span data-stu-id="eee81-104">Enumeration format strings</span></span>

<span data-ttu-id="eee81-105"><xref:System.Enum.ToString%2A?displayProperty=nameWithType> 메서드를 사용하여 열거형 멤버의 숫자, 16진수 또는 문자열 값을 나타내는 새 문자열 개체를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eee81-105">You can use the <xref:System.Enum.ToString%2A?displayProperty=nameWithType> method to create a new string object that represents the numeric, hexadecimal, or string value of an enumeration member.</span></span> <span data-ttu-id="eee81-106">이 메서드는 열거형 형식 문자열 중 하나를 사용하여 반환할 값을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="eee81-106">This method takes one of the enumeration formatting strings to specify the value that you want returned.</span></span>

<span data-ttu-id="eee81-107">다음 섹션에서는 열거형 형식 문자열과 반환되는 값을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="eee81-107">The following sections list the enumeration formatting strings and the values they return.</span></span> <span data-ttu-id="eee81-108">이러한 형식 지정자는 대/소문자를 구분하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="eee81-108">These format specifiers are not case-sensitive.</span></span>

## <a name="g-or-g"></a><span data-ttu-id="eee81-109">G 또는 g</span><span class="sxs-lookup"><span data-stu-id="eee81-109">G or g</span></span>

<span data-ttu-id="eee81-110">가능한 경우 열거형 항목을 문자열 값으로 표시하고, 가능하지 않은 경우 현재 인스턴스의 정수 값을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="eee81-110">Displays the enumeration entry as a string value, if possible, and otherwise displays the integer value of the current instance.</span></span> <span data-ttu-id="eee81-111">**Flags** 특성을 설정하여 열거형을 정의한 경우 유효한 각 항목의 문자열 값이 쉼표로 구분되어 서로 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="eee81-111">If the enumeration is defined with the **Flags** attribute set, the string values of each valid entry are concatenated together, separated by commas.</span></span> <span data-ttu-id="eee81-112">**Flags** 특성을 설정하지 않은 경우 잘못된 값이 숫자 항목으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="eee81-112">If the **Flags** attribute is not set, an invalid value is displayed as a numeric entry.</span></span> <span data-ttu-id="eee81-113">다음 예제에서는 G 형식 지정자를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="eee81-113">The following example illustrates the G format specifier.</span></span>

[!code-csharp[Formatting.Enum#1](~/samples/snippets/csharp/VS_Snippets_CLR/Formatting.Enum/cs/enum1.cs#1)]
[!code-vb[Formatting.Enum#1](~/samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Enum/vb/enum1.vb#1)]

## <a name="f-or-f"></a><span data-ttu-id="eee81-114">F 또는 f</span><span class="sxs-lookup"><span data-stu-id="eee81-114">F or f</span></span>

<span data-ttu-id="eee81-115">열거형 항목을 문자열 값으로 표시합니다(가능한 경우).</span><span class="sxs-lookup"><span data-stu-id="eee81-115">Displays the enumeration entry as a string value, if possible.</span></span> <span data-ttu-id="eee81-116">**Flags** 특성이 없어도 열거형 항목의 총합으로 값을 완전히 표시할 수 있는 경우 유효한 각 항목의 문자열 값이 쉼표로 구분되어 서로 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="eee81-116">If the value can be completely displayed as a summation of the entries in the enumeration (even if the **Flags** attribute is not present), the string values of each valid entry are concatenated together, separated by commas.</span></span> <span data-ttu-id="eee81-117">열거형 항목으로 값을 완전히 확인할 수 없는 경우에는 값의 형식이 정수 값으로 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="eee81-117">If the value cannot be completely determined by the enumeration entries, then the value is formatted as the integer value.</span></span> <span data-ttu-id="eee81-118">다음 예제에서는 F 형식 지정자를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="eee81-118">The following example illustrates the F format specifier.</span></span>

[!code-csharp[Formatting.Enum#2](~/samples/snippets/csharp/VS_Snippets_CLR/Formatting.Enum/cs/enum1.cs#2)]
[!code-vb[Formatting.Enum#2](~/samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Enum/vb/enum1.vb#2)]

## <a name="d-or-d"></a><span data-ttu-id="eee81-119">D 또는 d</span><span class="sxs-lookup"><span data-stu-id="eee81-119">D or d</span></span>

<span data-ttu-id="eee81-120">열거형 항목을 가능한 가장 짧은 표현의 정수 값으로 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="eee81-120">Displays the enumeration entry as an integer value in the shortest representation possible.</span></span> <span data-ttu-id="eee81-121">다음 예제에서는 D 형식 지정자를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="eee81-121">The following example illustrates the D format specifier.</span></span>

[!code-csharp[Formatting.Enum#3](~/samples/snippets/csharp/VS_Snippets_CLR/Formatting.Enum/cs/enum1.cs#3)]
[!code-vb[Formatting.Enum#3](~/samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Enum/vb/enum1.vb#3)]

## <a name="x-or-x"></a><span data-ttu-id="eee81-122">X 또는 x</span><span class="sxs-lookup"><span data-stu-id="eee81-122">X or x</span></span>

<span data-ttu-id="eee81-123">열거형 항목을 16진수 값으로 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="eee81-123">Displays the enumeration entry as a hexadecimal value.</span></span> <span data-ttu-id="eee81-124">결과 문자열이 열거형의 [기본 숫자 형식](xref:System.Enum.GetUnderlyingType%2A)에서 바이트마다 2개 문자를 갖도록 하기 위해 필요에 따라 앞에 0이 오는 값으로 표현됩니다.</span><span class="sxs-lookup"><span data-stu-id="eee81-124">The value is represented with leading zeros as necessary, to ensure that the result string has two characters for each byte in the enumeration type's [underlying numeric type](xref:System.Enum.GetUnderlyingType%2A).</span></span> <span data-ttu-id="eee81-125">다음 예제에서는 X 형식 지정자를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="eee81-125">The following example illustrates the X format specifier.</span></span> <span data-ttu-id="eee81-126">예제에서 <xref:System.ConsoleColor> 및 <xref:System.IO.FileAttributes>의 기본 형식은 <xref:System.Int32> 또는 8 글자 결과 문자열을 생성하는 32비트(또는 4바이트) 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="eee81-126">In the example, the underlying type of both <xref:System.ConsoleColor> and <xref:System.IO.FileAttributes> is <xref:System.Int32>, or a 32-bit (or 4-byte) integer, which produces an 8-character result string.</span></span>

[!code-csharp[Formatting.Enum#4](~/samples/snippets/csharp/VS_Snippets_CLR/Formatting.Enum/cs/enum1.cs#4)]
[!code-vb[Formatting.Enum#4](~/samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Enum/vb/enum1.vb#4)]

## <a name="example"></a><span data-ttu-id="eee81-127">예제</span><span class="sxs-lookup"><span data-stu-id="eee81-127">Example</span></span>

<span data-ttu-id="eee81-128">다음 예제에서는 세 개의 항목 `Red`, `Blue` 및 `Green`으로 구성된 `Colors`라는 열거형을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="eee81-128">The following example defines an enumeration called `Colors` that consists of three entries: `Red`, `Blue`, and `Green`.</span></span>

[!code-csharp[Formatting.Enum#5](~/samples/snippets/csharp/VS_Snippets_CLR/Formatting.Enum/cs/enum1.cs#5)]
[!code-vb[Formatting.Enum#5](~/samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Enum/vb/enum1.vb#5)]

<span data-ttu-id="eee81-129">열거형이 정의되면 다음과 같이 인스턴스를 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eee81-129">After the enumeration is defined, an instance can be declared in the following manner.</span></span>

[!code-csharp[Formatting.Enum#6](~/samples/snippets/csharp/VS_Snippets_CLR/Formatting.Enum/cs/enum1.cs#6)]
[!code-vb[Formatting.Enum#6](~/samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Enum/vb/enum1.vb#6)]

<span data-ttu-id="eee81-130">그런 다음 `Color.ToString(System.String)` 메서드를 사용하여 전달된 형식 지정자에 따라 열거형 값을 다양한 방식으로 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eee81-130">The `Color.ToString(System.String)` method can then be used to display the enumeration value in different ways, depending on the format specifier passed to it.</span></span>

[!code-csharp[Formatting.Enum#7](~/samples/snippets/csharp/VS_Snippets_CLR/Formatting.Enum/cs/enum1.cs#7)]
[!code-vb[Formatting.Enum#7](~/samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Enum/vb/enum1.vb#7)]

## <a name="see-also"></a><span data-ttu-id="eee81-131">참조</span><span class="sxs-lookup"><span data-stu-id="eee81-131">See also</span></span>

- [<span data-ttu-id="eee81-132">형식 서식 지정</span><span class="sxs-lookup"><span data-stu-id="eee81-132">Formatting Types</span></span>](formatting-types.md)
