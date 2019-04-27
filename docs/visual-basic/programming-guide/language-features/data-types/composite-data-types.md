---
title: 복합 데이터 형식(Visual Basic)
ms.date: 04/25/2017
helpviewer_keywords:
- classes [Visual Basic], composite data types
- composite types [Visual Basic]
- composite data types [Visual Basic]
- data types [Visual Basic], composite
- arrays [Visual Basic], composite data types
- structures [Visual Basic], composite data types
- classes [Visual Basic], composite types
- types [Visual Basic], composite
ms.assetid: 62970f2e-52c0-4369-8963-613820f1f434
ms.openlocfilehash: ea719b60a6bcd40494666d4923fad296a8ddae70
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61907389"
---
# <a name="composite-data-types-visual-basic"></a><span data-ttu-id="5fcea-102">복합 데이터 형식(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5fcea-102">Composite Data Types (Visual Basic)</span></span>
<span data-ttu-id="5fcea-103">기본 데이터 형식 Visual Basic에서 제공 하는 것 외에도 수 조합 하 여 만들려는 다른 형식의 항목 *복합 데이터 형식* 클래스, 구조체 및 배열 등입니다.</span><span class="sxs-lookup"><span data-stu-id="5fcea-103">In addition to the elementary data types Visual Basic supplies, you can also assemble items of different types to create *composite data types* such as structures, arrays, and classes.</span></span> <span data-ttu-id="5fcea-104">기본 형식에서 다른 복합 형식의 복합 데이터 형식을 빌드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5fcea-104">You can build composite data types from elementary types and from other composite types.</span></span> <span data-ttu-id="5fcea-105">예를 들어, 배열 멤버를 사용 하 여 한 구조 요소, 배열 또는 구조를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5fcea-105">For example, you can define an array of structure elements, or a structure with array members.</span></span>  
  
## <a name="data-types"></a><span data-ttu-id="5fcea-106">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="5fcea-106">Data Types</span></span>  
 <span data-ttu-id="5fcea-107">복합 형식 구성 요소 데이터 형식에서 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="5fcea-107">A composite type is different from the data type of any of its components.</span></span> <span data-ttu-id="5fcea-108">예를 들어 배열을 `Integer` 요소는 아닙니다는 `Integer` 데이터 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="5fcea-108">For example, an array of `Integer` elements is not of the `Integer` data type.</span></span>  
  
 <span data-ttu-id="5fcea-109">배열 데이터 형식은 요소 형식, 괄호 및 쉼표를 사용 하 여 필요에 따라 일반적으로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5fcea-109">An array data type is normally represented using the element type, parentheses, and commas as necessary.</span></span> <span data-ttu-id="5fcea-110">예를 들어, 1 차원 배열이 `String` 요소가 표시 됩니다 `String()`, 및 2 차원 배열을 `Boolean` 요소가 표시 됩니다 `Boolean(,)`합니다.</span><span class="sxs-lookup"><span data-stu-id="5fcea-110">For example, a one-dimensional array of `String` elements is represented as `String()`, and a two-dimensional array of `Boolean` elements is represented as `Boolean(,)`.</span></span>  
  
## <a name="structure-types"></a><span data-ttu-id="5fcea-111">구조체 형식</span><span class="sxs-lookup"><span data-stu-id="5fcea-111">Structure Types</span></span>  
 <span data-ttu-id="5fcea-112">모든 구조를 포함 하는 단일 데이터 형식은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5fcea-112">There is no single data type comprising all structures.</span></span> <span data-ttu-id="5fcea-113">대신 구조체의 각 정의 두 구조체가 동일한 순서로 동일한 요소를 정의 하는 경우에 고유 데이터 형식을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="5fcea-113">Instead, each definition of a structure represents a unique data type, even if two structures define identical elements in the same order.</span></span> <span data-ttu-id="5fcea-114">그러나 같은 구조의 두 개 이상의 인스턴스를 만드는 경우 Visual Basic 데이터 형식이 동일한 것으로 간주 합니다.</span><span class="sxs-lookup"><span data-stu-id="5fcea-114">However, if you create two or more instances of the same structure, Visual Basic considers them to be of the same data type.</span></span>  
  
