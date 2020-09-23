---
title: 제한 사항
ms.date: 07/20/2015
helpviewer_keywords:
- limits
- limitations [Visual Basic]
- limitations
- limits, Visual Basic code
- Visual Basic code, limitations
ms.assetid: cf1646b7-5d24-48c6-9616-bda8a4849d91
ms.openlocfilehash: abe4acd5850aa6065bf4f6fd41bc610ede7ad13f
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2020
ms.locfileid: "91097958"
---
# <a name="visual-basic-limitations"></a><span data-ttu-id="b046e-102">Visual Basic 제한 사항</span><span class="sxs-lookup"><span data-stu-id="b046e-102">Visual Basic Limitations</span></span>

<span data-ttu-id="b046e-103">이전 버전의에서는 변수 이름 길이, 모듈에서 허용 되는 변수 수 및 모듈 크기와 같이 코드에서 경계를 적용 Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="b046e-103">Earlier versions of Visual Basic enforced boundaries in code, such as the length of variable names, the number of variables allowed in modules, and module size.</span></span> <span data-ttu-id="b046e-104">Visual Basic .NET에서는 이러한 제한이 완화 되어 코드를 작성 하 고 정렬 하는 데 더 많은 자유를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b046e-104">In Visual Basic .NET, these restrictions have been relaxed, giving you greater freedom in writing and arranging your code.</span></span>  
  
 <span data-ttu-id="b046e-105">실제 제한은 컴파일 시간 고려 사항 보다 런타임 메모리에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="b046e-105">Physical limits are dependent more on run-time memory than on compile-time considerations.</span></span> <span data-ttu-id="b046e-106">신중한 프로그래밍 관행을 사용 하 고 큰 응용 프로그램을 여러 클래스 및 모듈로 나누는 경우 내부 Visual Basic 제한이 발생할 가능성이 거의 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b046e-106">If you use prudent programming practices, and divide large applications into multiple classes and modules, then there is very little chance of encountering an internal Visual Basic limitation.</span></span>  
  
 <span data-ttu-id="b046e-107">극단적인 경우에 발생할 수 있는 몇 가지 제한 사항은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b046e-107">The following are some limitations that you might encounter in extreme cases:</span></span>  
  
- <span data-ttu-id="b046e-108">**이름 길이입니다.**</span><span class="sxs-lookup"><span data-stu-id="b046e-108">**Name Length.**</span></span> <span data-ttu-id="b046e-109">선언 된 모든 프로그래밍 요소의 이름에는 최대 자까지 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b046e-109">There is a maximum number of characters for the name of every declared programming element.</span></span> <span data-ttu-id="b046e-110">이 최대값은 요소 이름이 정규화 된 경우 전체 정규화 문자열에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b046e-110">This maximum applies to an entire qualification string if the element name is qualified.</span></span> <span data-ttu-id="b046e-111">[Declared Element Names](../language-features/declared-elements/declared-element-names.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b046e-111">See [Declared Element Names](../language-features/declared-elements/declared-element-names.md).</span></span>  
  
- <span data-ttu-id="b046e-112">**줄 길이입니다.**</span><span class="sxs-lookup"><span data-stu-id="b046e-112">**Line Length.**</span></span> <span data-ttu-id="b046e-113">소스 코드의 물리적 줄에는 최대 65535 자까지 입력할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b046e-113">There is a maximum of 65535 characters in a physical line of source code.</span></span> <span data-ttu-id="b046e-114">줄 연속 문자를 사용 하는 경우 논리적 소스 코드 줄이 더 길어질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b046e-114">The logical source code line can be longer if you use line continuation characters.</span></span> <span data-ttu-id="b046e-115">[방법: 코드에서 문 분리 및 결합을](how-to-break-and-combine-statements-in-code.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b046e-115">See [How to: Break and Combine Statements in Code](how-to-break-and-combine-statements-in-code.md).</span></span>  
  
- <span data-ttu-id="b046e-116">**배열 차원입니다.**</span><span class="sxs-lookup"><span data-stu-id="b046e-116">**Array Dimensions.**</span></span> <span data-ttu-id="b046e-117">배열에 대해 선언할 수 있는 차원의 최대 수가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b046e-117">There is a maximum number of dimensions you can declare for an array.</span></span> <span data-ttu-id="b046e-118">이는 배열 요소를 지정 하는 데 사용할 수 있는 인덱스 수를 제한 합니다.</span><span class="sxs-lookup"><span data-stu-id="b046e-118">This limits how many indexes you can use to specify an array element.</span></span> <span data-ttu-id="b046e-119">[Visual Basic에서 배열 차원을](../language-features/arrays/array-dimensions.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b046e-119">See [Array Dimensions in Visual Basic](../language-features/arrays/array-dimensions.md).</span></span>  
  
- <span data-ttu-id="b046e-120">**문자열 길이입니다.**</span><span class="sxs-lookup"><span data-stu-id="b046e-120">**String Length.**</span></span> <span data-ttu-id="b046e-121">단일 문자열에 저장할 수 있는 최대 유니코드 문자 수가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b046e-121">There is a maximum number of Unicode characters you can store in a single string.</span></span> <span data-ttu-id="b046e-122">[문자열 데이터 형식](../../language-reference/data-types/string-data-type.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b046e-122">See [String Data Type](../../language-reference/data-types/string-data-type.md).</span></span>  
  
- <span data-ttu-id="b046e-123">**환경 문자열 길이입니다.**</span><span class="sxs-lookup"><span data-stu-id="b046e-123">**Environment String Length.**</span></span> <span data-ttu-id="b046e-124">명령줄 인수로 사용 되는 환경 문자열에는 최대 32768 자까지 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b046e-124">There is a maximum of 32768 characters for any environment string used as a command-line argument.</span></span> <span data-ttu-id="b046e-125">이는 모든 플랫폼에 대 한 제한 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="b046e-125">This is a limitation on all platforms.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b046e-126">참조</span><span class="sxs-lookup"><span data-stu-id="b046e-126">See also</span></span>

- [<span data-ttu-id="b046e-127">프로그램 구조 및 코드 규칙</span><span class="sxs-lookup"><span data-stu-id="b046e-127">Program Structure and Code Conventions</span></span>](program-structure-and-code-conventions.md)
- [<span data-ttu-id="b046e-128">Visual Basic 명명 규칙</span><span class="sxs-lookup"><span data-stu-id="b046e-128">Visual Basic Naming Conventions</span></span>](naming-conventions.md)
