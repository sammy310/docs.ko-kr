---
title: GetType Operator
ms.date: 07/20/2015
f1_keywords:
- vb.GetType
helpviewer_keywords:
- GetType operator [Visual Basic]
- GetType keyword [Visual Basic]
ms.assetid: 4f733297-2503-4607-850c-15eba65fff90
ms.openlocfilehash: 9ff207ea4f2b89ea30eb8f46a3e640ccf3789974
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "90867015"
---
# <a name="gettype-operator-visual-basic"></a><span data-ttu-id="0897d-102">GetType 연산자(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0897d-102">GetType Operator (Visual Basic)</span></span>

<span data-ttu-id="0897d-103">지정 된 <xref:System.Type> 형식에 대 한 개체를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="0897d-103">Returns a <xref:System.Type> object for the specified type.</span></span> <span data-ttu-id="0897d-104"><xref:System.Type>개체는 속성, 메서드 및 이벤트와 같은 형식에 대 한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="0897d-104">The <xref:System.Type> object provides information about the type such as its properties, methods, and events.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0897d-105">구문</span><span class="sxs-lookup"><span data-stu-id="0897d-105">Syntax</span></span>  
  
```vb  
GetType(typename)  
```  
  
## <a name="parameters"></a><span data-ttu-id="0897d-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="0897d-106">Parameters</span></span>  
  
|<span data-ttu-id="0897d-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="0897d-107">Parameter</span></span>|<span data-ttu-id="0897d-108">Description</span><span class="sxs-lookup"><span data-stu-id="0897d-108">Description</span></span>|  
|---|---|  
|`typename`|<span data-ttu-id="0897d-109">정보를 원하는 형식의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="0897d-109">The name of the type for which you desire information.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0897d-110">설명</span><span class="sxs-lookup"><span data-stu-id="0897d-110">Remarks</span></span>  

 <span data-ttu-id="0897d-111">`GetType`연산자는 지정 된 <xref:System.Type> 에 대 한 개체를 반환 합니다 `typename` .</span><span class="sxs-lookup"><span data-stu-id="0897d-111">The `GetType` operator returns the <xref:System.Type> object for the specified `typename`.</span></span> <span data-ttu-id="0897d-112">에서 정의 된 형식의 이름을 전달할 수 있습니다 `typename` .</span><span class="sxs-lookup"><span data-stu-id="0897d-112">You can pass the name of any defined type in `typename`.</span></span> <span data-ttu-id="0897d-113">여기에는 다음과 같은 사항이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="0897d-113">This includes the following:</span></span>  
  
- <span data-ttu-id="0897d-114">또는와 같은 모든 Visual Basic 데이터 형식 `Boolean` `Date` 입니다.</span><span class="sxs-lookup"><span data-stu-id="0897d-114">Any Visual Basic data type, such as `Boolean` or `Date`.</span></span>  
  
- <span data-ttu-id="0897d-115">또는와 같은 모든 .NET Framework 클래스, 구조체, 모듈 또는 인터페이스 <xref:System.ArgumentException?displayProperty=nameWithType> <xref:System.Double?displayProperty=nameWithType> 입니다.</span><span class="sxs-lookup"><span data-stu-id="0897d-115">Any .NET Framework class, structure, module, or interface, such as <xref:System.ArgumentException?displayProperty=nameWithType> or <xref:System.Double?displayProperty=nameWithType>.</span></span>  
  
- <span data-ttu-id="0897d-116">응용 프로그램에 정의 된 클래스, 구조체, 모듈 또는 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="0897d-116">Any class, structure, module, or interface defined by your application.</span></span>  
  
- <span data-ttu-id="0897d-117">응용 프로그램에서 정의 하는 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="0897d-117">Any array defined by your application.</span></span>  
  
- <span data-ttu-id="0897d-118">응용 프로그램에서 정의 하는 대리자입니다.</span><span class="sxs-lookup"><span data-stu-id="0897d-118">Any delegate defined by your application.</span></span>  
  
- <span data-ttu-id="0897d-119">Visual Basic, .NET Framework 또는 응용 프로그램에 의해 정의 되는 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="0897d-119">Any enumeration defined by Visual Basic, the .NET Framework, or your application.</span></span>  
  
 <span data-ttu-id="0897d-120">개체 변수의 형식 개체를 가져오려면 메서드를 사용 <xref:System.Type.GetType%2A?displayProperty=nameWithType> 합니다.</span><span class="sxs-lookup"><span data-stu-id="0897d-120">If you want to get the type object of an object variable, use the <xref:System.Type.GetType%2A?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="0897d-121">`GetType`연산자는 다음과 같은 경우에 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0897d-121">The `GetType` operator can be useful in the following circumstances:</span></span>  
  
- <span data-ttu-id="0897d-122">런타임에 형식에 대 한 메타 데이터에 액세스 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0897d-122">You must access the metadata for a type at run time.</span></span> <span data-ttu-id="0897d-123"><xref:System.Type>개체는 형식 멤버 및 배포 정보와 같은 메타 데이터를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="0897d-123">The <xref:System.Type> object supplies metadata such as type members and deployment information.</span></span> <span data-ttu-id="0897d-124">예를 들어, 어셈블리를 반영 하기 위해 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="0897d-124">You need this, for example, to reflect over an assembly.</span></span> <span data-ttu-id="0897d-125">자세한 내용은 <xref:System.Reflection?displayProperty=nameWithType>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0897d-125">For more information, see <xref:System.Reflection?displayProperty=nameWithType>.</span></span>  
  
- <span data-ttu-id="0897d-126">두 개체 참조를 비교 하 여 동일한 형식의 인스턴스를 참조 하는지 여부를 확인 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="0897d-126">You want to compare two object references to see if they refer to instances of the same type.</span></span> <span data-ttu-id="0897d-127">이 경우는 `GetType` 동일한 개체에 대 한 참조를 반환 <xref:System.Type> 합니다.</span><span class="sxs-lookup"><span data-stu-id="0897d-127">If they do, `GetType` returns references to the same <xref:System.Type> object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0897d-128">예제</span><span class="sxs-lookup"><span data-stu-id="0897d-128">Example</span></span>  

 <span data-ttu-id="0897d-129">다음 예에서는 `GetType` 사용 중인 연산자를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0897d-129">The following examples show the `GetType` operator in use.</span></span>  
  
 [!code-vb[VbVbalrOperators#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#26)]  
  
## <a name="see-also"></a><span data-ttu-id="0897d-130">참조</span><span class="sxs-lookup"><span data-stu-id="0897d-130">See also</span></span>

- [<span data-ttu-id="0897d-131">Visual Basic에서의 연산자 우선 순위</span><span class="sxs-lookup"><span data-stu-id="0897d-131">Operator Precedence in Visual Basic</span></span>](operator-precedence.md)
- [<span data-ttu-id="0897d-132">기능별 연산자 목록</span><span class="sxs-lookup"><span data-stu-id="0897d-132">Operators Listed by Functionality</span></span>](operators-listed-by-functionality.md)
- [<span data-ttu-id="0897d-133">연산자 및 식</span><span class="sxs-lookup"><span data-stu-id="0897d-133">Operators and Expressions</span></span>](../../programming-guide/language-features/operators-and-expressions/index.md)
