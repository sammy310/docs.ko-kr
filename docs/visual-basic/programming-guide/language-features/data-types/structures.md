---
title: 구조
ms.date: 07/20/2015
helpviewer_keywords:
- structures [Visual Basic]
- user-defined data types [Visual Basic], structures
- user-defined types [Visual Basic], about user-defined types
- data types [Visual Basic], user-defined
- user-defined data types [Visual Basic], about user-defined data types
- types [Visual Basic], user-defined
ms.assetid: 55e86462-5e99-4d33-8018-6d097ca491b2
ms.openlocfilehash: b5f1f8d6d783c6612fdb2bd2058b61a5a46024cc
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350770"
---
# <a name="structures-visual-basic"></a><span data-ttu-id="e0acd-102">구조체(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e0acd-102">Structures (Visual Basic)</span></span>
<span data-ttu-id="e0acd-103">*구조* 는 이전 버전의 Visual Basic에서 지원 되는 UDT (사용자 정의 형식)를 일반화 한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="e0acd-103">A *structure* is a generalization of the user-defined type (UDT) supported by previous versions of Visual Basic.</span></span> <span data-ttu-id="e0acd-104">필드 외에도 구조는 속성, 메서드 및 이벤트를 노출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0acd-104">In addition to fields, structures can expose properties, methods, and events.</span></span> <span data-ttu-id="e0acd-105">구조체는 하나 이상의 인터페이스를 구현할 수 있으며 각 필드에 대해 개별 액세스 수준을 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0acd-105">A structure can implement one or more interfaces, and you can declare individual access levels for each field.</span></span>  
  
 <span data-ttu-id="e0acd-106">서로 다른 형식의 데이터 항목을 결합 하 여 구조체를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0acd-106">You can combine data items of different types to create a structure.</span></span> <span data-ttu-id="e0acd-107">구조체는 하나 이상의 *요소* 를 서로 연결 하 고 구조체 자체와 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0acd-107">A structure associates one or more *elements* with each other and with the structure itself.</span></span> <span data-ttu-id="e0acd-108">구조체를 선언 하면 *복합 데이터 형식이*되며 해당 형식의 변수를 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0acd-108">When you declare a structure, it becomes a *composite data type*, and you can declare variables of that type.</span></span>  
  
 <span data-ttu-id="e0acd-109">구조체는 단일 변수가 여러 관련 정보를 포함 하도록 하려는 경우에 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0acd-109">Structures are useful when you want a single variable to hold several related pieces of information.</span></span> <span data-ttu-id="e0acd-110">예를 들어 직원의 이름, 전화 내선 번호 및 급여를 함께 유지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0acd-110">For example, you might want to keep an employee's name, telephone extension, and salary together.</span></span> <span data-ttu-id="e0acd-111">이 정보에 여러 변수를 사용할 수도 있고, 구조를 정의 하 고 단일 직원 변수에 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0acd-111">You could use several variables for this information, or you could define a structure and use it for a single employee variable.</span></span> <span data-ttu-id="e0acd-112">직원 수가 많고 변수의 인스턴스가 많은 경우 구조의 이점이 분명 하 게 드러납니다.</span><span class="sxs-lookup"><span data-stu-id="e0acd-112">The advantage of the structure becomes apparent when you have many employees and therefore many instances of the variable.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e0acd-113">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="e0acd-113">In This Section</span></span>  
 [<span data-ttu-id="e0acd-114">방법: 구조체 선언</span><span class="sxs-lookup"><span data-stu-id="e0acd-114">How to: Declare a Structure</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)  
 <span data-ttu-id="e0acd-115">구조체와 해당 요소를 선언 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e0acd-115">Shows how to declare a structure and its elements.</span></span>  
  
 [<span data-ttu-id="e0acd-116">구조체 변수</span><span class="sxs-lookup"><span data-stu-id="e0acd-116">Structure Variables</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structure-variables.md)  
 <span data-ttu-id="e0acd-117">구조체를 변수에 할당 하 고 해당 요소에 액세스 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0acd-117">Covers assigning a structure to a variable and accessing its elements.</span></span>  
  
 [<span data-ttu-id="e0acd-118">구조체 및 기타 프로그래밍 요소</span><span class="sxs-lookup"><span data-stu-id="e0acd-118">Structures and Other Programming Elements</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-other-programming-elements.md)  
 <span data-ttu-id="e0acd-119">구조체가 배열, 개체, 프로시저 및 상호 작용 하는 방법을 요약 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0acd-119">Summarizes how structures interact with arrays, objects, procedures, and each other.</span></span>  
  
 [<span data-ttu-id="e0acd-120">구조체와 클래스</span><span class="sxs-lookup"><span data-stu-id="e0acd-120">Structures and Classes</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md)  
 <span data-ttu-id="e0acd-121">구조체와 클래스 간의 유사성 및 차이점을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0acd-121">Describes the similarities and differences between structures and classes.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="e0acd-122">관련 단원</span><span class="sxs-lookup"><span data-stu-id="e0acd-122">Related Sections</span></span>  
 [<span data-ttu-id="e0acd-123">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="e0acd-123">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)  
 <span data-ttu-id="e0acd-124">Visual Basic 데이터 형식을 소개 하 고이를 사용 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0acd-124">Introduces the Visual Basic data types and describes how to use them.</span></span>  
  
 [<span data-ttu-id="e0acd-125">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="e0acd-125">Data Types</span></span>](../../../../visual-basic/language-reference/data-types/index.md)  
 <span data-ttu-id="e0acd-126">Visual Basic에서 제공 하는 기본 데이터 형식을 나열 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0acd-126">Lists the elementary data types supplied by Visual Basic.</span></span>
