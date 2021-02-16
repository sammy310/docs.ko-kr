---
description: '자세한 정보: 기타 데이터 형식 (Visual Basic)'
title: 기타 데이터 형식
ms.date: 07/20/2015
helpviewer_keywords:
- Object data type [Visual Basic], data types
- data types [Visual Basic], choosing
ms.assetid: 64c71a12-9057-4dbf-baca-7379c4aada69
ms.openlocfilehash: 3875a3fc3027d573013470cb96c9482a0be6cbbf
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100461998"
---
# <a name="miscellaneous-data-types-visual-basic"></a><span data-ttu-id="7216d-103">기타 데이터 형식(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7216d-103">Miscellaneous Data Types (Visual Basic)</span></span>

<span data-ttu-id="7216d-104">Visual Basic는 숫자나 문자를 중심으로 하지 않는 여러 데이터 형식을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="7216d-104">Visual Basic supplies several data types that are not oriented toward numbers or characters.</span></span> <span data-ttu-id="7216d-105">대신 예/아니요 값, 날짜/시간 값 및 개체 주소와 같은 특수 한 데이터를 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="7216d-105">Instead, they deal with specialized data such as yes/no values, date/time values, and object addresses.</span></span>  
  
 <span data-ttu-id="7216d-106">Visual Basic 데이터 형식을 나란히 비교 하 여 보여 주는 표는 [데이터 형식](../../../language-reference/data-types/index.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7216d-106">For a table showing a side-by-side comparison of the Visual Basic data types, see [Data Types](../../../language-reference/data-types/index.md).</span></span>  
  
## <a name="boolean-type"></a><span data-ttu-id="7216d-107">부울 형식</span><span class="sxs-lookup"><span data-stu-id="7216d-107">Boolean Type</span></span>  

 <span data-ttu-id="7216d-108">[부울 데이터 형식은](../../../language-reference/data-types/boolean-data-type.md) 또는로 해석 되는 부호 없는 값입니다 `True` `False` .</span><span class="sxs-lookup"><span data-stu-id="7216d-108">The [Boolean Data Type](../../../language-reference/data-types/boolean-data-type.md) is an unsigned value that is interpreted as either `True` or `False`.</span></span> <span data-ttu-id="7216d-109">데이터 너비는 구현 하는 플랫폼에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="7216d-109">Its data width depends on the implementing platform.</span></span> <span data-ttu-id="7216d-110">변수에 true/false, 예/아니요 또는 설정/해제와 같은 두 가지 상태 값만 포함 될 수 있는 경우로 선언 `Boolean` 합니다.</span><span class="sxs-lookup"><span data-stu-id="7216d-110">If a variable can contain only two-state values such as true/false, yes/no, or on/off, declare it as `Boolean`.</span></span>  
  
## <a name="date-type"></a><span data-ttu-id="7216d-111">날짜 형식</span><span class="sxs-lookup"><span data-stu-id="7216d-111">Date Type</span></span>  

 <span data-ttu-id="7216d-112">날짜 [데이터 형식은](../../../language-reference/data-types/date-data-type.md) 날짜 및 시간 정보를 모두 포함 하는 64 비트 값입니다.</span><span class="sxs-lookup"><span data-stu-id="7216d-112">The [Date Data Type](../../../language-reference/data-types/date-data-type.md) is a 64-bit value that holds both date and time information.</span></span> <span data-ttu-id="7216d-113">각 증가값은 그레고리오 력 달력에서 1 년 1 월 1 일의 시작 (12:00 AM) 이후 경과 된 시간 100 나노초를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="7216d-113">Each increment represents 100 nanoseconds of elapsed time since the beginning (12:00 AM) of January 1 of the year 1 in the Gregorian calendar.</span></span> <span data-ttu-id="7216d-114">변수에 날짜 값, 시간 값 또는 둘 다 포함 될 수 있는 경우로 선언 `Date` 합니다.</span><span class="sxs-lookup"><span data-stu-id="7216d-114">If a variable can contain a date value, a time value, or both, declare it as `Date`.</span></span>  
  
## <a name="object-type"></a><span data-ttu-id="7216d-115">개체 유형</span><span class="sxs-lookup"><span data-stu-id="7216d-115">Object Type</span></span>  

 <span data-ttu-id="7216d-116">[개체 데이터 형식은](../../../language-reference/data-types/object-data-type.md) 응용 프로그램이 나 다른 응용 프로그램 내에서 개체 인스턴스를 가리키는 32 비트 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="7216d-116">The [Object Data Type](../../../language-reference/data-types/object-data-type.md) is a 32-bit address that points to an object instance within your application or in some other application.</span></span> <span data-ttu-id="7216d-117">`Object`변수는 응용 프로그램에서 인식 하는 개체 또는 모든 데이터 형식의 데이터를 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7216d-117">An `Object` variable can refer to any object your application recognizes, or to data of any data type.</span></span> <span data-ttu-id="7216d-118">여기에는, 및 구조체 인스턴스와 같은 *값 형식과* 및 등의 `Integer` `Boolean` 클래스에서 만든 개체의 인스턴스인 *참조 형식이* 모두 포함 됩니다 `String` <xref:System.Windows.Forms.Form> .</span><span class="sxs-lookup"><span data-stu-id="7216d-118">This includes both *value types*, such as `Integer`, `Boolean`, and structure instances, and *reference types*, which are instances of objects created from classes such as `String` and <xref:System.Windows.Forms.Form>, and array instances.</span></span>  
  
 <span data-ttu-id="7216d-119">변수가 컴파일 시간에 알 수 없는 클래스의 인스턴스에 대 한 포인터를 저장 하거나 다양 한 데이터 형식의 데이터를 가리킬 수 있는 경우로 선언 `Object` 합니다.</span><span class="sxs-lookup"><span data-stu-id="7216d-119">If a variable stores a pointer to an instance of a class that you do not know at compile time, or if it can point to data of various data types, declare it as `Object`.</span></span>  
  
 <span data-ttu-id="7216d-120">데이터 형식의 장점은 데이터 형식의 데이터 `Object` 를 저장 하는 데 사용할 수 있다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="7216d-120">The advantage of the `Object` data type is that you can use it to store data of any data type.</span></span> <span data-ttu-id="7216d-121">단점은 실행 시간을 더 많이 사용 하 고 응용 프로그램을 느리게 수행 하는 추가 작업을 수행 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="7216d-121">The disadvantage is that you incur extra operations that take more execution time and make your application perform slower.</span></span> <span data-ttu-id="7216d-122">`Object`값 형식에 대 한 변수를 사용 하는 경우 *boxing* 및 *unboxing* 을 발생 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="7216d-122">If you use an `Object` variable for value types, you incur *boxing* and *unboxing*.</span></span> <span data-ttu-id="7216d-123">참조 형식에 사용 하는 경우 *런타임에 바인딩이* 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="7216d-123">If you use it for reference types, you incur *late binding*.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7216d-124">추가 정보</span><span class="sxs-lookup"><span data-stu-id="7216d-124">See also</span></span>

- [<span data-ttu-id="7216d-125">형식 문자</span><span class="sxs-lookup"><span data-stu-id="7216d-125">Type Characters</span></span>](type-characters.md)
- [<span data-ttu-id="7216d-126">기본 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="7216d-126">Elementary Data Types</span></span>](elementary-data-types.md)
- [<span data-ttu-id="7216d-127">숫자 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="7216d-127">Numeric Data Types</span></span>](numeric-data-types.md)
- [<span data-ttu-id="7216d-128">문자 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="7216d-128">Character Data Types</span></span>](character-data-types.md)
- [<span data-ttu-id="7216d-129">데이터 형식 문제 해결</span><span class="sxs-lookup"><span data-stu-id="7216d-129">Troubleshooting Data Types</span></span>](troubleshooting-data-types.md)
- [<span data-ttu-id="7216d-130">초기 바인딩 및 런타임에 바인딩</span><span class="sxs-lookup"><span data-stu-id="7216d-130">Early and Late Binding</span></span>](../early-late-binding/index.md)
