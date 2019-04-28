---
title: Visual Basic의 문자열 조작 메서드 유형
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], manipulating [Visual Basic]
- string manipulation
ms.assetid: 905055cd-7f50-48fb-9eed-b0995af1dc1f
ms.openlocfilehash: 44eb101ebdfeb316958a659107190ef1fc84df44
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61938270"
---
# <a name="types-of-string-manipulation-methods-in-visual-basic"></a><span data-ttu-id="6fb47-102">Visual Basic의 문자열 조작 메서드 유형</span><span class="sxs-lookup"><span data-stu-id="6fb47-102">Types of String Manipulation Methods in Visual Basic</span></span>
<span data-ttu-id="6fb47-103">분석 하 고 문자열을 조작 하는 여러 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6fb47-103">There are several different ways to analyze and manipulate your strings.</span></span> <span data-ttu-id="6fb47-104">메서드 중 일부는 Visual Basic 언어의 일부인 있고에 내재 된 `String` 클래스.</span><span class="sxs-lookup"><span data-stu-id="6fb47-104">Some of the methods are a part of the Visual Basic language, and others are inherent in the `String` class.</span></span>  
  
## <a name="visual-basic-language-and-the-net-framework"></a><span data-ttu-id="6fb47-105">Visual Basic 언어 및.NET Framework</span><span class="sxs-lookup"><span data-stu-id="6fb47-105">Visual Basic Language and the .NET Framework</span></span>  
 <span data-ttu-id="6fb47-106">Visual Basic 메서드는 언어의 기본 기능으로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6fb47-106">Visual Basic methods are used as inherent functions of the language.</span></span> <span data-ttu-id="6fb47-107">코드에서 자격 증명 없이 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6fb47-107">They may be used without qualification in your code.</span></span> <span data-ttu-id="6fb47-108">다음 예제에서는 일반적인 Visual Basic 문자열 조작 명령 사용 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6fb47-108">The following example shows typical use of a Visual Basic string-manipulation command:</span></span>  
  
 [!code-vb[VbVbalrStrings#44](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#44)]  
  
 <span data-ttu-id="6fb47-109">이 예제는 `Mid` 함수에서 직접 작업을 수행 `aString` 값을 할당 하 고 `bString`입니다.</span><span class="sxs-lookup"><span data-stu-id="6fb47-109">In this example, the `Mid` function performs a direct operation on `aString` and assigns the value to `bString`.</span></span>  
  
 <span data-ttu-id="6fb47-110">Visual Basic 문자열 조작 메서드 목록을 참조 하세요 [문자열 조작 요약](../../../../visual-basic/language-reference/keywords/string-manipulation-summary.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="6fb47-110">For a list of Visual Basic string manipulation methods, see [String Manipulation Summary](../../../../visual-basic/language-reference/keywords/string-manipulation-summary.md).</span></span>  
  
### <a name="shared-methods-and-instance-methods"></a><span data-ttu-id="6fb47-111">공유 메서드와 인스턴스 메서드</span><span class="sxs-lookup"><span data-stu-id="6fb47-111">Shared Methods and Instance Methods</span></span>  
 <span data-ttu-id="6fb47-112">메서드를 사용 하 여 문자열을 조작할 수도 있습니다는 `String` 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="6fb47-112">You can also manipulate strings with the methods of the `String` class.</span></span> <span data-ttu-id="6fb47-113">메서드는 방법은 두 가지가 `String`: *공유* 메서드 및 *인스턴스* 메서드.</span><span class="sxs-lookup"><span data-stu-id="6fb47-113">There are two types of methods in `String`: *shared* methods and *instance* methods.</span></span>  
  
#### <a name="shared-methods"></a><span data-ttu-id="6fb47-114">공유 메서드</span><span class="sxs-lookup"><span data-stu-id="6fb47-114">Shared Methods</span></span>  
 <span data-ttu-id="6fb47-115">발생 하는 방법은 공유 메서드는 `String` 클래스 자체와 작동 하도록 해당 클래스의 인스턴스를 필요로 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6fb47-115">A shared method is a method that stems from the `String` class itself and does not require an instance of that class to work.</span></span> <span data-ttu-id="6fb47-116">이러한 메서드는 클래스의 이름으로 한정할 수 있습니다 (`String`)의 인스턴스 대신는 `String` 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="6fb47-116">These methods can be qualified with the name of the class (`String`) rather than with an instance of the `String` class.</span></span> <span data-ttu-id="6fb47-117">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="6fb47-117">For example:</span></span>  
  
 [!code-vb[VbVbalrStrings#45](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#45)]  
  
 <span data-ttu-id="6fb47-118">앞의 예제에는 <xref:System.String.Copy%2A?displayProperty=nameWithType> 메서드는 정적 메서드를 식에 사용 되는 역할은 지정 하 고 결과 값을 할당 `bString`합니다.</span><span class="sxs-lookup"><span data-stu-id="6fb47-118">In the preceding example, the <xref:System.String.Copy%2A?displayProperty=nameWithType> method is a static method, which acts upon an expression it is given and assigns the resulting value to `bString`.</span></span>  
  
#### <a name="instance-methods"></a><span data-ttu-id="6fb47-119">인스턴스 메서드</span><span class="sxs-lookup"><span data-stu-id="6fb47-119">Instance Methods</span></span>  
 <span data-ttu-id="6fb47-120">인스턴스 메서드는 반면,의 특정 인스턴스에서 stem `String` 및 인스턴스 이름으로 정규화 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6fb47-120">Instance methods, by contrast, stem from a particular instance of `String` and must be qualified with the instance name.</span></span> <span data-ttu-id="6fb47-121">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="6fb47-121">For example:</span></span>  
  
 [!code-vb[VbVbalrStrings#46](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#46)]  
  
 <span data-ttu-id="6fb47-122">이 예제는 <xref:System.String.Substring%2A?displayProperty=nameWithType> 메서드는 인스턴스 메서드입니다 `String` (즉, `aString`).</span><span class="sxs-lookup"><span data-stu-id="6fb47-122">In this example, the <xref:System.String.Substring%2A?displayProperty=nameWithType> method is a method of the instance of `String` (that is, `aString`).</span></span> <span data-ttu-id="6fb47-123">작업 수행 `aString` 해당 값을 할당 하 고 `bString`입니다.</span><span class="sxs-lookup"><span data-stu-id="6fb47-123">It performs an operation on `aString` and assigns that value to `bString`.</span></span>  
  
 <span data-ttu-id="6fb47-124">자세한 내용은 설명서를 참조 합니다 <xref:System.String> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="6fb47-124">For more information, see the documentation for the <xref:System.String> class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6fb47-125">참고자료</span><span class="sxs-lookup"><span data-stu-id="6fb47-125">See also</span></span>

- [<span data-ttu-id="6fb47-126">Visual Basic의 문자열 소개</span><span class="sxs-lookup"><span data-stu-id="6fb47-126">Introduction to Strings in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
