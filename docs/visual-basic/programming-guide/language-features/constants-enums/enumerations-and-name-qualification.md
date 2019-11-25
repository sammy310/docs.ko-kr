---
title: 열거형 및 이름 한정
ms.date: 07/20/2015
helpviewer_keywords:
- declarations [Visual Basic], enumerations
- Imports statement [Visual Basic], namespace declarations
- declaring namespaces [Visual Basic], enumerations
- name collisions
- ambiguous names [Visual Basic], enumerations
- enumerations [Visual Basic], name qualification
- names [Visual Basic], avoiding conflicts
- namespaces [Visual Basic], declaring
- naming conflicts, enumerations
- naming conflicts, qualifying names
- declaring enumerations
- references [Visual Basic], enumeration members
- naming conventions [Visual Basic], naming conflicts
- declarations [Visual Basic], namespaces
ms.assetid: 08ba2738-df52-4140-bc55-f57c871c9b73
ms.openlocfilehash: 4121266447b771ba954ad52a46e0d8b88de3f9cc
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347490"
---
# <a name="enumerations-and-name-qualification-visual-basic"></a><span data-ttu-id="6256e-102">열거형 및 이름 한정(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6256e-102">Enumerations and Name Qualification (Visual Basic)</span></span>
<span data-ttu-id="6256e-103">Normally, when referring to a member of an enumeration, you must qualify the member name with the enumeration name.</span><span class="sxs-lookup"><span data-stu-id="6256e-103">Normally, when referring to a member of an enumeration, you must qualify the member name with the enumeration name.</span></span> <span data-ttu-id="6256e-104">For example, to refer to the `Sunday` member of your `Days` enumeration, you would use the following syntax:</span><span class="sxs-lookup"><span data-stu-id="6256e-104">For example, to refer to the `Sunday` member of your `Days` enumeration, you would use the following syntax:</span></span>  
  
 [!code-vb[VbEnumsTask#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#18)]  
  
## <a name="using-the-imports-statement"></a><span data-ttu-id="6256e-105">Using the Imports Statement</span><span class="sxs-lookup"><span data-stu-id="6256e-105">Using the Imports Statement</span></span>  
 <span data-ttu-id="6256e-106">You can avoid using fully qualified names by adding an `Imports` statement to the namespace declarations section of your code, as in the following example:</span><span class="sxs-lookup"><span data-stu-id="6256e-106">You can avoid using fully qualified names by adding an `Imports` statement to the namespace declarations section of your code, as in the following example:</span></span>  
  
 [!code-vb[VbEnumsTask#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class1.vb#22)]  
  
 <span data-ttu-id="6256e-107">An `Imports` statement imports namespace names from referenced projects and assemblies and from within the same project as the module in which the statement appears.</span><span class="sxs-lookup"><span data-stu-id="6256e-107">An `Imports` statement imports namespace names from referenced projects and assemblies and from within the same project as the module in which the statement appears.</span></span> <span data-ttu-id="6256e-108">Once this statement is added, you can refer to your enumeration members without qualification, as in the following example:</span><span class="sxs-lookup"><span data-stu-id="6256e-108">Once this statement is added, you can refer to your enumeration members without qualification, as in the following example:</span></span>  
  
 [!code-vb[VbEnumsTask#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class1.vb#24)]  
  
 <span data-ttu-id="6256e-109">By organizing sets of related constants in enumerations, you can use the same constant names in different contexts.</span><span class="sxs-lookup"><span data-stu-id="6256e-109">By organizing sets of related constants in enumerations, you can use the same constant names in different contexts.</span></span> <span data-ttu-id="6256e-110">For example, you can use the same names for the weekday constants in the `Days` and `WorkDays` enumerations.</span><span class="sxs-lookup"><span data-stu-id="6256e-110">For example, you can use the same names for the weekday constants in the `Days` and `WorkDays` enumerations.</span></span> <span data-ttu-id="6256e-111">If you use the `Imports` statement with your enumerations, you must be careful to avoid ambiguous references.</span><span class="sxs-lookup"><span data-stu-id="6256e-111">If you use the `Imports` statement with your enumerations, you must be careful to avoid ambiguous references.</span></span> <span data-ttu-id="6256e-112">다음 예제를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6256e-112">Consider the following example:</span></span>  
  
 [!code-vb[VbEnumsTask#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class1.vb#22)]  
  
 [!code-vb[VbEnumsTask#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class1.vb#25)]  
  
 <span data-ttu-id="6256e-113">Assuming that `Monday` is a member of both the `Days` enumeration and the `Workdays` enumeration, this code generates a compiler error.</span><span class="sxs-lookup"><span data-stu-id="6256e-113">Assuming that `Monday` is a member of both the `Days` enumeration and the `Workdays` enumeration, this code generates a compiler error.</span></span> <span data-ttu-id="6256e-114">To avoid ambiguous references when referring to an individual constant, qualify the constant name with its enumeration.</span><span class="sxs-lookup"><span data-stu-id="6256e-114">To avoid ambiguous references when referring to an individual constant, qualify the constant name with its enumeration.</span></span> <span data-ttu-id="6256e-115">The following code refers to the `Saturday` constants in the `Days` and `WorkDays` enumerations.</span><span class="sxs-lookup"><span data-stu-id="6256e-115">The following code refers to the `Saturday` constants in the `Days` and `WorkDays` enumerations.</span></span>  
  
 [!code-vb[VbEnumsTask#32](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#32)]  
  
## <a name="see-also"></a><span data-ttu-id="6256e-116">참조</span><span class="sxs-lookup"><span data-stu-id="6256e-116">See also</span></span>

- [<span data-ttu-id="6256e-117">상수 및 열거형</span><span class="sxs-lookup"><span data-stu-id="6256e-117">Constants and Enumerations</span></span>](../../../../visual-basic/language-reference/constants-and-enumerations.md)
- [<span data-ttu-id="6256e-118">How to: Declare an Enumeration</span><span class="sxs-lookup"><span data-stu-id="6256e-118">How to: Declare an Enumeration</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)
- [<span data-ttu-id="6256e-119">방법: 열거형 멤버 참조</span><span class="sxs-lookup"><span data-stu-id="6256e-119">How to: Refer to an Enumeration Member</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)
- [<span data-ttu-id="6256e-120">How to: Iterate Through An Enumeration in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="6256e-120">How to: Iterate Through An Enumeration in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-iterate-through-an-enumeration.md)
- [<span data-ttu-id="6256e-121">방법: 열거형 값과 연결된 문자열 확인</span><span class="sxs-lookup"><span data-stu-id="6256e-121">How to: Determine the String Associated with an Enumeration Value</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-determine-the-string-associated-with-an-enumeration-value.md)
- [<span data-ttu-id="6256e-122">열거형을 사용하는 경우</span><span class="sxs-lookup"><span data-stu-id="6256e-122">When to Use an Enumeration</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/when-to-use-an-enumeration.md)
- [<span data-ttu-id="6256e-123">상수 및 리터럴 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="6256e-123">Constant and Literal Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/constant-and-literal-data-types.md)
- [<span data-ttu-id="6256e-124">Enum 문</span><span class="sxs-lookup"><span data-stu-id="6256e-124">Enum Statement</span></span>](../../../../visual-basic/language-reference/statements/enum-statement.md)
- [<span data-ttu-id="6256e-125">Imports 문(.NET 네임스페이스 및 형식)</span><span class="sxs-lookup"><span data-stu-id="6256e-125">Imports Statement (.NET Namespace and Type)</span></span>](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)
- [<span data-ttu-id="6256e-126">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="6256e-126">Data Types</span></span>](../../../../visual-basic/language-reference/data-types/index.md)
