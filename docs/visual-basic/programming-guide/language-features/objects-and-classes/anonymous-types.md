---
title: 익명 형식
ms.date: 07/20/2015
f1_keywords:
- vb.AnonymousType
helpviewer_keywords:
- anonymous types [Visual Basic], about anonymous types
- anonymous types [Visual Basic]
- types [Visual Basic], anonymous
ms.assetid: 7b87532c-4b3e-4398-8503-6ea9d67574a4
ms.openlocfilehash: 5ab3cf8c3c02ff35890f71ad6c7f314b51b87133
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2020
ms.locfileid: "91075241"
---
# <a name="anonymous-types-visual-basic"></a><span data-ttu-id="41f72-102">익명 형식(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="41f72-102">Anonymous Types (Visual Basic)</span></span>

<span data-ttu-id="41f72-103">Visual Basic는 데이터 형식에 대 한 클래스 정의를 작성 하지 않고 개체를 만들 수 있도록 하는 익명 형식을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="41f72-103">Visual Basic supports anonymous types, which enable you to create objects without writing a class definition for the data type.</span></span> <span data-ttu-id="41f72-104">대신 컴파일러가 클래스를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="41f72-104">Instead, the compiler generates a class for you.</span></span> <span data-ttu-id="41f72-105">클래스에는 사용할 수 있는 이름이 없고에서 직접 상속 <xref:System.Object> 되며 개체를 선언할 때 지정 하는 속성이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="41f72-105">The class has no usable name, inherits directly from <xref:System.Object>, and contains the properties you specify in declaring the object.</span></span> <span data-ttu-id="41f72-106">데이터 형식의 이름을 지정 하지 않았기 때문에 *익명 형식*이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="41f72-106">Because the name of the data type is not specified, it is referred to as an *anonymous type*.</span></span>  
  
 <span data-ttu-id="41f72-107">다음 예제에서는 변수를 선언 하 고 `product` , 및 라는 두 개의 속성이 있는 무명 형식의 인스턴스로 만듭니다 `Name` `Price` .</span><span class="sxs-lookup"><span data-stu-id="41f72-107">The following example declares and creates variable `product` as an instance of an anonymous type that has two properties, `Name` and `Price`.</span></span>  
  
 [!code-vb[VbVbalrAnonymousTypes#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class1.vb#1)]  
  
 <span data-ttu-id="41f72-108">쿼리 *식은* 익명 형식을 사용 하 여 쿼리에 의해 선택 된 데이터 열을 결합 합니다.</span><span class="sxs-lookup"><span data-stu-id="41f72-108">A *query expression* uses anonymous types to combine columns of data selected by a query.</span></span> <span data-ttu-id="41f72-109">특정 쿼리에서 선택할 수 있는 열을 예측할 수 없으므로 결과 유형을 미리 정의할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="41f72-109">You cannot define the type of the result in advance, because you cannot predict the columns a particular query might select.</span></span> <span data-ttu-id="41f72-110">익명 형식을 사용 하면 임의 개수의 열을 순서 대로 선택 하는 쿼리를 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41f72-110">Anonymous types enable you to write a query that selects any number of columns, in any order.</span></span> <span data-ttu-id="41f72-111">컴파일러는 지정 된 속성 및 지정 된 순서와 일치 하는 데이터 형식을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="41f72-111">The compiler creates a data type that matches the specified properties and the specified order.</span></span>  
  
 <span data-ttu-id="41f72-112">다음 예제에서 `products` 는 각각 여러 속성을 포함 하는 제품 개체의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="41f72-112">In the following examples, `products` is a list of product objects, each of which has many properties.</span></span> <span data-ttu-id="41f72-113">변수는 `namePriceQuery` 실행 시 및 라는 두 개의 속성이 있는 익명 형식의 인스턴스 컬렉션을 반환 하는 쿼리 정의를 포함 합니다 `Name` `Price` .</span><span class="sxs-lookup"><span data-stu-id="41f72-113">Variable `namePriceQuery` holds the definition of a query that, when it is executed, returns a collection of instances of an anonymous type that has two properties, `Name` and `Price`.</span></span>  
  
 [!code-vb[VbVbalrAnonymousTypes#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class1.vb#2)]  
  
 <span data-ttu-id="41f72-114">변수는 `nameQuantityQuery` 실행 시 및 라는 두 개의 속성이 있는 익명 형식의 인스턴스 컬렉션을 반환 하는 쿼리 정의를 포함 합니다 `Name` `OnHand` .</span><span class="sxs-lookup"><span data-stu-id="41f72-114">Variable `nameQuantityQuery` holds the definition of a query that, when it is executed, returns a collection of instances of an anonymous type that has two properties, `Name` and `OnHand`.</span></span>  
  
 [!code-vb[VbVbalrAnonymousTypes#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class1.vb#3)]  
  
 <span data-ttu-id="41f72-115">익명 형식에 대해 컴파일러에서 생성 하는 코드에 대 한 자세한 내용은 [익명 형식 정의](anonymous-type-definition.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="41f72-115">For more information about the code created by the compiler for an anonymous type, see [Anonymous Type Definition](anonymous-type-definition.md).</span></span>  
  
> [!CAUTION]
> <span data-ttu-id="41f72-116">익명 형식의 이름은 컴파일러에서 생성 되며 컴파일 간에 달라질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41f72-116">The name of the anonymous type is compiler generated and may vary from compilation to compilation.</span></span> <span data-ttu-id="41f72-117">프로젝트를 다시 컴파일할 때 이름이 변경 될 수 있기 때문에 코드에서를 사용 하거나 익명 형식의 이름을 사용 하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="41f72-117">Your code should not use or rely on the name of an anonymous type because the name might change when a project is recompiled.</span></span>  
  
## <a name="declaring-an-anonymous-type"></a><span data-ttu-id="41f72-118">무명 형식 선언</span><span class="sxs-lookup"><span data-stu-id="41f72-118">Declaring an Anonymous Type</span></span>  

 <span data-ttu-id="41f72-119">무명 형식의 인스턴스 선언에서는 이니셜라이저 목록을 사용 하 여 형식의 속성을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="41f72-119">The declaration of an instance of an anonymous type uses an initializer list to specify the properties of the type.</span></span> <span data-ttu-id="41f72-120">무명 형식을 선언 하는 경우에는 속성을 지정할 수 있으며, 메서드 또는 이벤트와 같은 다른 클래스 요소는 지정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="41f72-120">You can specify only properties when you declare an anonymous type, not other class elements such as methods or events.</span></span> <span data-ttu-id="41f72-121">다음 예제에서 `product1` 는와 라는 두 개의 속성이 있는 무명 형식의 인스턴스입니다. `Name` `Price`</span><span class="sxs-lookup"><span data-stu-id="41f72-121">In the following example, `product1` is an instance of an anonymous type that has two properties: `Name` and `Price`.</span></span>  
  
 [!code-vb[VbVbalrAnonymousTypes#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class1.vb#4)]  
  
 <span data-ttu-id="41f72-122">속성을 키 속성으로 지정 하는 경우이 속성을 사용 하 여 두 익명 형식 인스턴스가 같은지 비교할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41f72-122">If you designate properties as key properties, you can use them to compare two anonymous type instances for equality.</span></span> <span data-ttu-id="41f72-123">그러나 키 속성의 값은 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="41f72-123">However, the values of key properties cannot be changed.</span></span> <span data-ttu-id="41f72-124">자세한 내용은이 항목의 뒷부분에 나오는 키 속성 섹션을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="41f72-124">See the Key Properties section later in this topic for more information.</span></span>  
  
 <span data-ttu-id="41f72-125">무명 형식의 인스턴스를 선언 하는 것은 개체 이니셜라이저를 사용 하 여 명명 된 형식의 인스턴스를 선언 하는 것과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="41f72-125">Notice that declaring an instance of an anonymous type is like declaring an instance of a named type by using an object initializer:</span></span>  
  
 [!code-vb[VbVbalrAnonymousTypes#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class1.vb#5)]  
  
 <span data-ttu-id="41f72-126">익명 형식 속성을 지정 하는 다른 방법에 대 한 자세한 내용은 [방법: 익명 형식 선언에서 속성 이름 및 형식 유추](how-to-infer-property-names-and-types-in-anonymous-type-declarations.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="41f72-126">For more information about other ways to specify anonymous type properties, see [How to: Infer Property Names and Types in Anonymous Type Declarations](how-to-infer-property-names-and-types-in-anonymous-type-declarations.md).</span></span>  
  
## <a name="key-properties"></a><span data-ttu-id="41f72-127">키 속성</span><span class="sxs-lookup"><span data-stu-id="41f72-127">Key Properties</span></span>  

 <span data-ttu-id="41f72-128">키 속성은 다음과 같은 몇 가지 기본적인 방법으로 키가 아닌 속성과 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="41f72-128">Key properties differ from non-key properties in several fundamental ways:</span></span>  
  
- <span data-ttu-id="41f72-129">두 인스턴스가 같은지 여부를 확인 하기 위해 키 속성의 값만 비교 됩니다.</span><span class="sxs-lookup"><span data-stu-id="41f72-129">Only the values of key properties are compared in order to determine whether two instances are equal.</span></span>  
  
- <span data-ttu-id="41f72-130">키 속성의 값은 읽기 전용 이며 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="41f72-130">The values of key properties are read-only and cannot be changed.</span></span>  
  
- <span data-ttu-id="41f72-131">익명 형식에 대 한 컴파일러 생성 해시 코드 알고리즘에는 키 속성 값만 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="41f72-131">Only key property values are included in the compiler-generated hash code algorithm for an anonymous type.</span></span>  
  
### <a name="equality"></a><span data-ttu-id="41f72-132">등호</span><span class="sxs-lookup"><span data-stu-id="41f72-132">Equality</span></span>  

 <span data-ttu-id="41f72-133">익명 형식의 인스턴스는 동일한 익명 형식의 인스턴스인 경우에만 동일할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41f72-133">Instances of anonymous types can be equal only if they are instances of the same anonymous type.</span></span> <span data-ttu-id="41f72-134">컴파일러는 다음 조건을 충족 하는 경우 두 인스턴스를 동일한 형식의 인스턴스로 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="41f72-134">The compiler treats two instances as instances of the same type if they meet the following conditions:</span></span>  
  
- <span data-ttu-id="41f72-135">이러한 어셈블리는 동일한 어셈블리에 선언 됩니다.</span><span class="sxs-lookup"><span data-stu-id="41f72-135">They are declared in the same assembly.</span></span>  
  
- <span data-ttu-id="41f72-136">해당 속성의 이름은 동일 하 고 유추 된 형식이 같으며 동일한 순서로 선언 됩니다.</span><span class="sxs-lookup"><span data-stu-id="41f72-136">Their properties have the same names, the same inferred types, and are declared in the same order.</span></span> <span data-ttu-id="41f72-137">이름 비교는 대/소문자를 구분 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="41f72-137">Name comparisons are not case-sensitive.</span></span>  
  
- <span data-ttu-id="41f72-138">각각의 동일한 속성이 키 속성으로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="41f72-138">The same properties in each are marked as key properties.</span></span>  
  
- <span data-ttu-id="41f72-139">각 선언에서 하나 이상의 속성이 키 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="41f72-139">At least one property in each declaration is a key property.</span></span>  
  
 <span data-ttu-id="41f72-140">키 속성이 없는 무명 형식의 인스턴스는 자체와 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="41f72-140">An instance of an anonymous types that has no key properties is equal only to itself.</span></span>  
  
 [!code-vb[VbVbalrAnonymousTypes#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class1.vb#6)]  
  
 <span data-ttu-id="41f72-141">동일한 익명 형식의 두 인스턴스는 해당 키 속성의 값이 동일한 경우에 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="41f72-141">Two instances of the same anonymous type are equal if the values of their key properties are equal.</span></span> <span data-ttu-id="41f72-142">다음 예에서는 같음을 테스트 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="41f72-142">The following examples illustrate how equality is tested.</span></span>  
  
 [!code-vb[VbVbalrAnonymousTypes#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class1.vb#7)]  
  
### <a name="read-only-values"></a><span data-ttu-id="41f72-143">읽기 전용 값</span><span class="sxs-lookup"><span data-stu-id="41f72-143">Read-Only Values</span></span>  

 <span data-ttu-id="41f72-144">키 속성의 값은 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="41f72-144">The values of key properties cannot be changed.</span></span> <span data-ttu-id="41f72-145">예를 들어 `prod8` 앞의 예제에서 `Name` 및 필드는 이지만 `Price` `read-only` `OnHand` 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41f72-145">For example, in `prod8` in the previous example, the `Name` and `Price` fields are `read-only`, but `OnHand` can be changed.</span></span>  
  
 [!code-vb[VbVbalrAnonymousTypes#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class1.vb#8)]  
  
## <a name="anonymous-types-from-query-expressions"></a><span data-ttu-id="41f72-146">쿼리 식의 익명 형식</span><span class="sxs-lookup"><span data-stu-id="41f72-146">Anonymous Types from Query Expressions</span></span>  

 <span data-ttu-id="41f72-147">쿼리 식에는 항상 익명 형식을 만들 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="41f72-147">Query expressions do not always require the creation of anonymous types.</span></span> <span data-ttu-id="41f72-148">가능 하면 기존 형식을 사용 하 여 열 데이터를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="41f72-148">When possible, they use an existing type to hold the column data.</span></span> <span data-ttu-id="41f72-149">이는 쿼리가 데이터 원본에서 전체 레코드를 반환 하거나 각 레코드의 필드를 하나만 반환 하는 경우에 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="41f72-149">This occurs when the query returns either whole records from the data source, or only one field from each record.</span></span> <span data-ttu-id="41f72-150">다음 코드 예제에서 `customers` 는 클래스의 개체 컬렉션입니다 `Customer` .</span><span class="sxs-lookup"><span data-stu-id="41f72-150">In the following code examples, `customers` is a collection of objects of a `Customer` class.</span></span> <span data-ttu-id="41f72-151">클래스에는 많은 속성이 있으며 쿼리 결과에서 순서에 관계 없이 하나 이상의 속성을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41f72-151">The class has many properties, and you can include one or more of them in the query result, in any order.</span></span> <span data-ttu-id="41f72-152">처음 두 예제에서는 쿼리가 명명 된 형식의 요소를 선택 하기 때문에 익명 형식이 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="41f72-152">In the first two examples, no anonymous types are required because the queries select elements of named types:</span></span>  
  
- <span data-ttu-id="41f72-153">`custs1` 가 문자열 이기 때문에 문자열의 컬렉션을 포함 `cust.Name` 합니다.</span><span class="sxs-lookup"><span data-stu-id="41f72-153">`custs1` contains a collection of strings, because `cust.Name` is a string.</span></span>  
  
     [!code-vb[VbVbalrAnonymousTypes#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#30)]  
  
- <span data-ttu-id="41f72-154">`custs2``Customer`의 각 요소가 `customers` `Customer` 개체이 고 전체 요소가 쿼리에서 선택 되기 때문에 개체의 컬렉션을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="41f72-154">`custs2` contains a collection of `Customer` objects, because each element of `customers` is a `Customer` object, and the whole element is selected by the query.</span></span>  
  
     [!code-vb[VbVbalrAnonymousTypes#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#31)]  
  
 <span data-ttu-id="41f72-155">그러나 적절 한 명명 된 형식은 항상 사용할 수 있는 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="41f72-155">However, appropriate named types are not always available.</span></span> <span data-ttu-id="41f72-156">한 가지 목적으로 고객 이름 및 주소를 선택 하 고, 다른 사용자에 대 한 고객 ID 번호 및 위치를 선택 하 고, 세 번째에 대 한 고객 이름, 주소 및 주문 기록을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41f72-156">You might want to select customer names and addresses for one purpose, customer ID numbers and locations for another, and customer names, addresses, and order histories for a third.</span></span> <span data-ttu-id="41f72-157">익명 형식을 사용 하면 결과를 저장 하기 위해 새 명명 된 형식을 먼저 선언 하지 않고 임의의 순서로 속성 조합을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41f72-157">Anonymous types enable you to select any combination of properties, in any order, without first declaring a new named type to hold the result.</span></span> <span data-ttu-id="41f72-158">대신 컴파일러는 각 속성 컴파일에 대해 무명 형식을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="41f72-158">Instead, the compiler creates an anonymous type for each compilation of properties.</span></span> <span data-ttu-id="41f72-159">다음 쿼리는의 각 개체에서 고객의 이름과 ID 숫자만 선택 합니다 `Customer` `customers` .</span><span class="sxs-lookup"><span data-stu-id="41f72-159">The following query selects only the customer's name and ID number from each `Customer` object in `customers`.</span></span> <span data-ttu-id="41f72-160">따라서 컴파일러는 이러한 두 속성만 포함 하는 무명 형식을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="41f72-160">Therefore, the compiler creates an anonymous type that contains only those two properties.</span></span>  
  
 [!code-vb[VbVbalrAnonymousTYpes#32](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#32)]  
  
 <span data-ttu-id="41f72-161">무명 형식의 속성 이름과 데이터 형식은 모두, 및에 대 한 인수에서 가져옵니다 `Select` `cust.Name` `cust.ID` .</span><span class="sxs-lookup"><span data-stu-id="41f72-161">Both the names and the data types of the properties in the anonymous type are taken from the arguments to `Select`, `cust.Name` and `cust.ID`.</span></span> <span data-ttu-id="41f72-162">쿼리에서 만든 무명 형식의 속성은 항상 키 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="41f72-162">The properties in an anonymous type that is created by a query are always key properties.</span></span> <span data-ttu-id="41f72-163">`custs3`다음 루프에서를 실행 하는 경우 `For Each` 결과는 두 개의 키 속성인 및가 있는 익명 형식의 인스턴스 컬렉션입니다 `Name` `ID` .</span><span class="sxs-lookup"><span data-stu-id="41f72-163">When `custs3` is executed in the following `For Each` loop, the result is a collection of instances of an anonymous type with two key properties, `Name` and `ID`.</span></span>  
  
 [!code-vb[VbVbalrAnonymousTypes#33](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#33)]  
  
 <span data-ttu-id="41f72-164">로 표현 되는 컬렉션의 요소는 `custs3` 강력한 형식이 며 IntelliSense를 사용 하 여 사용 가능한 속성을 탐색 하 고 해당 형식을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41f72-164">The elements in the collection represented by `custs3` are strongly typed, and you can use IntelliSense to navigate through the available properties and to verify their types.</span></span>  
  
 <span data-ttu-id="41f72-165">자세한 내용은 [Visual Basic의 LINQ 쿼리 소개](../linq/introduction-to-linq.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="41f72-165">For more information, see [Introduction to LINQ in Visual Basic](../linq/introduction-to-linq.md).</span></span>  
  
## <a name="deciding-whether-to-use-anonymous-types"></a><span data-ttu-id="41f72-166">익명 형식 사용 여부 결정</span><span class="sxs-lookup"><span data-stu-id="41f72-166">Deciding Whether to Use Anonymous Types</span></span>  

 <span data-ttu-id="41f72-167">개체를 익명 클래스의 인스턴스로 만들기 전에이 옵션을 선택 하는 것이 가장 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="41f72-167">Before you create an object as an instance of an anonymous class, consider whether that is the best option.</span></span> <span data-ttu-id="41f72-168">예를 들어 관련 데이터를 포함 하는 임시 개체를 만들려는 경우 전체 클래스에 포함 될 수 있는 다른 필드와 메서드가 필요 하지 않은 경우 무명 형식은 좋은 솔루션입니다.</span><span class="sxs-lookup"><span data-stu-id="41f72-168">For example, if you want to create a temporary object to contain related data, and you have no need for other fields and methods that a complete class might contain, an anonymous type is a good solution.</span></span> <span data-ttu-id="41f72-169">또한 각 선언에 대해 다른 속성을 선택 하려는 경우 나 속성의 순서를 변경 하려는 경우에는 익명 형식도 편리 합니다.</span><span class="sxs-lookup"><span data-stu-id="41f72-169">Anonymous types are also convenient if you want a different selection of properties for each declaration, or if you want to change the order of the properties.</span></span> <span data-ttu-id="41f72-170">그러나 프로젝트에 같은 속성을 가진 개체가 여러 개 포함 되어 있는 경우에는 클래스 생성자를 사용 하 여 명명 된 형식을 사용 하 여 보다 쉽게 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41f72-170">However, if your project includes several objects that have the same properties, in a fixed order, you can declare them more easily by using a named type with a class constructor.</span></span> <span data-ttu-id="41f72-171">예를 들어 적절 한 생성자를 사용 하는 경우 `Product` 익명 형식의 여러 인스턴스를 선언 하는 것 보다 클래스의 여러 인스턴스를 선언 하는 것이 더 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="41f72-171">For example, with an appropriate constructor, it is easier to declare several instances of a `Product` class than it is to declare several instances of an anonymous type.</span></span>  
  
 [!code-vb[VbVbalrAnonymousTypes#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class1.vb#9)]  
  
 <span data-ttu-id="41f72-172">명명 된 형식의 또 다른 장점은 컴파일러에서 실수로 잘못 된 형식의 속성 이름을 catch 할 수 있다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="41f72-172">Another advantage of named types is that the compiler can catch an accidental mistyping of a property name.</span></span> <span data-ttu-id="41f72-173">앞의 예제에서, `firstProd2` `secondProd2` 및 `thirdProd2` 는 동일한 익명 형식의 인스턴스인 것입니다.</span><span class="sxs-lookup"><span data-stu-id="41f72-173">In the previous examples, `firstProd2`, `secondProd2`, and `thirdProd2` are intended to be instances of the same anonymous type.</span></span> <span data-ttu-id="41f72-174">그러나 다음 방법 중 하나를 실수로 선언 하는 경우 `thirdProd2` 해당 형식은 및의 형식과 다를 수 있습니다 `firstProd2` `secondProd2` .</span><span class="sxs-lookup"><span data-stu-id="41f72-174">However, if you were to accidentally declare `thirdProd2` in one of the following ways, its type would be different from that of `firstProd2` and `secondProd2`.</span></span>  
  
 [!code-vb[VbVbalrAnonymousTypes#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class1.vb#10)]  
  
 <span data-ttu-id="41f72-175">무엇 보다도, 명명 된 형식의 인스턴스에 적용 되지 않는 익명 형식의 사용에 대 한 제한 사항이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41f72-175">More importantly, there are limitations on the use of anonymous types that do not apply to instances of named types.</span></span> <span data-ttu-id="41f72-176">`firstProd2`, `secondProd2` 및 `thirdProd2` 는 동일한 익명 형식의 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="41f72-176">`firstProd2`, `secondProd2`, and `thirdProd2` are instances of the same anonymous type.</span></span> <span data-ttu-id="41f72-177">그러나 공유 익명 형식의 이름은 사용할 수 없으며 코드에서 형식 이름이 필요한 위치에 나타날 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="41f72-177">However, the name for the shared anonymous type is not available and cannot appear where a type name is expected in your code.</span></span> <span data-ttu-id="41f72-178">예를 들어, 무명 형식은 메서드 시그니처를 정의 하는 데 사용 하거나 다른 변수나 필드를 선언 하거나 모든 형식 선언에 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="41f72-178">For example, an anonymous type cannot be used to define a method signature, to declare another variable or field, or in any type declaration.</span></span> <span data-ttu-id="41f72-179">따라서 메서드 간에 정보를 공유 해야 하는 경우에는 익명 형식이 적절 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="41f72-179">As a result, anonymous types are not appropriate when you have to share information across methods.</span></span>  
  
## <a name="an-anonymous-type-definition"></a><span data-ttu-id="41f72-180">익명 형식 정의</span><span class="sxs-lookup"><span data-stu-id="41f72-180">An Anonymous Type Definition</span></span>  

 <span data-ttu-id="41f72-181">익명 형식의 인스턴스 선언에 대 한 응답으로 컴파일러는 지정 된 속성을 포함 하는 새 클래스 정의를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="41f72-181">In response to the declaration of an instance of an anonymous type, the compiler creates a new class definition that contains the specified properties.</span></span>  
  
 <span data-ttu-id="41f72-182">익명 형식에 키 속성이 하나 이상 포함 되어 있으면 정의는 <xref:System.Object> <xref:System.Object.Equals%2A> , <xref:System.Object.GetHashCode%2A> 및에서 상속 된 세 개의 멤버를 재정의 <xref:System.Object.ToString%2A> 합니다.</span><span class="sxs-lookup"><span data-stu-id="41f72-182">If the anonymous type contains at least one key property, the definition overrides three members inherited from <xref:System.Object>: <xref:System.Object.Equals%2A>, <xref:System.Object.GetHashCode%2A>, and <xref:System.Object.ToString%2A>.</span></span> <span data-ttu-id="41f72-183">같음을 테스트 하 고 해시 코드 값을 결정 하기 위해 생성 된 코드는 키 속성만 고려 합니다.</span><span class="sxs-lookup"><span data-stu-id="41f72-183">The code produced for testing equality and determining the hash code value considers only the key properties.</span></span> <span data-ttu-id="41f72-184">익명 형식에 키 속성이 없으면만 <xref:System.Object.ToString%2A> 재정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="41f72-184">If the anonymous type contains no key properties, only <xref:System.Object.ToString%2A> is overridden.</span></span> <span data-ttu-id="41f72-185">익명 형식의 명시적으로 명명 된 속성은 이러한 생성 된 메서드와 충돌할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="41f72-185">Explicitly named properties of an anonymous type cannot conflict with these generated methods.</span></span> <span data-ttu-id="41f72-186">즉,, 또는를 사용 `.Equals` `.GetHashCode` `.ToString` 하 여 속성의 이름을 지정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="41f72-186">That is, you cannot use `.Equals`, `.GetHashCode`, or `.ToString` to name a property.</span></span>  
  
 <span data-ttu-id="41f72-187">하나 이상의 키 속성이 있는 무명 형식 정의는 인터페이스를 구현 하기도 <xref:System.IEquatable%601?displayProperty=nameWithType> `T` 합니다. 여기서은 익명 형식의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="41f72-187">Anonymous type definitions that have at least one key property also implement the <xref:System.IEquatable%601?displayProperty=nameWithType> interface, where `T` is the type of the anonymous type.</span></span>  
  
 <span data-ttu-id="41f72-188">컴파일러에서 생성 되는 코드 및 재정의 된 메서드의 기능에 대 한 자세한 내용은 [익명 형식 정의](anonymous-type-definition.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="41f72-188">For more information about the code created by the compiler and the functionality of the overridden methods, see [Anonymous Type Definition](anonymous-type-definition.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41f72-189">참조</span><span class="sxs-lookup"><span data-stu-id="41f72-189">See also</span></span>

- [<span data-ttu-id="41f72-190">개체 이니셜라이저: 명명된 형식 및 무명 형식</span><span class="sxs-lookup"><span data-stu-id="41f72-190">Object Initializers: Named and Anonymous Types</span></span>](object-initializers-named-and-anonymous-types.md)
- [<span data-ttu-id="41f72-191">지역 형식 유추</span><span class="sxs-lookup"><span data-stu-id="41f72-191">Local Type Inference</span></span>](../variables/local-type-inference.md)
- [<span data-ttu-id="41f72-192">Visual Basic의 LINQ 소개</span><span class="sxs-lookup"><span data-stu-id="41f72-192">Introduction to LINQ in Visual Basic</span></span>](../linq/introduction-to-linq.md)
- [<span data-ttu-id="41f72-193">방법: 익명 형식 선언에서 속성 이름 및 형식 유추</span><span class="sxs-lookup"><span data-stu-id="41f72-193">How to: Infer Property Names and Types in Anonymous Type Declarations</span></span>](how-to-infer-property-names-and-types-in-anonymous-type-declarations.md)
- [<span data-ttu-id="41f72-194">익명 형식 정의</span><span class="sxs-lookup"><span data-stu-id="41f72-194">Anonymous Type Definition</span></span>](anonymous-type-definition.md)
- [<span data-ttu-id="41f72-195">Key</span><span class="sxs-lookup"><span data-stu-id="41f72-195">Key</span></span>](../../../language-reference/modifiers/key.md)
