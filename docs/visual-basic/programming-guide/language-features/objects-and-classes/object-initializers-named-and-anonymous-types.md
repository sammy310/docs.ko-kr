---
title: '개체 이니셜라이저: 명명된 형식과 익명 형식'
ms.date: 07/20/2015
f1_keywords:
- vb.ObjectInitializer
helpviewer_keywords:
- object initializers [Visual Basic]
- anonymous types [Visual Basic], object initializers
- initializing properties [Visual Basic]
- initializers [Visual Basic]
- named types [Visual Basic]
ms.assetid: e2df3807-a70f-49dd-ac94-f1e07f472b1b
ms.openlocfilehash: e6ffc649d7eb841c2d009b0ec1237975f46e2d2d
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/03/2020
ms.locfileid: "75636811"
---
# <a name="object-initializers-named-and-anonymous-types-visual-basic"></a><span data-ttu-id="f3030-102">개체 이니셜라이저: 명명된 형식과 익명 형식(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f3030-102">Object Initializers: Named and Anonymous Types (Visual Basic)</span></span>
<span data-ttu-id="f3030-103">개체 이니셜라이저를 사용 하면 단일 식을 사용 하 여 복합 개체에 대 한 속성을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3030-103">Object initializers enable you to specify properties for a complex object by using a single expression.</span></span> <span data-ttu-id="f3030-104">명명 된 형식과 익명 형식의 인스턴스를 만드는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3030-104">They can be used to create instances of named types and of anonymous types.</span></span>  
  
