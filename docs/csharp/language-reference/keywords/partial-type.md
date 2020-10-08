---
description: partial 형식 - C# 참조
title: partial 형식 - C# 참조
ms.date: 07/20/2015
f1_keywords:
- partialtype
- partialtype_CSharpKeyword
helpviewer_keywords:
- partial types [C#]
ms.assetid: 27320743-a22e-4c7b-b0b3-53afe3607334
ms.openlocfilehash: 4e73b34390143a2ac9b839e1da79b7894232c4b4
ms.sourcegitcommit: b4a46f6d7ebf44c0035627d00924164bcae2db30
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2020
ms.locfileid: "91437881"
---
# <a name="partial-type-c-reference"></a><span data-ttu-id="85ebc-103">partial 형식(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="85ebc-103">partial type (C# Reference)</span></span>

<span data-ttu-id="85ebc-104">부분 형식(Partial Type) 정의를 사용하면 클래스, 구조체, 인터페이스 또는 레코드의 정의를 여러 파일로 분할할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85ebc-104">Partial type definitions allow for the definition of a class, struct, interface, or record to be split into multiple files.</span></span>

<span data-ttu-id="85ebc-105">*File1.cs*:</span><span class="sxs-lookup"><span data-stu-id="85ebc-105">In *File1.cs*:</span></span>

[!code-csharp[csrefKeywordsContextual#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsContextual/CS/csrefKeywordsContextual.cs#3)]  

<span data-ttu-id="85ebc-106">*File2.cs*에서 선언은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="85ebc-106">In *File2.cs* the declaration:</span></span>

[!code-csharp[csrefKeywordsContextual#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsContextual/CS/csrefKeywordsContextual.cs#4)]  

## <a name="remarks"></a><span data-ttu-id="85ebc-107">설명</span><span class="sxs-lookup"><span data-stu-id="85ebc-107">Remarks</span></span>

<span data-ttu-id="85ebc-108">클래스, 구조체 또는 인터페이스 형식을 여러 파일에 분할하면 대형 프로젝트 또는 [Windows Forms 디자이너](/dotnet/desktop/winforms/controls/developing-windows-forms-controls-at-design-time)에서 제공하는 것과 같은 자동으로 생성된 코드로 작업할 때 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85ebc-108">Splitting a class, struct or interface type over several files can be useful when you are working with large projects, or with automatically generated code such as that provided by the [Windows Forms Designer](/dotnet/desktop/winforms/controls/developing-windows-forms-controls-at-design-time).</span></span> <span data-ttu-id="85ebc-109">부분 형식(Partial Type)에는 [부분 메서드(Partial Method)](partial-method.md)가 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85ebc-109">A partial type may contain a [partial method](partial-method.md).</span></span> <span data-ttu-id="85ebc-110">자세한 내용은 참조 [Partial 클래스 및 메서드](../../programming-guide/classes-and-structs/partial-classes-and-methods.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="85ebc-110">For more information, see [Partial Classes and Methods](../../programming-guide/classes-and-structs/partial-classes-and-methods.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="85ebc-111">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="85ebc-111">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="85ebc-112">참조</span><span class="sxs-lookup"><span data-stu-id="85ebc-112">See also</span></span>

- [<span data-ttu-id="85ebc-113">C# 참조</span><span class="sxs-lookup"><span data-stu-id="85ebc-113">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="85ebc-114">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="85ebc-114">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="85ebc-115">한정자</span><span class="sxs-lookup"><span data-stu-id="85ebc-115">Modifiers</span></span>](index.md)
- [<span data-ttu-id="85ebc-116">제네릭 소개</span><span class="sxs-lookup"><span data-stu-id="85ebc-116">Introduction to Generics</span></span>](../../programming-guide/generics/index.md)
