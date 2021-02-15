---
description: '자세한 정보: 개체 변수 값 (Visual Basic)'
title: 개체 변수 값
ms.date: 07/20/2015
helpviewer_keywords:
- object variables [Visual Basic], values
- values [Visual Basic], of object variables
- data types [Visual Basic], object variable
- variables [Visual Basic], object
ms.assetid: 31555704-58a3-49f1-9a0a-6421f605664f
ms.openlocfilehash: 3259a0b04ed629feea89c1a3e9dba69ed7d226f6
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100481677"
---
# <a name="object-variable-values-visual-basic"></a><span data-ttu-id="5d56e-103">개체 변수 값(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5d56e-103">Object Variable Values (Visual Basic)</span></span>

<span data-ttu-id="5d56e-104">[Object 데이터 형식의](../../../language-reference/data-types/object-data-type.md) 변수는 모든 형식의 데이터를 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d56e-104">A variable of the [Object Data Type](../../../language-reference/data-types/object-data-type.md) can refer to data of any type.</span></span> <span data-ttu-id="5d56e-105">변수에 저장 하는 값은 `Object` 메모리의 다른 위치에 유지 되는 반면 변수 자체는 데이터에 대 한 포인터를 보유 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d56e-105">The value you store in an `Object` variable is kept elsewhere in memory, while the variable itself holds a pointer to the data.</span></span>  
  
## <a name="object-classifier-functions"></a><span data-ttu-id="5d56e-106">개체 분류자 함수</span><span class="sxs-lookup"><span data-stu-id="5d56e-106">Object Classifier Functions</span></span>  

 <span data-ttu-id="5d56e-107">Visual Basic는 `Object` 다음 표와 같이 변수가 참조 하는 내용에 대 한 정보를 반환 하는 함수를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d56e-107">Visual Basic supplies functions that return information about what an `Object` variable refers to, as shown in the following table.</span></span>  
  
|<span data-ttu-id="5d56e-108">기능</span><span class="sxs-lookup"><span data-stu-id="5d56e-108">Function</span></span>|<span data-ttu-id="5d56e-109">개체 변수가 참조 하는 경우 True를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d56e-109">Returns True if the Object variable refers to</span></span>|  
|--------------|---------------------------------------------------|  
|<xref:Microsoft.VisualBasic.Information.IsArray%2A>|<span data-ttu-id="5d56e-110">단일 값이 아닌 값의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="5d56e-110">An array of values, rather than a single value</span></span>|  
|<xref:Microsoft.VisualBasic.Information.IsDate%2A>|<span data-ttu-id="5d56e-111">날짜 [데이터 형식](../../../language-reference/data-types/date-data-type.md) 값 또는 날짜 및 시간 값으로 해석 될 수 있는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="5d56e-111">A [Date Data Type](../../../language-reference/data-types/date-data-type.md) value, or a string that can be interpreted as a date and time value</span></span>|  
|<xref:Microsoft.VisualBasic.Information.IsDBNull%2A>|<span data-ttu-id="5d56e-112"><xref:System.DBNull>누락 되거나 존재 하지 않는 데이터를 나타내는 형식의 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="5d56e-112">An object of type <xref:System.DBNull>, which represents missing or nonexistent data</span></span>|  
|<xref:Microsoft.VisualBasic.Information.IsError%2A>|<span data-ttu-id="5d56e-113">에서 파생 되는 예외 개체입니다. <xref:System.Exception></span><span class="sxs-lookup"><span data-stu-id="5d56e-113">An exception object, which derives from <xref:System.Exception></span></span>|  
|<xref:Microsoft.VisualBasic.Information.IsNothing%2A>|<span data-ttu-id="5d56e-114">[Nothing](../../../language-reference/nothing.md), 즉 변수에 현재 할당 된 개체가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5d56e-114">[Nothing](../../../language-reference/nothing.md), that is, no object is currently assigned to the variable</span></span>|  
|<xref:Microsoft.VisualBasic.Information.IsNumeric%2A>|<span data-ttu-id="5d56e-115">숫자 또는 숫자로 해석할 수 있는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="5d56e-115">A number, or a string that can be interpreted as a number</span></span>|  
|<xref:Microsoft.VisualBasic.Information.IsReference%2A>|<span data-ttu-id="5d56e-116">참조 형식 (예: 문자열, 배열, 대리자 또는 클래스 형식)</span><span class="sxs-lookup"><span data-stu-id="5d56e-116">A reference type (such as a string, array, delegate, or class type)</span></span>|  
  
 <span data-ttu-id="5d56e-117">이러한 함수를 사용 하 여 작업 또는 프로시저에 잘못 된 값을 제출 하지 않도록 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d56e-117">You can use these functions to avoid submitting an invalid value to an operation or a procedure.</span></span>  
  
