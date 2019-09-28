---
title: GetType 연산자(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.GetType
helpviewer_keywords:
- GetType operator [Visual Basic]
- GetType keyword [Visual Basic]
ms.assetid: 4f733297-2503-4607-850c-15eba65fff90
ms.openlocfilehash: 2e3e05973f2ef72fef5e429bc98cc58b4b21f2c2
ms.sourcegitcommit: 35da8fb45b4cca4e59cc99a5c56262c356977159
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/28/2019
ms.locfileid: "71592147"
---
# <a name="gettype-operator-visual-basic"></a><span data-ttu-id="4445a-102">GetType 연산자(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4445a-102">GetType Operator (Visual Basic)</span></span>
<span data-ttu-id="4445a-103">지정 된 형식에 대 한 <xref:System.Type> 개체를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="4445a-103">Returns a <xref:System.Type> object for the specified type.</span></span> <span data-ttu-id="4445a-104">@No__t-0 개체는 속성, 메서드 및 이벤트와 같은 형식에 대 한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="4445a-104">The <xref:System.Type> object provides information about the type such as its properties, methods, and events.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4445a-105">구문</span><span class="sxs-lookup"><span data-stu-id="4445a-105">Syntax</span></span>  
  
```vb  
GetType(typename)  
```  
  
## <a name="parameters"></a><span data-ttu-id="4445a-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="4445a-106">Parameters</span></span>  
  
|<span data-ttu-id="4445a-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="4445a-107">Parameter</span></span>|<span data-ttu-id="4445a-108">설명</span><span class="sxs-lookup"><span data-stu-id="4445a-108">Description</span></span>|  
|---|---|  
|`typename`|<span data-ttu-id="4445a-109">정보를 원하는 형식의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="4445a-109">The name of the type for which you desire information.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4445a-110">설명</span><span class="sxs-lookup"><span data-stu-id="4445a-110">Remarks</span></span>  
 <span data-ttu-id="4445a-111">@No__t-0 연산자는 지정 된 `typename`에 대 한 <xref:System.Type> 개체를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="4445a-111">The `GetType` operator returns the <xref:System.Type> object for the specified `typename`.</span></span> <span data-ttu-id="4445a-112">@No__t-0에서 정의 된 형식의 이름을 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4445a-112">You can pass the name of any defined type in `typename`.</span></span> <span data-ttu-id="4445a-113">여기에는 다음이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="4445a-113">This includes the following:</span></span>  
  
- <span data-ttu-id="4445a-114">@No__t-0 또는 `Date`과 같은 Visual Basic 데이터 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="4445a-114">Any Visual Basic data type, such as `Boolean` or `Date`.</span></span>  
  
- <span data-ttu-id="4445a-115">@No__t-0 또는 <xref:System.Double?displayProperty=nameWithType>과 같은 .NET Framework 클래스, 구조체, 모듈 또는 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="4445a-115">Any .NET Framework class, structure, module, or interface, such as <xref:System.ArgumentException?displayProperty=nameWithType> or <xref:System.Double?displayProperty=nameWithType>.</span></span>  
  
- <span data-ttu-id="4445a-116">응용 프로그램에 정의 된 클래스, 구조체, 모듈 또는 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="4445a-116">Any class, structure, module, or interface defined by your application.</span></span>  
  
- <span data-ttu-id="4445a-117">응용 프로그램에서 정의 하는 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="4445a-117">Any array defined by your application.</span></span>  
  
- <span data-ttu-id="4445a-118">응용 프로그램에서 정의 하는 대리자입니다.</span><span class="sxs-lookup"><span data-stu-id="4445a-118">Any delegate defined by your application.</span></span>  
  
- <span data-ttu-id="4445a-119">Visual Basic, .NET Framework 또는 응용 프로그램에 의해 정의 되는 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="4445a-119">Any enumeration defined by Visual Basic, the .NET Framework, or your application.</span></span>  
  
 <span data-ttu-id="4445a-120">개체 변수의 형식 개체를 가져오려는 경우 <xref:System.Type.GetType%2A?displayProperty=nameWithType> 메서드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4445a-120">If you want to get the type object of an object variable, use the <xref:System.Type.GetType%2A?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="4445a-121">@No__t-0 연산자는 다음과 같은 경우에 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4445a-121">The `GetType` operator can be useful in the following circumstances:</span></span>  
  
- <span data-ttu-id="4445a-122">런타임에 형식에 대 한 메타 데이터에 액세스 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4445a-122">You must access the metadata for a type at run time.</span></span> <span data-ttu-id="4445a-123">@No__t-0 개체는 형식 멤버 및 배포 정보와 같은 메타 데이터를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="4445a-123">The <xref:System.Type> object supplies metadata such as type members and deployment information.</span></span> <span data-ttu-id="4445a-124">예를 들어, 어셈블리를 반영 하기 위해 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="4445a-124">You need this, for example, to reflect over an assembly.</span></span> <span data-ttu-id="4445a-125">자세한 내용은 <xref:System.Reflection?displayProperty=nameWithType>을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4445a-125">For more information, see <xref:System.Reflection?displayProperty=nameWithType>.</span></span>  
  
- <span data-ttu-id="4445a-126">두 개체 참조를 비교 하 여 동일한 형식의 인스턴스를 참조 하는지 여부를 확인 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="4445a-126">You want to compare two object references to see if they refer to instances of the same type.</span></span> <span data-ttu-id="4445a-127">이 경우 `GetType`은 동일한 <xref:System.Type> 개체에 대 한 참조를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="4445a-127">If they do, `GetType` returns references to the same <xref:System.Type> object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4445a-128">예제</span><span class="sxs-lookup"><span data-stu-id="4445a-128">Example</span></span>  
 <span data-ttu-id="4445a-129">다음 예에서는 `GetType` 연산자를 사용 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4445a-129">The following examples show the `GetType` operator in use.</span></span>  
  
 [!code-vb[VbVbalrOperators#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#26)]  
  
## <a name="see-also"></a><span data-ttu-id="4445a-130">참조</span><span class="sxs-lookup"><span data-stu-id="4445a-130">See also</span></span>

- [<span data-ttu-id="4445a-131">Visual Basic에서의 연산자 우선 순위</span><span class="sxs-lookup"><span data-stu-id="4445a-131">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="4445a-132">기능별 연산자 목록</span><span class="sxs-lookup"><span data-stu-id="4445a-132">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="4445a-133">연산자 및 식</span><span class="sxs-lookup"><span data-stu-id="4445a-133">Operators and Expressions</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