## <a name="tuples"></a><span data-ttu-id="5fcea-115">튜플</span><span class="sxs-lookup"><span data-stu-id="5fcea-115">Tuples</span></span>

<span data-ttu-id="5fcea-116">튜플은은 형식이 미리 정의 된 두 개 이상의 필드를 포함 하는 간단한 구조체입니다.</span><span class="sxs-lookup"><span data-stu-id="5fcea-116">A tuple is a lightweight structure that contains two or more fields whose types are predefined.</span></span> <span data-ttu-id="5fcea-117">튜플은 Visual Basic 2017부터 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5fcea-117">Tuples are supported starting with Visual Basic 2017.</span></span> <span data-ttu-id="5fcea-118">참조로 인수를 전달할 필요 없이 더 많은 가중치 클래스 또는 구조체에서 반환 되는 필드를 패키징 단일 메서드 호출에서 여러 값을 반환할 튜플 가장 흔히 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5fcea-118">Tuples are most commonly used to return multiple values from a single method call without having to pass arguments by reference or packaging the returned fields in a more heavy-weight class or structure.</span></span> <span data-ttu-id="5fcea-119">참조 된 [튜플](tuples.md) 튜플에 대 한 자세한 내용은 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="5fcea-119">See the [Tuples](tuples.md) topic for more information on tuples.</span></span>

## <a name="array-types"></a><span data-ttu-id="5fcea-120">배열 형식</span><span class="sxs-lookup"><span data-stu-id="5fcea-120">Array Types</span></span>  
 <span data-ttu-id="5fcea-121">모든 배열을 포함 하는 단일 데이터 형식은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5fcea-121">There is no single data type comprising all arrays.</span></span> <span data-ttu-id="5fcea-122">데이터 형식의 배열의 특정 인스턴스를 다음에 의해 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5fcea-122">The data type of a particular instance of an array is determined by the following:</span></span>  
  
-   <span data-ttu-id="5fcea-123">배열 이라는 사실</span><span class="sxs-lookup"><span data-stu-id="5fcea-123">The fact of being an array</span></span>  
  
-   <span data-ttu-id="5fcea-124">배열의 차수 (차원 수)</span><span class="sxs-lookup"><span data-stu-id="5fcea-124">The rank (number of dimensions) of the array</span></span>  
  
-   <span data-ttu-id="5fcea-125">배열의 요소 형식</span><span class="sxs-lookup"><span data-stu-id="5fcea-125">The element type of the array</span></span>  
  
 <span data-ttu-id="5fcea-126">특히 지정 된 차원의 길이 인스턴스의 데이터 형식의 일부가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="5fcea-126">In particular, the length of a given dimension is not part of the instance's data type.</span></span> <span data-ttu-id="5fcea-127">다음은 이에 대한 예입니다.</span><span class="sxs-lookup"><span data-stu-id="5fcea-127">The following example illustrates this.</span></span>  
  
