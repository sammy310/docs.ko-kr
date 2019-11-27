---
title: GetType Operator
ms.date: 07/20/2015
f1_keywords:
- vb.GetType
helpviewer_keywords:
- GetType operator [Visual Basic]
- GetType keyword [Visual Basic]
ms.assetid: 4f733297-2503-4607-850c-15eba65fff90
ms.openlocfilehash: 4e59bcfaa24c9545ed75c6b5c1d29cad398ac2de
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349546"
---
# <a name="gettype-operator-visual-basic"></a><span data-ttu-id="7908c-102">GetType 연산자(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7908c-102">GetType Operator (Visual Basic)</span></span>
<span data-ttu-id="7908c-103">지정 된 형식에 대 한 <xref:System.Type> 개체를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="7908c-103">Returns a <xref:System.Type> object for the specified type.</span></span> <span data-ttu-id="7908c-104"><xref:System.Type> 개체는 속성, 메서드 및 이벤트와 같은 형식에 대 한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="7908c-104">The <xref:System.Type> object provides information about the type such as its properties, methods, and events.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7908c-105">구문</span><span class="sxs-lookup"><span data-stu-id="7908c-105">Syntax</span></span>  
  
```vb  
GetType(typename)  
```  
  
## <a name="parameters"></a><span data-ttu-id="7908c-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="7908c-106">Parameters</span></span>  
  
|<span data-ttu-id="7908c-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="7908c-107">Parameter</span></span>|<span data-ttu-id="7908c-108">설명</span><span class="sxs-lookup"><span data-stu-id="7908c-108">Description</span></span>|  
|---|---|  
|`typename`|<span data-ttu-id="7908c-109">정보를 원하는 형식의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="7908c-109">The name of the type for which you desire information.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7908c-110">설명</span><span class="sxs-lookup"><span data-stu-id="7908c-110">Remarks</span></span>  
 <span data-ttu-id="7908c-111">`GetType` 연산자는 지정 된 `typename`에 대 한 <xref:System.Type> 개체를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="7908c-111">The `GetType` operator returns the <xref:System.Type> object for the specified `typename`.</span></span> <span data-ttu-id="7908c-112">`typename`에서 정의 된 형식의 이름을 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7908c-112">You can pass the name of any defined type in `typename`.</span></span> <span data-ttu-id="7908c-113">여기에는 다음이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="7908c-113">This includes the following:</span></span>  
  
- <span data-ttu-id="7908c-114">`Boolean` 또는 `Date`와 같은 Visual Basic 데이터 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="7908c-114">Any Visual Basic data type, such as `Boolean` or `Date`.</span></span>  
  
- <span data-ttu-id="7908c-115"><xref:System.ArgumentException?displayProperty=nameWithType> 또는 <xref:System.Double?displayProperty=nameWithType>와 같은 .NET Framework 클래스, 구조체, 모듈 또는 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="7908c-115">Any .NET Framework class, structure, module, or interface, such as <xref:System.ArgumentException?displayProperty=nameWithType> or <xref:System.Double?displayProperty=nameWithType>.</span></span>  
  
- <span data-ttu-id="7908c-116">응용 프로그램에 정의 된 클래스, 구조체, 모듈 또는 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="7908c-116">Any class, structure, module, or interface defined by your application.</span></span>  
  
- <span data-ttu-id="7908c-117">응용 프로그램에서 정의 하는 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="7908c-117">Any array defined by your application.</span></span>  
  
- <span data-ttu-id="7908c-118">응용 프로그램에서 정의 하는 대리자입니다.</span><span class="sxs-lookup"><span data-stu-id="7908c-118">Any delegate defined by your application.</span></span>  
  
- <span data-ttu-id="7908c-119">Visual Basic, .NET Framework 또는 응용 프로그램에 의해 정의 되는 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="7908c-119">Any enumeration defined by Visual Basic, the .NET Framework, or your application.</span></span>  
  
 <span data-ttu-id="7908c-120">개체 변수의 형식 개체를 가져오려는 경우 <xref:System.Type.GetType%2A?displayProperty=nameWithType> 메서드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="7908c-120">If you want to get the type object of an object variable, use the <xref:System.Type.GetType%2A?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="7908c-121">`GetType` 연산자는 다음과 같은 경우에 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7908c-121">The `GetType` operator can be useful in the following circumstances:</span></span>  
  
- <span data-ttu-id="7908c-122">런타임에 형식에 대 한 메타 데이터에 액세스 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7908c-122">You must access the metadata for a type at run time.</span></span> <span data-ttu-id="7908c-123"><xref:System.Type> 개체는 형식 멤버 및 배포 정보와 같은 메타 데이터를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="7908c-123">The <xref:System.Type> object supplies metadata such as type members and deployment information.</span></span> <span data-ttu-id="7908c-124">예를 들어, 어셈블리를 반영 하기 위해 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="7908c-124">You need this, for example, to reflect over an assembly.</span></span> <span data-ttu-id="7908c-125">자세한 내용은 <xref:System.Reflection?displayProperty=nameWithType>을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7908c-125">For more information, see <xref:System.Reflection?displayProperty=nameWithType>.</span></span>  
  
- <span data-ttu-id="7908c-126">두 개체 참조를 비교 하 여 동일한 형식의 인스턴스를 참조 하는지 여부를 확인 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="7908c-126">You want to compare two object references to see if they refer to instances of the same type.</span></span> <span data-ttu-id="7908c-127">이 경우 `GetType`는 동일한 <xref:System.Type> 개체에 대 한 참조를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="7908c-127">If they do, `GetType` returns references to the same <xref:System.Type> object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7908c-128">예제</span><span class="sxs-lookup"><span data-stu-id="7908c-128">Example</span></span>  
 <span data-ttu-id="7908c-129">다음 예에서는 `GetType` 연산자를 사용 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7908c-129">The following examples show the `GetType` operator in use.</span></span>  
  
 [!code-vb[VbVbalrOperators#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#26)]  
  
## <a name="see-also"></a><span data-ttu-id="7908c-130">참고자료</span><span class="sxs-lookup"><span data-stu-id="7908c-130">See also</span></span>

- [<span data-ttu-id="7908c-131">Visual Basic에서의 연산자 우선 순위</span><span class="sxs-lookup"><span data-stu-id="7908c-131">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="7908c-132">기능별 연산자 목록</span><span class="sxs-lookup"><span data-stu-id="7908c-132">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="7908c-133">연산자 및 식</span><span class="sxs-lookup"><span data-stu-id="7908c-133">Operators and Expressions</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