## <a name="typeof-operator"></a><span data-ttu-id="5d56e-118">TypeOf 연산자</span><span class="sxs-lookup"><span data-stu-id="5d56e-118">TypeOf Operator</span></span>  

 <span data-ttu-id="5d56e-119">[TypeOf 연산자](../../../language-reference/operators/typeof-operator.md) 를 사용 하 여 현재 개체 변수가 특정 데이터 형식을 참조 하는지 여부를 확인할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d56e-119">You can also use the [TypeOf Operator](../../../language-reference/operators/typeof-operator.md) to determine whether an object variable currently refers to a specific data type.</span></span> <span data-ttu-id="5d56e-120">`TypeOf`... `Is` 식은 `True` 피연산자의 런타임 형식이에서 파생 되거나 지정 된 형식을 구현 하는 경우로 평가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5d56e-120">The `TypeOf`...`Is` expression evaluates to `True` if the run-time type of the operand is derived from or implements the specified type.</span></span>  
  
 <span data-ttu-id="5d56e-121">다음 예에서는 `TypeOf` 값 및 참조 형식을 참조 하는 개체 변수에를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d56e-121">The following example uses `TypeOf` on object variables referring to value and reference types.</span></span>  
  
```vb  
' The following statement puts a value type (Integer) in an Object variable.  
Dim num As Object = 10  
' The following statement puts a reference type (Form) in an Object variable.  
Dim frm As Object = New Form()  
If TypeOf num Is Long Then Debug.WriteLine("num is Long")  
If TypeOf num Is Integer Then Debug.WriteLine("num is Integer")  
If TypeOf num Is Short Then Debug.WriteLine("num is Short")  
If TypeOf num Is Object Then Debug.WriteLine("num is Object")  
If TypeOf frm Is Form Then Debug.WriteLine("frm is Form")  
If TypeOf frm Is Label Then Debug.WriteLine("frm is Label")  
If TypeOf frm Is Object Then Debug.WriteLine("frm is Object")  
```  
  
 <span data-ttu-id="5d56e-122">앞의 예제에서는 **디버그** 창에 다음 줄을 씁니다.</span><span class="sxs-lookup"><span data-stu-id="5d56e-122">The preceding example writes the following lines to the **Debug** window:</span></span>  
  
 `num is Integer`  
  
 `num is Object`  
  
 `frm is Form`  
  
 `frm is Object`  
  
 <span data-ttu-id="5d56e-123">개체 변수는 `num` 형식의 데이터를 참조 하 `Integer` 고 `frm` 클래스의 개체를 참조 <xref:System.Windows.Forms.Form> 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d56e-123">The object variable `num` refers to data of type `Integer`, and `frm` refers to an object of class <xref:System.Windows.Forms.Form>.</span></span>  
  
## <a name="object-arrays"></a><span data-ttu-id="5d56e-124">개체 배열</span><span class="sxs-lookup"><span data-stu-id="5d56e-124">Object Arrays</span></span>  

 <span data-ttu-id="5d56e-125">변수 배열을 선언 하 고 사용할 수 있습니다 `Object` .</span><span class="sxs-lookup"><span data-stu-id="5d56e-125">You can declare and use an array of `Object` variables.</span></span> <span data-ttu-id="5d56e-126">이는 다양 한 데이터 형식 및 개체 클래스를 처리 해야 하는 경우에 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d56e-126">This is useful when you need to handle a variety of data types and object classes.</span></span> <span data-ttu-id="5d56e-127">배열의 모든 요소에는 동일한 선언 된 데이터 형식이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d56e-127">All the elements in an array must have the same declared data type.</span></span> <span data-ttu-id="5d56e-128">이 데이터 형식을로 선언 하면 `Object` 개체와 클래스 인스턴스를 배열에 있는 다른 데이터 형식과 함께 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d56e-128">Declaring this data type as `Object` allows you to store objects and class instances alongside other data types in the array.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d56e-129">추가 정보</span><span class="sxs-lookup"><span data-stu-id="5d56e-129">See also</span></span>

- [<span data-ttu-id="5d56e-130">개체 변수</span><span class="sxs-lookup"><span data-stu-id="5d56e-130">Object Variables</span></span>](object-variables.md)
- [<span data-ttu-id="5d56e-131">개체 변수 선언</span><span class="sxs-lookup"><span data-stu-id="5d56e-131">Object Variable Declaration</span></span>](object-variable-declaration.md)
- [<span data-ttu-id="5d56e-132">개체 변수 할당</span><span class="sxs-lookup"><span data-stu-id="5d56e-132">Object Variable Assignment</span></span>](object-variable-assignment.md)
- [<span data-ttu-id="5d56e-133">방법: 개체의 현재 인스턴스 참조</span><span class="sxs-lookup"><span data-stu-id="5d56e-133">How to: Refer to the Current Instance of an Object</span></span>](how-to-refer-to-the-current-instance-of-an-object.md)
- [<span data-ttu-id="5d56e-134">방법: 개체 변수가 참조하는 형식 확인</span><span class="sxs-lookup"><span data-stu-id="5d56e-134">How to: Determine What Type an Object Variable Refers To</span></span>](how-to-determine-what-type-an-object-variable-refers-to.md)
- [<span data-ttu-id="5d56e-135">방법: 두 개체가 관련이 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="5d56e-135">How to: Determine Whether Two Objects Are Related</span></span>](how-to-determine-whether-two-objects-are-related.md)
- [<span data-ttu-id="5d56e-136">방법: 두 개체가 동일한지 확인</span><span class="sxs-lookup"><span data-stu-id="5d56e-136">How to: Determine Whether Two Objects Are Identical</span></span>](how-to-determine-whether-two-objects-are-identical.md)
- [<span data-ttu-id="5d56e-137">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="5d56e-137">Data Types</span></span>](../data-types/index.md)
