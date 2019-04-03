---
title: GetType 연산자(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.GetType
helpviewer_keywords:
- GetType operator [Visual Basic]
- GetType keyword [Visual Basic]
ms.assetid: 4f733297-2503-4607-850c-15eba65fff90
ms.openlocfilehash: 34ab192814583db5cdc0d0183c73cc22b8633e9c
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58840323"
---
# <a name="gettype-operator-visual-basic"></a><span data-ttu-id="9ca09-102">GetType 연산자(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9ca09-102">GetType Operator (Visual Basic)</span></span>
<span data-ttu-id="9ca09-103">반환 된 <xref:System.Type> 지정 된 형식의 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="9ca09-103">Returns a <xref:System.Type> object for the specified type.</span></span> <span data-ttu-id="9ca09-104"><xref:System.Type> 개체는 해당 속성, 메서드 및 이벤트와 같은 유형에 대 한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ca09-104">The <xref:System.Type> object provides information about the type such as its properties, methods, and events.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9ca09-105">구문</span><span class="sxs-lookup"><span data-stu-id="9ca09-105">Syntax</span></span>  
  
```  
GetType(typename)  
```  
  
## <a name="parameters"></a><span data-ttu-id="9ca09-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="9ca09-106">Parameters</span></span>  
  
|<span data-ttu-id="9ca09-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="9ca09-107">Parameter</span></span>|<span data-ttu-id="9ca09-108">설명</span><span class="sxs-lookup"><span data-stu-id="9ca09-108">Description</span></span>|  
|---|---|  
|`typename`|<span data-ttu-id="9ca09-109">이름 정보를 원하는 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="9ca09-109">The name of the type for which you desire information.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9ca09-110">설명</span><span class="sxs-lookup"><span data-stu-id="9ca09-110">Remarks</span></span>  
 <span data-ttu-id="9ca09-111">합니다 `GetType` 연산자를 반환 합니다 <xref:System.Type> 지정 된 개체 `typename`합니다.</span><span class="sxs-lookup"><span data-stu-id="9ca09-111">The `GetType` operator returns the <xref:System.Type> object for the specified `typename`.</span></span> <span data-ttu-id="9ca09-112">에 정의 된 형식의 이름을 전달할 수 있습니다 `typename`합니다.</span><span class="sxs-lookup"><span data-stu-id="9ca09-112">You can pass the name of any defined type in `typename`.</span></span> <span data-ttu-id="9ca09-113">여기에는 다음과 같은 사항이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="9ca09-113">This includes the following:</span></span>  
  
-   <span data-ttu-id="9ca09-114">와 같은 모든 Visual Basic 데이터 형식 `Boolean` 또는 `Date`합니다.</span><span class="sxs-lookup"><span data-stu-id="9ca09-114">Any Visual Basic data type, such as `Boolean` or `Date`.</span></span>  
  
-   <span data-ttu-id="9ca09-115">모든.NET Framework 클래스, 구조체, 모듈 또는 인터페이스와 같은 <xref:System.ArgumentException?displayProperty=nameWithType> 또는 <xref:System.Double?displayProperty=nameWithType>합니다.</span><span class="sxs-lookup"><span data-stu-id="9ca09-115">Any .NET Framework class, structure, module, or interface, such as <xref:System.ArgumentException?displayProperty=nameWithType> or <xref:System.Double?displayProperty=nameWithType>.</span></span>  
  
-   <span data-ttu-id="9ca09-116">모든 클래스, 구조체, 모듈 또는 응용 프로그램에서 정의 된 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="9ca09-116">Any class, structure, module, or interface defined by your application.</span></span>  
  
-   <span data-ttu-id="9ca09-117">응용 프로그램에서 정의한 모든 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="9ca09-117">Any array defined by your application.</span></span>  
  
-   <span data-ttu-id="9ca09-118">응용 프로그램에서 정의한 모든 대리자입니다.</span><span class="sxs-lookup"><span data-stu-id="9ca09-118">Any delegate defined by your application.</span></span>  
  
-   <span data-ttu-id="9ca09-119">Visual Basic,.NET Framework 또는 응용 프로그램에 정의 된 모든 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="9ca09-119">Any enumeration defined by Visual Basic, the .NET Framework, or your application.</span></span>  
  
 <span data-ttu-id="9ca09-120">개체 변수의 형식 개체를 가져오려는 경우 사용 된 <xref:System.Type.GetType%2A?displayProperty=nameWithType> 메서드.</span><span class="sxs-lookup"><span data-stu-id="9ca09-120">If you want to get the type object of an object variable, use the <xref:System.Type.GetType%2A?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="9ca09-121">`GetType` 연산자는 다음과 같은 경우에 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ca09-121">The `GetType` operator can be useful in the following circumstances:</span></span>  
  
-   <span data-ttu-id="9ca09-122">런타임 시 형식에 대 한 메타 데이터에 액세스 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ca09-122">You must access the metadata for a type at run time.</span></span> <span data-ttu-id="9ca09-123"><xref:System.Type> 개체 형식 멤버 및 배포 정보 같은 메타 데이터를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ca09-123">The <xref:System.Type> object supplies metadata such as type members and deployment information.</span></span> <span data-ttu-id="9ca09-124">해야이 예를 들어, 어셈블리를 반영 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ca09-124">You need this, for example, to reflect over an assembly.</span></span> <span data-ttu-id="9ca09-125">자세한 내용은 <xref:System.Reflection?displayProperty=nameWithType>을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9ca09-125">For more information, see <xref:System.Reflection?displayProperty=nameWithType>.</span></span>  
  
-   <span data-ttu-id="9ca09-126">두 개체 참조는 동일한 형식의 인스턴스를 참조 하는 경우를 비교 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ca09-126">You want to compare two object references to see if they refer to instances of the same type.</span></span> <span data-ttu-id="9ca09-127">이렇게 되 면 `GetType` 동일에 대 한 참조를 반환 합니다. <xref:System.Type> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="9ca09-127">If they do, `GetType` returns references to the same <xref:System.Type> object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9ca09-128">예제</span><span class="sxs-lookup"><span data-stu-id="9ca09-128">Example</span></span>  
 <span data-ttu-id="9ca09-129">다음 예제에 나온은 `GetType` 연산자를 사용에서 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ca09-129">The following examples show the `GetType` operator in use.</span></span>  
  
 [!code-vb[VbVbalrOperators#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#26)]  
  
## <a name="see-also"></a><span data-ttu-id="9ca09-130">참고자료</span><span class="sxs-lookup"><span data-stu-id="9ca09-130">See also</span></span>

- [<span data-ttu-id="9ca09-131">Visual Basic에서의 연산자 우선 순위</span><span class="sxs-lookup"><span data-stu-id="9ca09-131">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="9ca09-132">기능별 연산자 목록</span><span class="sxs-lookup"><span data-stu-id="9ca09-132">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="9ca09-133">연산자 및 식</span><span class="sxs-lookup"><span data-stu-id="9ca09-133">Operators and Expressions</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
