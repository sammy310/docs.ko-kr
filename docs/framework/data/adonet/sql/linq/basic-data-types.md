---
description: '자세한 정보: 기본 데이터 형식'
title: 기본 데이터 형식
ms.date: 03/30/2017
ms.assetid: eca2c472-9548-4800-bd31-5d8d9f11752b
ms.openlocfilehash: d0236bc315c884d9e70c3c4a75755c3b66b1f2e4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99712612"
---
# <a name="basic-data-types"></a><span data-ttu-id="a15df-103">기본 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="a15df-103">Basic Data Types</span></span>

<span data-ttu-id="a15df-104">LINQ to SQL 쿼리는 Microsoft SQL Server에서 실행되기 전에 Transact-SQL로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="a15df-104">Because LINQ to SQL queries translate to Transact-SQL before they are executed on the Microsoft SQL Server.</span></span> <span data-ttu-id="a15df-105">따라서 LINQ to SQL에서는 SQL Server에서 기본 데이터 형식에 대해 지원하는 기본 제공 함수 대부분을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="a15df-105">LINQ to SQL supports much of the same built-in functionality that SQL Server does for basic data types.</span></span>  
  
## <a name="casting"></a><span data-ttu-id="a15df-106">캐스팅</span><span class="sxs-lookup"><span data-stu-id="a15df-106">Casting</span></span>  

 <span data-ttu-id="a15df-107">SQL Server 내에 비슷한 유효한 변환이 있는 경우 암시적 또는 명시적 캐스팅을 사용하여 소스 CLR 형식에서 대상 CLR 형식으로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a15df-107">Implicit or explicit casts are enabled from a source CLR type to a target CLR type if there is a similar valid conversion within SQL Server.</span></span> <span data-ttu-id="a15df-108">CLR 캐스팅에 대 한 자세한 내용은 [CType 함수](../../../../../visual-basic/language-reference/functions/ctype-function.md) (Visual Basic) 및 [형식 테스트 및 캐스트 연산자](../../../../../csharp/language-reference/operators/type-testing-and-cast.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a15df-108">For more information about CLR casting, see [CType Function](../../../../../visual-basic/language-reference/functions/ctype-function.md) (Visual Basic) and [Type-testing and cast operators](../../../../../csharp/language-reference/operators/type-testing-and-cast.md).</span></span> <span data-ttu-id="a15df-109">변환 후 캐스팅은 CLR 식에서 수행된 작업 동작을 변경하여 기본적으로 대상 형식에 매핑되는 다른 CLR 식의 동작과 일치시킵니다.</span><span class="sxs-lookup"><span data-stu-id="a15df-109">After conversion, casts change the behavior of operations performed on a CLR expression to match the behavior of other CLR expressions that naturally map to the destination type.</span></span> <span data-ttu-id="a15df-110">캐스팅은 또한 상속 매핑의 컨텍스트에서 변환 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="a15df-110">Casts are also translatable in the context of inheritance mapping.</span></span> <span data-ttu-id="a15df-111">개체는 보다 구체적인 엔터티 하위 형식에 캐스팅되어 하위 형식의 특정 데이터에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a15df-111">Objects can be cast to more specific entity subtypes so that their subtype-specific data can be accessed.</span></span>  
  
## <a name="equality-operators"></a><span data-ttu-id="a15df-112">같음 연산자</span><span class="sxs-lookup"><span data-stu-id="a15df-112">Equality Operators</span></span>  

 <span data-ttu-id="a15df-113">LINQ to SQL에서는 LINQ to SQL 쿼리 내의 기본 데이터 형식에 다음과 같은 같음 연산자를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="a15df-113">LINQ to SQL supports the following equality operators on basic data types inside LINQ to SQL queries:</span></span>  
  
- <span data-ttu-id="a15df-114">같음 및 같지 않음 연산자: 같음 및 같지 않음 연산자는 숫자, <xref:System.Boolean> , <xref:System.DateTime> 및 형식에 대해 지원 됩니다 <xref:System.TimeSpan> .</span><span class="sxs-lookup"><span data-stu-id="a15df-114">Equal and Inequality Operator: Equality and inequality operators are supported for numeric, <xref:System.Boolean>, <xref:System.DateTime>, and <xref:System.TimeSpan> types.</span></span> <span data-ttu-id="a15df-115">Visual Basic 연산자 및에 대 한 자세한 `=` `<>` 내용은 [비교 연산자](../../../../../visual-basic/language-reference/operators/comparison-operators.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a15df-115">For more about Visual Basic operators `=` and `<>`, see [Comparison Operators](../../../../../visual-basic/language-reference/operators/comparison-operators.md).</span></span> <span data-ttu-id="a15df-116">C # 비교 연산자 및에 대 한 자세한 내용은 `==` `!=` [같음 연산자](../../../../../csharp/language-reference/operators/equality-operators.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a15df-116">For more information about C# comparison operators `==` and `!=`, see [Equality operators](../../../../../csharp/language-reference/operators/equality-operators.md).</span></span>
  
- <span data-ttu-id="a15df-117">Is 연산자: `IS` 연산자에서는 상속 매핑이 사용되는 경우 변환이 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="a15df-117">Is operator: The `IS` operator has a supported translation when inheritance mapping is being used.</span></span> <span data-ttu-id="a15df-118">개체가 특정 엔터티 형식인지 여부를 확인하기 위해 판별자 열을 직접 테스트하는 대신에 사용되어 판별자 열에 대한 확인으로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="a15df-118">It can be used instead of directly testing the discriminator column to determine whether an object is of a specific entity type, and is translated to a check on the discriminator column.</span></span> <span data-ttu-id="a15df-119">Visual Basic 및 c # Is 연산자에 대 한 자세한 내용은 [Is 연산자](../../../../../visual-basic/language-reference/operators/is-operator.md) 및 [is를](../../../../../csharp/language-reference/operators/type-testing-and-cast.md#is-operator)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a15df-119">For more information about the Visual Basic and C# Is operators, see [Is Operator](../../../../../visual-basic/language-reference/operators/is-operator.md) and [is](../../../../../csharp/language-reference/operators/type-testing-and-cast.md#is-operator).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a15df-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a15df-120">See also</span></span>

- [<span data-ttu-id="a15df-121">SQL-CLR 형식 매핑</span><span class="sxs-lookup"><span data-stu-id="a15df-121">SQL-CLR Type Mapping</span></span>](sql-clr-type-mapping.md)
- [<span data-ttu-id="a15df-122">데이터 형식 및 함수</span><span class="sxs-lookup"><span data-stu-id="a15df-122">Data Types and Functions</span></span>](data-types-and-functions.md)
