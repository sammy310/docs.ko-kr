---
title: 문자열 조작 메서드 형식
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], manipulating [Visual Basic]
- string manipulation
ms.assetid: 905055cd-7f50-48fb-9eed-b0995af1dc1f
ms.openlocfilehash: aba9af9c699cf8d07862c5d2967902bec1623500
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84363761"
---
# <a name="types-of-string-manipulation-methods-in-visual-basic"></a><span data-ttu-id="0be5c-102">Visual Basic의 문자열 조작 메서드 유형</span><span class="sxs-lookup"><span data-stu-id="0be5c-102">Types of String Manipulation Methods in Visual Basic</span></span>
<span data-ttu-id="0be5c-103">문자열을 분석 하 고 조작 하는 여러 가지 방법이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0be5c-103">There are several different ways to analyze and manipulate your strings.</span></span> <span data-ttu-id="0be5c-104">일부 메서드는 Visual Basic 언어의 일부 이며 다른 메서드는 클래스에 내재 되어 있습니다 `String` .</span><span class="sxs-lookup"><span data-stu-id="0be5c-104">Some of the methods are a part of the Visual Basic language, and others are inherent in the `String` class.</span></span>  
  
## <a name="visual-basic-language-and-the-net-framework"></a><span data-ttu-id="0be5c-105">Visual Basic 언어 및 .NET Framework</span><span class="sxs-lookup"><span data-stu-id="0be5c-105">Visual Basic Language and the .NET Framework</span></span>  
 <span data-ttu-id="0be5c-106">Visual Basic 메서드는 언어의 고유 함수로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0be5c-106">Visual Basic methods are used as inherent functions of the language.</span></span> <span data-ttu-id="0be5c-107">코드에서 한정자 없이 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0be5c-107">They may be used without qualification in your code.</span></span> <span data-ttu-id="0be5c-108">다음 예에서는 Visual Basic 문자열 조작 명령의 일반적인 사용을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0be5c-108">The following example shows typical use of a Visual Basic string-manipulation command:</span></span>  
  
 [!code-vb[VbVbalrStrings#44](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#44)]  
  
 <span data-ttu-id="0be5c-109">이 예제에서 함수는 `Mid` 에 대 한 직접 연산을 수행 하 `aString` 고에 값을 할당 `bString` 합니다.</span><span class="sxs-lookup"><span data-stu-id="0be5c-109">In this example, the `Mid` function performs a direct operation on `aString` and assigns the value to `bString`.</span></span>  
  
 <span data-ttu-id="0be5c-110">Visual Basic 문자열 조작 메서드 목록은 [문자열 조작 요약](../../../language-reference/keywords/string-manipulation-summary.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0be5c-110">For a list of Visual Basic string manipulation methods, see [String Manipulation Summary](../../../language-reference/keywords/string-manipulation-summary.md).</span></span>  
  
### <a name="shared-methods-and-instance-methods"></a><span data-ttu-id="0be5c-111">공유 메서드 및 인스턴스 메서드</span><span class="sxs-lookup"><span data-stu-id="0be5c-111">Shared Methods and Instance Methods</span></span>  
 <span data-ttu-id="0be5c-112">클래스의 메서드를 사용 하 여 문자열을 조작할 수도 있습니다 `String` .</span><span class="sxs-lookup"><span data-stu-id="0be5c-112">You can also manipulate strings with the methods of the `String` class.</span></span> <span data-ttu-id="0be5c-113">에는 `String` *shared* 메서드와 *인스턴스* 메서드 라는 두 가지 유형의 메서드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0be5c-113">There are two types of methods in `String`: *shared* methods and *instance* methods.</span></span>  
  
#### <a name="shared-methods"></a><span data-ttu-id="0be5c-114">공유 메서드</span><span class="sxs-lookup"><span data-stu-id="0be5c-114">Shared Methods</span></span>  
 <span data-ttu-id="0be5c-115">공유 메서드는 `String` 클래스 자체에서 생기고 해당 클래스의 인스턴스가 작동 하지 않아도 되는 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="0be5c-115">A shared method is a method that stems from the `String` class itself and does not require an instance of that class to work.</span></span> <span data-ttu-id="0be5c-116">이러한 메서드는 클래스의 인스턴스가 아닌 클래스 이름 ()으로 정규화 될 수 있습니다 `String` `String` .</span><span class="sxs-lookup"><span data-stu-id="0be5c-116">These methods can be qualified with the name of the class (`String`) rather than with an instance of the `String` class.</span></span> <span data-ttu-id="0be5c-117">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="0be5c-117">For example:</span></span>  
  
 [!code-vb[VbVbalrStrings#45](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#45)]  
  
 <span data-ttu-id="0be5c-118">앞의 예제에서 메서드는 <xref:System.String.Copy%2A?displayProperty=nameWithType> 지정 된 식에 대해 작동 하 고 결과 값을에 할당 하는 정적 메서드입니다 `bString` .</span><span class="sxs-lookup"><span data-stu-id="0be5c-118">In the preceding example, the <xref:System.String.Copy%2A?displayProperty=nameWithType> method is a static method, which acts upon an expression it is given and assigns the resulting value to `bString`.</span></span>  
  
#### <a name="instance-methods"></a><span data-ttu-id="0be5c-119">인스턴스 메서드</span><span class="sxs-lookup"><span data-stu-id="0be5c-119">Instance Methods</span></span>  
 <span data-ttu-id="0be5c-120">이와 대조적으로 인스턴스 메서드는의 특정 인스턴스에서 생기고 `String` 인스턴스 이름으로 한정 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0be5c-120">Instance methods, by contrast, stem from a particular instance of `String` and must be qualified with the instance name.</span></span> <span data-ttu-id="0be5c-121">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="0be5c-121">For example:</span></span>  
  
 [!code-vb[VbVbalrStrings#46](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#46)]  
  
 <span data-ttu-id="0be5c-122">이 예제에서 메서드는 <xref:System.String.Substring%2A?displayProperty=nameWithType> 의 인스턴스 (즉,)의 메서드입니다 `String` `aString` .</span><span class="sxs-lookup"><span data-stu-id="0be5c-122">In this example, the <xref:System.String.Substring%2A?displayProperty=nameWithType> method is a method of the instance of `String` (that is, `aString`).</span></span> <span data-ttu-id="0be5c-123">에서 연산을 수행 하 `aString` 고 해당 값을에 할당 `bString` 합니다.</span><span class="sxs-lookup"><span data-stu-id="0be5c-123">It performs an operation on `aString` and assigns that value to `bString`.</span></span>  
  
 <span data-ttu-id="0be5c-124">자세한 내용은 클래스에 대 한 설명서를 참조 하세요 <xref:System.String> .</span><span class="sxs-lookup"><span data-stu-id="0be5c-124">For more information, see the documentation for the <xref:System.String> class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0be5c-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0be5c-125">See also</span></span>

- [<span data-ttu-id="0be5c-126">Visual Basic의 문자열 소개</span><span class="sxs-lookup"><span data-stu-id="0be5c-126">Introduction to Strings in Visual Basic</span></span>](introduction-to-strings.md)