```  
Dim arrayA( ) As Byte = New Byte(12) {}  
Dim arrayB( ) As Byte = New Byte(100) {}  
Dim arrayC( ) As Short = New Short(100) {}  
Dim arrayD( , ) As Short  
Dim arrayE( , ) As Short = New Short(4, 10) {}  
```  
  
 <span data-ttu-id="5fcea-128">앞의 예제에서 배열 변수 `arrayA` 하 고 `arrayB` 동일한 데이터 형식으로 간주 됩니다- `Byte()` -길이가 다른 초기화 되는 경우에 합니다.</span><span class="sxs-lookup"><span data-stu-id="5fcea-128">In the preceding example, array variables `arrayA` and `arrayB` are considered to be of the same data type — `Byte()` — even though they are initialized to different lengths.</span></span> <span data-ttu-id="5fcea-129">변수 `arrayB` 고 `arrayC` 는 요소 형식이 다른 동일한 형식이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="5fcea-129">Variables `arrayB` and `arrayC` are not of the same type because their element types are different.</span></span> <span data-ttu-id="5fcea-130">변수 `arrayC` 및 `arrayD` 는 차수가 다른 동일한 형식이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="5fcea-130">Variables `arrayC` and `arrayD` are not of the same type because their ranks are different.</span></span> <span data-ttu-id="5fcea-131">변수 `arrayD` 하 고 `arrayE` 형식이 같은- `Short(,)` -같기 때문에 해당 순위 및 요소 형식에도 `arrayD` 아직 초기화 되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="5fcea-131">Variables `arrayD` and `arrayE` have the same type — `Short(,)` — because their ranks and element types are the same, even though `arrayD` is not yet initialized.</span></span>  
  
 <span data-ttu-id="5fcea-132">배열에 대 한 자세한 내용은 참조 하세요. [배열](../../../../visual-basic/programming-guide/language-features/arrays/index.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="5fcea-132">For more information on arrays, see [Arrays](../../../../visual-basic/programming-guide/language-features/arrays/index.md).</span></span>  
  
## <a name="class-types"></a><span data-ttu-id="5fcea-133">클래스 형식</span><span class="sxs-lookup"><span data-stu-id="5fcea-133">Class Types</span></span>  
 <span data-ttu-id="5fcea-134">모든 클래스를 포함 하는 단일 데이터 형식은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5fcea-134">There is no single data type comprising all classes.</span></span> <span data-ttu-id="5fcea-135">하나의 클래스에서는 다른 클래스에서 상속할 수 있지만 각각 별도 데이터 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="5fcea-135">Although one class can inherit from another class, each is a separate data type.</span></span> <span data-ttu-id="5fcea-136">동일한 클래스의 여러 인스턴스는 동일한 데이터 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="5fcea-136">Multiple instances of the same class are of the same data type.</span></span> <span data-ttu-id="5fcea-137">다른 하나의 클래스 인스턴스 변수를 할당 하는 경우 뿐 아니라 동일한 데이터 형식이 있는지, 메모리에서 동일한 클래스 인스턴스를 가리키도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="5fcea-137">If you assign one class instance variable to another, not only do they have the same data type, they point to the same class instance in memory.</span></span>  
  
 <span data-ttu-id="5fcea-138">클래스에 대 한 자세한 내용은 참조 하세요. [개체 및 클래스](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="5fcea-138">For more information on classes, see [Objects and Classes](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5fcea-139">참고자료</span><span class="sxs-lookup"><span data-stu-id="5fcea-139">See also</span></span>

- [<span data-ttu-id="5fcea-140">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="5fcea-140">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
- [<span data-ttu-id="5fcea-141">기본 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="5fcea-141">Elementary Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)
- [<span data-ttu-id="5fcea-142">Visual Basic의 제네릭 형식</span><span class="sxs-lookup"><span data-stu-id="5fcea-142">Generic Types in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [<span data-ttu-id="5fcea-143">Value Types and Reference Types</span><span class="sxs-lookup"><span data-stu-id="5fcea-143">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
- [<span data-ttu-id="5fcea-144">Visual Basic의 형식 변환</span><span class="sxs-lookup"><span data-stu-id="5fcea-144">Type Conversions in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
- [<span data-ttu-id="5fcea-145">구조체</span><span class="sxs-lookup"><span data-stu-id="5fcea-145">Structures</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="5fcea-146">데이터 형식 문제 해결</span><span class="sxs-lookup"><span data-stu-id="5fcea-146">Troubleshooting Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [<span data-ttu-id="5fcea-147">방법: 변수에 두 개 이상의 값 사용</span><span class="sxs-lookup"><span data-stu-id="5fcea-147">How to: Hold More Than One Value in a Variable</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-hold-more-than-one-value-in-a-variable.md)
