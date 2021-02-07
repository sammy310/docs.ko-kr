---
description: '자세한 정보: GetType 연산자 (Visual Basic)'
title: GetType Operator
ms.date: 07/20/2015
f1_keywords:
- vb.GetType
helpviewer_keywords:
- GetType operator [Visual Basic]
- GetType keyword [Visual Basic]
ms.assetid: 4f733297-2503-4607-850c-15eba65fff90
ms.openlocfilehash: 15fe9c28997aa01527f23c0cc8fdbb0fe6cc53f7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99665993"
---
# <a name="gettype-operator-visual-basic"></a><span data-ttu-id="29da8-103">GetType 연산자(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="29da8-103">GetType Operator (Visual Basic)</span></span>

<span data-ttu-id="29da8-104">지정 된 <xref:System.Type> 형식에 대 한 개체를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="29da8-104">Returns a <xref:System.Type> object for the specified type.</span></span> <span data-ttu-id="29da8-105"><xref:System.Type>개체는 속성, 메서드 및 이벤트와 같은 형식에 대 한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="29da8-105">The <xref:System.Type> object provides information about the type such as its properties, methods, and events.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="29da8-106">구문</span><span class="sxs-lookup"><span data-stu-id="29da8-106">Syntax</span></span>  
  
```vb  
GetType(typename)  
```  
  
## <a name="parameters"></a><span data-ttu-id="29da8-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="29da8-107">Parameters</span></span>  
  
|<span data-ttu-id="29da8-108">매개 변수</span><span class="sxs-lookup"><span data-stu-id="29da8-108">Parameter</span></span>|<span data-ttu-id="29da8-109">설명</span><span class="sxs-lookup"><span data-stu-id="29da8-109">Description</span></span>|  
|---|---|  
|`typename`|<span data-ttu-id="29da8-110">정보를 원하는 형식의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="29da8-110">The name of the type for which you desire information.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="29da8-111">설명</span><span class="sxs-lookup"><span data-stu-id="29da8-111">Remarks</span></span>  

 <span data-ttu-id="29da8-112">`GetType`연산자는 지정 된 <xref:System.Type> 에 대 한 개체를 반환 합니다 `typename` .</span><span class="sxs-lookup"><span data-stu-id="29da8-112">The `GetType` operator returns the <xref:System.Type> object for the specified `typename`.</span></span> <span data-ttu-id="29da8-113">에서 정의 된 형식의 이름을 전달할 수 있습니다 `typename` .</span><span class="sxs-lookup"><span data-stu-id="29da8-113">You can pass the name of any defined type in `typename`.</span></span> <span data-ttu-id="29da8-114">여기에는 다음과 같은 사항이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="29da8-114">This includes the following:</span></span>  
  
- <span data-ttu-id="29da8-115">또는와 같은 모든 Visual Basic 데이터 형식 `Boolean` `Date` 입니다.</span><span class="sxs-lookup"><span data-stu-id="29da8-115">Any Visual Basic data type, such as `Boolean` or `Date`.</span></span>  
  
- <span data-ttu-id="29da8-116">또는와 같은 모든 .NET Framework 클래스, 구조체, 모듈 또는 인터페이스 <xref:System.ArgumentException?displayProperty=nameWithType> <xref:System.Double?displayProperty=nameWithType> 입니다.</span><span class="sxs-lookup"><span data-stu-id="29da8-116">Any .NET Framework class, structure, module, or interface, such as <xref:System.ArgumentException?displayProperty=nameWithType> or <xref:System.Double?displayProperty=nameWithType>.</span></span>  
  
- <span data-ttu-id="29da8-117">응용 프로그램에 정의 된 클래스, 구조체, 모듈 또는 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="29da8-117">Any class, structure, module, or interface defined by your application.</span></span>  
  
- <span data-ttu-id="29da8-118">응용 프로그램에서 정의 하는 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="29da8-118">Any array defined by your application.</span></span>  
  
- <span data-ttu-id="29da8-119">응용 프로그램에서 정의 하는 대리자입니다.</span><span class="sxs-lookup"><span data-stu-id="29da8-119">Any delegate defined by your application.</span></span>  
  
- <span data-ttu-id="29da8-120">Visual Basic, .NET Framework 또는 응용 프로그램에 의해 정의 되는 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="29da8-120">Any enumeration defined by Visual Basic, the .NET Framework, or your application.</span></span>  
  
 <span data-ttu-id="29da8-121">개체 변수의 형식 개체를 가져오려면 메서드를 사용 <xref:System.Type.GetType%2A?displayProperty=nameWithType> 합니다.</span><span class="sxs-lookup"><span data-stu-id="29da8-121">If you want to get the type object of an object variable, use the <xref:System.Type.GetType%2A?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="29da8-122">`GetType`연산자는 다음과 같은 경우에 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="29da8-122">The `GetType` operator can be useful in the following circumstances:</span></span>  
  
- <span data-ttu-id="29da8-123">런타임에 형식에 대 한 메타 데이터에 액세스 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="29da8-123">You must access the metadata for a type at run time.</span></span> <span data-ttu-id="29da8-124"><xref:System.Type>개체는 형식 멤버 및 배포 정보와 같은 메타 데이터를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="29da8-124">The <xref:System.Type> object supplies metadata such as type members and deployment information.</span></span> <span data-ttu-id="29da8-125">예를 들어, 어셈블리를 반영 하기 위해 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="29da8-125">You need this, for example, to reflect over an assembly.</span></span> <span data-ttu-id="29da8-126">자세한 내용은 <xref:System.Reflection?displayProperty=nameWithType>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="29da8-126">For more information, see <xref:System.Reflection?displayProperty=nameWithType>.</span></span>  
  
- <span data-ttu-id="29da8-127">두 개체 참조를 비교 하 여 동일한 형식의 인스턴스를 참조 하는지 여부를 확인 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="29da8-127">You want to compare two object references to see if they refer to instances of the same type.</span></span> <span data-ttu-id="29da8-128">이 경우는 `GetType` 동일한 개체에 대 한 참조를 반환 <xref:System.Type> 합니다.</span><span class="sxs-lookup"><span data-stu-id="29da8-128">If they do, `GetType` returns references to the same <xref:System.Type> object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="29da8-129">예제</span><span class="sxs-lookup"><span data-stu-id="29da8-129">Example</span></span>  

 <span data-ttu-id="29da8-130">다음 예에서는 `GetType` 사용 중인 연산자를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="29da8-130">The following examples show the `GetType` operator in use.</span></span>  
  
 [!code-vb[VbVbalrOperators#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#26)]  
  
## <a name="see-also"></a><span data-ttu-id="29da8-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="29da8-131">See also</span></span>

- [<span data-ttu-id="29da8-132">Visual Basic에서의 연산자 우선 순위</span><span class="sxs-lookup"><span data-stu-id="29da8-132">Operator Precedence in Visual Basic</span></span>](operator-precedence.md)
- [<span data-ttu-id="29da8-133">기능별 연산자 목록</span><span class="sxs-lookup"><span data-stu-id="29da8-133">Operators Listed by Functionality</span></span>](operators-listed-by-functionality.md)
- [<span data-ttu-id="29da8-134">연산자 및 식</span><span class="sxs-lookup"><span data-stu-id="29da8-134">Operators and Expressions</span></span>](../../programming-guide/language-features/operators-and-expressions/index.md)
