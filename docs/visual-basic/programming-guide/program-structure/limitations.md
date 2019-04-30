---
title: Visual Basic 제한 사항
ms.date: 07/20/2015
helpviewer_keywords:
- limits
- limitations [Visual Basic]
- limitations
- limits, Visual Basic code
- Visual Basic code, limitations
ms.assetid: cf1646b7-5d24-48c6-9616-bda8a4849d91
ms.openlocfilehash: 10f67c02d25ec275d1c3e98197d51c25aa250c19
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61955508"
---
# <a name="visual-basic-limitations"></a><span data-ttu-id="5cbaa-102">Visual Basic 제한 사항</span><span class="sxs-lookup"><span data-stu-id="5cbaa-102">Visual Basic Limitations</span></span>
<span data-ttu-id="5cbaa-103">이전 버전의 Visual Basic 코드에서 변수 이름, 모듈 및 모듈 크기에 허용 되는 변수의 수의 길이 같은 경계를 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="5cbaa-103">Earlier versions of Visual Basic enforced boundaries in code, such as the length of variable names, the number of variables allowed in modules, and module size.</span></span> <span data-ttu-id="5cbaa-104">Visual Basic.net에서는 이러한 제한은 완화 되었습니다, 큰 자유롭게 쓰고 정렬 코드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="5cbaa-104">In Visual Basic .NET, these restrictions have been relaxed, giving you greater freedom in writing and arranging your code.</span></span>  
  
 <span data-ttu-id="5cbaa-105">물리적 제한은 종속 런타임 메모리 보다 더 컴파일 시간 고려 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="5cbaa-105">Physical limits are dependent more on run-time memory than on compile-time considerations.</span></span> <span data-ttu-id="5cbaa-106">신중한 프로그래밍 사례를 사용 하 고 여러 클래스와 모듈 큰 응용 프로그램을 나누는 경우에 내부 Visual Basic 제한 사항이 발생할 확률이 거의 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5cbaa-106">If you use prudent programming practices, and divide large applications into multiple classes and modules, then there is very little chance of encountering an internal Visual Basic limitation.</span></span>  
  
 <span data-ttu-id="5cbaa-107">다음은 극단적인 경우에 발생할 수 있는 몇 가지 제한 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="5cbaa-107">The following are some limitations that you might encounter in extreme cases:</span></span>  
  
- <span data-ttu-id="5cbaa-108">**이름 길이입니다.**</span><span class="sxs-lookup"><span data-stu-id="5cbaa-108">**Name Length.**</span></span> <span data-ttu-id="5cbaa-109">모든 선언 된 프로그래밍 요소의 이름에 대 한 문자의 최대 수가입니다.</span><span class="sxs-lookup"><span data-stu-id="5cbaa-109">There is a maximum number of characters for the name of every declared programming element.</span></span> <span data-ttu-id="5cbaa-110">이 최대 요소 이름이 정규화 된 경우 전체 한정 문자열에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5cbaa-110">This maximum applies to an entire qualification string if the element name is qualified.</span></span> <span data-ttu-id="5cbaa-111">[Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5cbaa-111">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>  
  
- <span data-ttu-id="5cbaa-112">**Line Length.**</span><span class="sxs-lookup"><span data-stu-id="5cbaa-112">**Line Length.**</span></span> <span data-ttu-id="5cbaa-113">실제 소스 코드 줄에서 65535 자가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5cbaa-113">There is a maximum of 65535 characters in a physical line of source code.</span></span> <span data-ttu-id="5cbaa-114">논리 소스 코드 줄은 줄 연속 문자를 사용 하는 경우에 길어질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5cbaa-114">The logical source code line can be longer if you use line continuation characters.</span></span> <span data-ttu-id="5cbaa-115">[방법: 코드에서 문 분리 및 결합](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="5cbaa-115">See [How to: Break and Combine Statements in Code](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md).</span></span>  
  
- <span data-ttu-id="5cbaa-116">**배열 차원이 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="5cbaa-116">**Array Dimensions.**</span></span> <span data-ttu-id="5cbaa-117">배열에 선언할 수 있는 차원의 최대 수가입니다.</span><span class="sxs-lookup"><span data-stu-id="5cbaa-117">There is a maximum number of dimensions you can declare for an array.</span></span> <span data-ttu-id="5cbaa-118">이 배열 요소를 지정 하 여 인덱스 수를 제한 합니다.</span><span class="sxs-lookup"><span data-stu-id="5cbaa-118">This limits how many indexes you can use to specify an array element.</span></span> <span data-ttu-id="5cbaa-119">참조 [Array Dimensions in Visual Basic](../../../visual-basic/programming-guide/language-features/arrays/array-dimensions.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="5cbaa-119">See [Array Dimensions in Visual Basic](../../../visual-basic/programming-guide/language-features/arrays/array-dimensions.md).</span></span>  
  
- <span data-ttu-id="5cbaa-120">**문자열 길이입니다.**</span><span class="sxs-lookup"><span data-stu-id="5cbaa-120">**String Length.**</span></span> <span data-ttu-id="5cbaa-121">단일 문자열에 저장할 수 있습니다 하는 유니코드 문자의 최대 수가입니다.</span><span class="sxs-lookup"><span data-stu-id="5cbaa-121">There is a maximum number of Unicode characters you can store in a single string.</span></span> <span data-ttu-id="5cbaa-122">참조 [문자열 데이터 형식](../../../visual-basic/language-reference/data-types/string-data-type.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="5cbaa-122">See [String Data Type](../../../visual-basic/language-reference/data-types/string-data-type.md).</span></span>  
  
- <span data-ttu-id="5cbaa-123">**환경 문자열 길이입니다.**</span><span class="sxs-lookup"><span data-stu-id="5cbaa-123">**Environment String Length.**</span></span> <span data-ttu-id="5cbaa-124">명령줄 인수를 받았던 환경 문자열의 32768 자의 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5cbaa-124">There is a maximum of 32768 characters for any environment string used as a command-line argument.</span></span> <span data-ttu-id="5cbaa-125">모든 플랫폼에서 제한 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5cbaa-125">This is a limitation on all platforms.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5cbaa-126">참고자료</span><span class="sxs-lookup"><span data-stu-id="5cbaa-126">See also</span></span>

- [<span data-ttu-id="5cbaa-127">프로그램 구조 및 코드 규칙</span><span class="sxs-lookup"><span data-stu-id="5cbaa-127">Program Structure and Code Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)
- [<span data-ttu-id="5cbaa-128">Visual Basic 명명 규칙</span><span class="sxs-lookup"><span data-stu-id="5cbaa-128">Visual Basic Naming Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)