## <a name="declarations"></a><span data-ttu-id="f3030-105">선언</span><span class="sxs-lookup"><span data-stu-id="f3030-105">Declarations</span></span>  
 <span data-ttu-id="f3030-106">명명 된 형식과 익명 형식의 인스턴스 선언은 거의 동일 하 게 보일 수 있지만 그 영향은 동일 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f3030-106">Declarations of instances of named and anonymous types can look almost identical, but their effects are not the same.</span></span> <span data-ttu-id="f3030-107">각 범주에는 자체의 기능 및 제한 사항이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3030-107">Each category has abilities and restrictions of its own.</span></span> <span data-ttu-id="f3030-108">다음 예제에서는 개체 이니셜라이저 목록을 사용 하 여 `Customer`명명 된 클래스의 인스턴스를 선언 하 고 초기화 하는 편리한 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f3030-108">The following example shows a convenient way to declare and initialize an instance of a named class, `Customer`, by using an object initializer list.</span></span> <span data-ttu-id="f3030-109">클래스의 이름은 키워드 `New`뒤에 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f3030-109">Notice that the name of the class is specified after the keyword `New`.</span></span>  
  
 [!code-vb[VbVbalrObjectInit#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class1.vb#1)]  
  
 <span data-ttu-id="f3030-110">익명 형식에 사용할 수 있는 이름이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f3030-110">An anonymous type has no usable name.</span></span> <span data-ttu-id="f3030-111">따라서 익명 형식의 인스턴스화에는 클래스 이름을 포함할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f3030-111">Therefore an instantiation of an anonymous type cannot include a class name.</span></span>  
  
 [!code-vb[VbVbalrObjectInit#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class1.vb#2)]  
  
 <span data-ttu-id="f3030-112">두 선언의 요구 사항과 결과가 동일 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f3030-112">The requirements and results of the two declarations are not the same.</span></span> <span data-ttu-id="f3030-113">`namedCust`의 경우 `Name` 속성이 있는 `Customer` 클래스가 이미 존재 해야 하며 선언은 해당 클래스의 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f3030-113">For `namedCust`, a `Customer` class that has a `Name` property must already exist, and the declaration creates an instance of that class.</span></span> <span data-ttu-id="f3030-114">`anonymousCust`의 경우 컴파일러는 하나의 속성, `Name`라는 문자열을 포함 하는 새 클래스를 정의 하 고 해당 클래스의 새 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f3030-114">For `anonymousCust`, the compiler defines a new class that has one property, a string called `Name`, and creates a new instance of that class.</span></span>  
  
## <a name="named-types"></a><span data-ttu-id="f3030-115">명명 된 형식</span><span class="sxs-lookup"><span data-stu-id="f3030-115">Named Types</span></span>  
 <span data-ttu-id="f3030-116">개체 이니셜라이저는 형식의 생성자를 호출 하는 간단한 방법을 제공 하 고 단일 문에서 일부 또는 모든 속성의 값을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3030-116">Object initializers provide a simple way to call the constructor of a type and then set the values of some or all properties in a single statement.</span></span> <span data-ttu-id="f3030-117">컴파일러가 인수를 제공 하지 않는 경우 매개 변수가 없는 생성자 또는 하나 이상의 인수가 전송 될 경우 매개 변수가 있는 생성자를 호출 하 여 문에 대 한 적절 한 생성자를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3030-117">The compiler invokes the appropriate constructor for the statement: the parameterless constructor if no arguments are presented, or a parameterized constructor if one or more arguments are sent.</span></span> <span data-ttu-id="f3030-118">그런 다음 지정 된 속성은 이니셜라이저 목록에 표시 되는 순서 대로 초기화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f3030-118">After that, the specified properties are initialized in the order in which they are presented in the initializer list.</span></span>  
  
 <span data-ttu-id="f3030-119">이니셜라이저 목록의 각 초기화는 클래스의 멤버에 초기 값을 할당 하는 것으로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f3030-119">Each initialization in the initializer list consists of the assignment of an initial value to a member of the class.</span></span> <span data-ttu-id="f3030-120">멤버의 이름과 데이터 형식은 클래스를 정의할 때 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f3030-120">The names and data types of the members are determined when the class is defined.</span></span> <span data-ttu-id="f3030-121">다음 예제에서는 `Customer` 클래스가 있어야 하 고, 문자열 값을 받아들일 수 있는 `Name` 및 `City` 라는 멤버가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3030-121">In the following examples, the `Customer` class must exist, and must have members named `Name` and `City` that can accept string values.</span></span>  
  
 [!code-vb[VbVbalrObjectInit#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class1.vb#3)]  
  
 <span data-ttu-id="f3030-122">또는 다음 코드를 사용 하 여 동일한 결과를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3030-122">Alternatively, you can obtain the same result by using the following code:</span></span>  
  
 [!code-vb[VbVbalrObjectInit#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class1.vb#4)]  
  
 <span data-ttu-id="f3030-123">이러한 각 선언에는 매개 변수가 없는 생성자를 사용 하 여 `Customer` 개체를 만든 다음 `With` 문을 사용 하 여 `Name` 및 `City` 속성의 초기 값을 지정 하는 다음 예제와 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3030-123">Each of these declarations is equivalent to the following example, which creates a `Customer` object by using the parameterless constructor, and then specifies initial values for the `Name` and `City` properties by using a `With` statement.</span></span>  
  
 [!code-vb[VbVbalrObjectInit#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class1.vb#5)]  
  
 <span data-ttu-id="f3030-124">예를 들어 `Customer` 클래스에 `Name`에 대 한 값을 보낼 수 있는 매개 변수가 있는 생성자가 포함 된 경우 다음과 같은 방법으로 `Customer` 개체를 선언 하 고 초기화할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3030-124">If the `Customer` class contains a parameterized constructor that enables you to send in a value for `Name`, for example, you can also declare and initialize a `Customer` object in the following ways:</span></span>  
  
 [!code-vb[VbVbalrObjectInit#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class1.vb#6)]  
  
 <span data-ttu-id="f3030-125">다음 코드에 나와 있는 것 처럼 모든 속성을 초기화할 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f3030-125">You do not have to initialize all properties, as the following code shows.</span></span>  
  
 [!code-vb[VbVbalrObjectInit#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class1.vb#7)]  
  
 <span data-ttu-id="f3030-126">그러나 초기화 목록은 비워 둘 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f3030-126">However, the initialization list cannot be empty.</span></span> <span data-ttu-id="f3030-127">초기화 되지 않은 속성은 해당 기본값을 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3030-127">Uninitialized properties retain their default values.</span></span>  
  
### <a name="type-inference-with-named-types"></a><span data-ttu-id="f3030-128">명명 된 형식을 사용 하는 형식 유추</span><span class="sxs-lookup"><span data-stu-id="f3030-128">Type Inference with Named Types</span></span>  
 <span data-ttu-id="f3030-129">개체 이니셜라이저 및 로컬 형식 유추를 결합 하 여 `cust1`의 선언에 대 한 코드를 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3030-129">You can shorten the code for the declaration of `cust1` by combining object initializers and local type inference.</span></span> <span data-ttu-id="f3030-130">이렇게 하면 변수 선언에서 `As` 절을 생략할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3030-130">This enables you to omit the `As` clause in the variable declaration.</span></span> <span data-ttu-id="f3030-131">변수의 데이터 형식은 할당에 의해 생성 된 개체의 형식에서 유추 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f3030-131">The data type of the variable is inferred from the type of the object that is created by the assignment.</span></span> <span data-ttu-id="f3030-132">다음 예제에서는 `cust6` 유형을 `Customer`합니다.</span><span class="sxs-lookup"><span data-stu-id="f3030-132">In the following example, the type of `cust6` is `Customer`.</span></span>  
  
 [!code-vb[VbVbalrObjectInit#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class1.vb#8)]  
  
### <a name="remarks-about-named-types"></a><span data-ttu-id="f3030-133">명명 된 형식에 대 한 설명</span><span class="sxs-lookup"><span data-stu-id="f3030-133">Remarks About Named Types</span></span>  
  
- <span data-ttu-id="f3030-134">개체 이니셜라이저 목록에서 클래스 멤버를 두 번 이상 초기화할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f3030-134">A class member cannot be initialized more than one time in the object initializer list.</span></span> <span data-ttu-id="f3030-135">`cust7`를 선언 하면 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3030-135">The declaration of `cust7` causes an error.</span></span>  
  
     [!code-vb[VbVbalrObjectInit#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class1.vb#9)]  
  
- <span data-ttu-id="f3030-136">멤버를 사용 하 여 자체 또는 다른 필드를 초기화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3030-136">A member can be used to initialize itself or another field.</span></span> <span data-ttu-id="f3030-137">`cust8`에 대 한 다음 선언과 같이 멤버가 초기화 되기 전에 액세스 되는 경우에는 기본값이 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f3030-137">If a member is accessed before it has been initialized, as in the following declaration for `cust8`, the default value will be used.</span></span> <span data-ttu-id="f3030-138">개체 이니셜라이저를 사용 하는 선언이 처리 되는 경우 가장 먼저 적절 한 생성자가 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f3030-138">Remember that when a declaration that uses an object initializer is processed, the first thing that happens is that the appropriate constructor is invoked.</span></span> <span data-ttu-id="f3030-139">그런 다음 이니셜라이저 목록의 개별 필드가 초기화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f3030-139">After that, the individual fields in the initializer list are initialized.</span></span> <span data-ttu-id="f3030-140">다음 예에서는 `cust8`에 대해 `Name`의 기본값을 할당 하 고 초기화 된 값을 `cust9`에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3030-140">In the following examples, the default value for `Name` is assigned for `cust8`, and an initialized value is assigned in `cust9`.</span></span>  
  
     [!code-vb[VbVbalrObjectInit#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class1.vb#10)]  
  
     <span data-ttu-id="f3030-141">다음 예제에서는 `cust3` 및 `cust4`에서 매개 변수가 있는 생성자를 사용 하 여 `cust10` 및 `cust11`를 선언 하 고 초기화 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3030-141">The following example uses the parameterized constructor from `cust3` and `cust4` to declare and initialize `cust10` and `cust11`.</span></span>  
  
     [!code-vb[VbVbalrObjectInit#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class1.vb#11)]  
  
- <span data-ttu-id="f3030-142">개체 이니셜라이저는 중첩 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3030-142">Object initializers can be nested.</span></span> <span data-ttu-id="f3030-143">다음 예제에서 `AddressClass`은 `City` 및 `State`라는 두 개의 속성을 포함 하는 클래스이 고 `Customer` 클래스에는 `Address` 인스턴스인 `AddressClass`속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3030-143">In the following example, `AddressClass` is a class that has two properties, `City` and `State`, and the `Customer` class has an `Address` property that is an instance of `AddressClass`.</span></span>  
  
     [!code-vb[VbVbalrObjectInit#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class1.vb#12)]  
  
- <span data-ttu-id="f3030-144">초기화 목록은 비워 둘 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f3030-144">The initialization list cannot be empty.</span></span>  
  
- <span data-ttu-id="f3030-145">초기화 되는 인스턴스는 Object 형식일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f3030-145">The instance being initialized cannot be of type Object.</span></span>  
  
- <span data-ttu-id="f3030-146">초기화 되는 클래스 멤버는 공유 멤버, 읽기 전용 멤버, 상수 또는 메서드 호출 일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f3030-146">Class members being initialized cannot be shared members, read-only members, constants, or method calls.</span></span>  
  
- <span data-ttu-id="f3030-147">초기화 되는 클래스 멤버는 인덱싱하거나 정규화 할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f3030-147">Class members being initialized cannot be indexed or qualified.</span></span> <span data-ttu-id="f3030-148">다음 예제에서는 컴파일러 오류를 발생 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="f3030-148">The following examples raise compiler errors:</span></span>  
  
     `'' Not valid.`  
  
     `' Dim c1 = New Customer With {.OrderNumbers(0) = 148662}`  
  
     `' Dim c2 = New Customer with {.Address.City = "Springfield"}`  
  
## <a name="anonymous-types"></a><span data-ttu-id="f3030-149">익명 형식</span><span class="sxs-lookup"><span data-stu-id="f3030-149">Anonymous Types</span></span>  
 <span data-ttu-id="f3030-150">무명 형식은 개체 이니셜라이저를 사용 하 여 명시적으로 정의 하지 않고 이름을 지정 하는 새 형식의 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f3030-150">Anonymous types use object initializers to create instances of new types that you do not explicitly define and name.</span></span> <span data-ttu-id="f3030-151">대신, 컴파일러는 개체 이니셜라이저 목록에서 지정 하는 속성에 따라 형식을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3030-151">Instead, the compiler generates a type according to the properties you designate in the object initializer list.</span></span> <span data-ttu-id="f3030-152">형식의 이름을 지정 하지 않았기 때문에 *익명 형식*이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3030-152">Because the name of the type is not specified, it is referred to as an *anonymous type*.</span></span> <span data-ttu-id="f3030-153">예를 들어 다음 선언을 `cust6`의 이전 선언과 비교 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3030-153">For example, compare the following declaration to the earlier one for `cust6`.</span></span>  
  
 [!code-vb[VbVbalrObjectInit#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class1.vb#13)]  
  
 <span data-ttu-id="f3030-154">구문적으로 데이터 형식에 대 한 `New` 후에는 이름이 지정 되지 않는다는 점만 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="f3030-154">The only difference syntactically is that no name is specified after `New` for the data type.</span></span> <span data-ttu-id="f3030-155">그러나 수행 되는 작업은 매우 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="f3030-155">However, what happens is quite different.</span></span> <span data-ttu-id="f3030-156">컴파일러는 `Name` 및 `City`라는 두 개의 속성을 포함 하는 새 익명 형식을 정의 하 고 지정 된 값을 사용 하 여 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f3030-156">The compiler defines a new anonymous type that has two properties, `Name` and `City`, and creates an instance of it with the specified values.</span></span> <span data-ttu-id="f3030-157">형식 유추는 예제에서 문자열이 될 `Name` 형식과 `City`를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3030-157">Type inference determines the types of `Name` and `City` in the example to be strings.</span></span>  
  
> [!CAUTION]
> <span data-ttu-id="f3030-158">익명 형식의 이름은 컴파일러에 의해 생성 되며 컴파일 간에 달라질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3030-158">The name of the anonymous type is generated by the compiler, and may vary from compilation to compilation.</span></span> <span data-ttu-id="f3030-159">코드에서 익명 형식의 이름을 사용 하거나 사용 하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3030-159">Your code should not use or rely on the name of an anonymous type.</span></span>  
  
 <span data-ttu-id="f3030-160">형식의 이름을 사용할 수 없기 때문에 `As` 절을 사용 하 여 `cust13`를 선언할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f3030-160">Because the name of the type is not available, you cannot use an `As` clause to declare `cust13`.</span></span> <span data-ttu-id="f3030-161">해당 형식을 유추 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3030-161">Its type must be inferred.</span></span> <span data-ttu-id="f3030-162">런타임에 바인딩을 사용 하지 않으면 로컬 변수에 익명 형식의 사용이 제한 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f3030-162">Without using late binding, this limits the use of anonymous types to local variables.</span></span>  
  
 <span data-ttu-id="f3030-163">무명 형식은 LINQ 쿼리에 대 한 중요 한 지원을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3030-163">Anonymous types provide critical support for LINQ queries.</span></span> <span data-ttu-id="f3030-164">쿼리에서 익명 형식을 사용 하는 방법에 대 한 자세한 내용은 [익명 형식](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md) 및 [LINQ 소개 Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f3030-164">For more information about the use of anonymous types in queries, see [Anonymous Types](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md) and [Introduction to LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md).</span></span>  
  
### <a name="remarks-about-anonymous-types"></a><span data-ttu-id="f3030-165">익명 형식에 대 한 설명</span><span class="sxs-lookup"><span data-stu-id="f3030-165">Remarks About Anonymous Types</span></span>  
  
- <span data-ttu-id="f3030-166">일반적으로 익명 형식 선언에 있는 모든 또는 대부분의 속성은 키 속성입니다 .이 속성은 속성 이름 앞에 `Key` 키워드를 입력 하 여 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f3030-166">Typically, all or most of the properties in an anonymous type declaration will be key properties, which are indicated by typing the keyword `Key` in front of the property name.</span></span>  
  
     [!code-vb[VbVbalrObjectInit#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class1.vb#14)]  
  
     <span data-ttu-id="f3030-167">키 속성에 대 한 자세한 내용은 [키](../../../../visual-basic/language-reference/modifiers/key.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f3030-167">For more information about key properties, see [Key](../../../../visual-basic/language-reference/modifiers/key.md).</span></span>  
  
- <span data-ttu-id="f3030-168">명명 된 형식과 마찬가지로 익명 형식 정의의 이니셜라이저 목록은 적어도 하나 이상의 속성을 선언 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3030-168">Like named types, initializer lists for anonymous type definitions must declare at least one property.</span></span>  
  
     [!code-vb[VbVbalrObjectInit#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class1.vb#2)]  
  
- <span data-ttu-id="f3030-169">무명 형식의 인스턴스를 선언 하면 컴파일러는 일치 하는 익명 형식 정의를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3030-169">When an instance of an anonymous type is declared, the compiler generates a matching anonymous type definition.</span></span> <span data-ttu-id="f3030-170">속성의 이름과 데이터 형식은 인스턴스 선언에서 가져오며 컴파일러에 의해 정의에 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f3030-170">The names and data types of the properties are taken from the instance declaration, and are included by the compiler in the definition.</span></span> <span data-ttu-id="f3030-171">명명 된 형식과 같이 속성의 이름을 지정 하지 않고 미리 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3030-171">The properties are not named and defined in advance, as they would be for a named type.</span></span> <span data-ttu-id="f3030-172">해당 형식이 유추 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f3030-172">Their types are inferred.</span></span> <span data-ttu-id="f3030-173">`As` 절을 사용 하 여 속성의 데이터 형식을 지정할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f3030-173">You cannot specify the data types of the properties by using an `As` clause.</span></span>  
  
- <span data-ttu-id="f3030-174">익명 형식은 여러 가지 다른 방법으로 해당 속성의 이름과 값을 설정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3030-174">Anonymous types can also establish the names and values of their properties in several other ways.</span></span> <span data-ttu-id="f3030-175">예를 들어, 무명 형식 속성은 변수의 이름과 값 또는 다른 개체의 속성 이름 및 값을 모두 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3030-175">For example, an anonymous type property can take both the name and the value of a variable, or the name and value of a property of another object.</span></span>  
  
     [!code-vb[VbVbalrObjectInit#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class1.vb#15)]  
  
     <span data-ttu-id="f3030-176">무명 형식의 속성을 정의 하는 옵션에 대 한 자세한 내용은 [방법: 익명 형식 선언에서 속성 이름 및 형식 유추](../../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f3030-176">For more information about the options for defining properties in anonymous types, see [How to: Infer Property Names and Types in Anonymous Type Declarations](../../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3030-177">참조</span><span class="sxs-lookup"><span data-stu-id="f3030-177">See also</span></span>

- [<span data-ttu-id="f3030-178">지역 형식 유추</span><span class="sxs-lookup"><span data-stu-id="f3030-178">Local Type Inference</span></span>](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [<span data-ttu-id="f3030-179">익명 형식</span><span class="sxs-lookup"><span data-stu-id="f3030-179">Anonymous Types</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
- [<span data-ttu-id="f3030-180">Visual Basic의 LINQ 소개</span><span class="sxs-lookup"><span data-stu-id="f3030-180">Introduction to LINQ in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="f3030-181">방법: 익명 형식 선언에서 속성 이름 및 형식 유추</span><span class="sxs-lookup"><span data-stu-id="f3030-181">How to: Infer Property Names and Types in Anonymous Type Declarations</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md)
- [<span data-ttu-id="f3030-182">키</span><span class="sxs-lookup"><span data-stu-id="f3030-182">Key</span></span>](../../../../visual-basic/language-reference/modifiers/key.md)
- [<span data-ttu-id="f3030-183">방법: 개체 이니셜라이저를 사용하여 개체 선언</span><span class="sxs-lookup"><span data-stu-id="f3030-183">How to: Declare an Object by Using an Object Initializer</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-declare-an-object-by-using-an-object-initializer.md)
