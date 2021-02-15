---
description: '자세한 정보: 방법: 제네릭 클래스 사용 (Visual Basic)'
title: '방법: 제네릭 클래스 사용'
ms.date: 07/20/2015
helpviewer_keywords:
- type parameters [Visual Basic], defining
- data type arguments [Visual Basic], defining
- arguments [Visual Basic], data types
- Of keyword [Visual Basic], using
- generic parameters
- data type parameters
- generics [Visual Basic], about generics
- data types [Visual Basic], as parameters
- data types [Visual Basic], as arguments
- parameters [Visual Basic], type
- types [Visual Basic], generic
- parameters [Visual Basic], generic
- generics [Visual Basic], creating generic types
- data type arguments
- parameters [Visual Basic], data type
- data type parameters [Visual Basic], defining
- type arguments [Visual Basic], defining
- arguments [Visual Basic], type
ms.assetid: 242dd2a6-86c4-4ce7-83f2-f2661803f752
ms.openlocfilehash: b21f29223c6a7f611fd4064a0df28ed72f599361
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100483965"
---
# <a name="how-to-use-a-generic-class-visual-basic"></a><span data-ttu-id="3c004-103">방법: 제네릭 클래스 사용(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3c004-103">How to: Use a Generic Class (Visual Basic)</span></span>

<span data-ttu-id="3c004-104">*형식 매개 변수* 를 사용하는 클래스를 *제네릭 클래스* 라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c004-104">A class that takes *type parameters* is called a *generic class*.</span></span> <span data-ttu-id="3c004-105">제네릭 클래스를 사용 중인 경우 이러한 각 매개 변수에 대해 *형식 인수* 를 제공하여, 여기에서 *생성된 클래스* 를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c004-105">If you are using a generic class, you can generate a *constructed class* from it by supplying a *type argument* for each of these parameters.</span></span> <span data-ttu-id="3c004-106">그런 다음 생성된 클래스 형식의 변수를 선언하고, 생성된 클래스의 인스턴스를 만들어 해당 변수에 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c004-106">You can then declare a variable of the constructed class type, and you can create an instance of the constructed class and assign it to that variable.</span></span>  
  
 <span data-ttu-id="3c004-107">클래스 이외에도 제네릭 구조체, 인터페이스, 프로시저 및 대리자도 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c004-107">In addition to classes, you can also define and use generic structures, interfaces, procedures, and delegates.</span></span>  
  
 <span data-ttu-id="3c004-108">다음 절차에서는 .NET Framework에 정의 된 제네릭 클래스를 사용 하 여이 클래스에서 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="3c004-108">The following procedure takes a generic class defined in the .NET Framework and creates an instance from it.</span></span>  
  
### <a name="to-use-a-class-that-takes-a-type-parameter"></a><span data-ttu-id="3c004-109">형식 매개 변수를 가져오는 클래스를 사용하려면</span><span class="sxs-lookup"><span data-stu-id="3c004-109">To use a class that takes a type parameter</span></span>  
  
1. <span data-ttu-id="3c004-110">소스 파일의 시작 부분에 네임 스페이스를 가져오는 [Imports 문 (.Net 네임 스페이스 및 형식)](../../../language-reference/statements/imports-statement-net-namespace-and-type.md) 을 포함 합니다 <xref:System.Collections.Generic?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="3c004-110">At the beginning of your source file, include an [Imports Statement (.NET Namespace and Type)](../../../language-reference/statements/imports-statement-net-namespace-and-type.md) to import the <xref:System.Collections.Generic?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="3c004-111">이렇게 하면 <xref:System.Collections.Queue?displayProperty=nameWithType> 같은 다른 큐 클래스와 차별화하기 위해 정규화하지 않고도 <xref:System.Collections.Generic.Queue%601?displayProperty=nameWithType> 클래스를 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c004-111">This allows you to refer to the <xref:System.Collections.Generic.Queue%601?displayProperty=nameWithType> class without having to fully qualify it to differentiate it from other queue classes such as <xref:System.Collections.Queue?displayProperty=nameWithType>.</span></span>  
  
2. <span data-ttu-id="3c004-112">일반적인 방법으로 개체를 만들지만 클래스 이름 바로 뒤에 `(Of type)` 을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="3c004-112">Create the object in the normal way, but add `(Of type)` immediately after the class name.</span></span>  
  
     <span data-ttu-id="3c004-113">다음 예에서는 동일한 클래스(<xref:System.Collections.Generic.Queue%601?displayProperty=nameWithType>)를 사용하여, 서로 다른 데이터 형식의 항목을 포함하는 두 개의 큐 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="3c004-113">The following example uses the same class (<xref:System.Collections.Generic.Queue%601?displayProperty=nameWithType>) to create two queue objects that hold items of different data types.</span></span> <span data-ttu-id="3c004-114">각 큐의 끝에 항목을 추가한 다음 각 큐의 앞부분부터 항목을 제거하고 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="3c004-114">It adds items to the end of each queue and then removes and displays items from the front of each queue.</span></span>  
  
     [!code-vb[VbVbalrDataTypes#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDataTypes/VB/Class1.vb#9)]  
  
## <a name="see-also"></a><span data-ttu-id="3c004-115">추가 정보</span><span class="sxs-lookup"><span data-stu-id="3c004-115">See also</span></span>

- [<span data-ttu-id="3c004-116">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="3c004-116">Data Types</span></span>](index.md)
- [<span data-ttu-id="3c004-117">Visual Basic의 제네릭 형식</span><span class="sxs-lookup"><span data-stu-id="3c004-117">Generic Types in Visual Basic</span></span>](generic-types.md)
- [<span data-ttu-id="3c004-118">언어 독립성 및 언어 독립적 구성 요소</span><span class="sxs-lookup"><span data-stu-id="3c004-118">Language Independence and Language-Independent Components</span></span>](../../../../standard/language-independence-and-language-independent-components.md)
- [<span data-ttu-id="3c004-119">으로</span><span class="sxs-lookup"><span data-stu-id="3c004-119">Of</span></span>](../../../language-reference/statements/of-clause.md)
- [<span data-ttu-id="3c004-120">Imports 문(.NET 네임스페이스 및 형식)</span><span class="sxs-lookup"><span data-stu-id="3c004-120">Imports Statement (.NET Namespace and Type)</span></span>](../../../language-reference/statements/imports-statement-net-namespace-and-type.md)
- [<span data-ttu-id="3c004-121">방법: 다른 데이터 형식에 동일한 기능을 제공할 수 있는 클래스 정의</span><span class="sxs-lookup"><span data-stu-id="3c004-121">How to: Define a Class That Can Provide Identical Functionality on Different Data Types</span></span>](how-to-define-a-class-that-can-provide-identical-functionality.md)
- [<span data-ttu-id="3c004-122">반복기</span><span class="sxs-lookup"><span data-stu-id="3c004-122">Iterators</span></span>](../../concepts/iterators.md)
