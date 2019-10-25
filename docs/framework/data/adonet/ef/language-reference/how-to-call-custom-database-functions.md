---
title: '방법: 사용자 지정 데이터베이스 함수 호출'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 4354e5eb-dd45-469d-97fb-1c495705ee59
ms.openlocfilehash: e357868361e11dc919fa09db9a36185923a6e40e
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2019
ms.locfileid: "72847088"
---
# <a name="how-to-call-custom-database-functions"></a><span data-ttu-id="73dac-102">방법: 사용자 지정 데이터베이스 함수 호출</span><span class="sxs-lookup"><span data-stu-id="73dac-102">How to: Call Custom Database Functions</span></span>

<span data-ttu-id="73dac-103">이 항목에서는 LINQ to Entities 쿼리 내에서 데이터베이스에 정의된 사용자 지정 함수를 호출하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="73dac-103">This topic describes how to call custom functions that are defined in the database from within LINQ to Entities queries.</span></span>

<span data-ttu-id="73dac-104">LINQ to Entities 쿼리에서 호출된 데이터베이스 함수는 데이터베이스에서 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="73dac-104">Database functions that are called from LINQ to Entities queries are executed in the database.</span></span> <span data-ttu-id="73dac-105">데이터베이스에서 함수를 실행하면 애플리케이션 성능이 향상될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73dac-105">Executing functions in the database can improve application performance.</span></span>

<span data-ttu-id="73dac-106">다음 절차에서는 사용자 지정 데이터베이스 함수를 호출하는 방법에 대해 간단히 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="73dac-106">The procedure below provides a high-level outline for calling a custom database function.</span></span> <span data-ttu-id="73dac-107">절차 다음에 나오는 예제에서는 절차의 단계를 보다 자세히 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="73dac-107">The example that follows provides more detail about the steps in the procedure.</span></span>

## <a name="to-call-custom-functions-that-are-defined-in-the-database"></a><span data-ttu-id="73dac-108">데이터베이스에 정의되어 있는 사용자 지정 함수를 호출하려면</span><span class="sxs-lookup"><span data-stu-id="73dac-108">To call custom functions that are defined in the database</span></span>

1. <span data-ttu-id="73dac-109">데이터베이스에서 사용자 지정 함수를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="73dac-109">Create a custom function in your database.</span></span>

     <span data-ttu-id="73dac-110">SQL Server에서 사용자 지정 함수를 만드는 방법에 대 한 자세한 내용은 [CREATE FUNCTION (transact-sql)](https://go.microsoft.com/fwlink/?LinkID=139871)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="73dac-110">For more information about creating custom functions in SQL Server, see [CREATE FUNCTION (Transact-SQL)](https://go.microsoft.com/fwlink/?LinkID=139871).</span></span>

2. <span data-ttu-id="73dac-111">.edmx 파일의 SSDL(저장소 스키마 정의 언어)에서 함수를 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="73dac-111">Declare a function in the store schema definition language (SSDL) of your .edmx file.</span></span> <span data-ttu-id="73dac-112">함수의 이름은 데이터베이스에 선언된 함수의 이름과 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="73dac-112">The name of the function must be the same as the name of the function declared in the database.</span></span>

     <span data-ttu-id="73dac-113">자세한 내용은 [Function 요소 (SSDL)](/ef/ef6/modeling/designer/advanced/edmx/ssdl-spec#function-element-ssdl)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="73dac-113">For more information, see [Function Element (SSDL)](/ef/ef6/modeling/designer/advanced/edmx/ssdl-spec#function-element-ssdl).</span></span>

3. <span data-ttu-id="73dac-114">해당되는 메서드를 애플리케이션 코드의 클래스에 추가하고 <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute>를 메서드에 적용합니다. 특성의 <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.NamespaceName%2A> 매개 변수는 개념적 모델의 네임스페이스 이름이고, 특성의 <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.FunctionName%2A> 매개 변수는 개념적 모델의 함수 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="73dac-114">Add a corresponding method to a class in your application code and apply a <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute> to the method Note that the <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.NamespaceName%2A> and <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.FunctionName%2A> parameters of the attribute are the namespace name of the conceptual model and the function name in the conceptual model respectively.</span></span> <span data-ttu-id="73dac-115">LINQ에서 함수 이름을 확인할 때는 대/소문자가 구분됩니다.</span><span class="sxs-lookup"><span data-stu-id="73dac-115">Function name resolution for LINQ is case sensitive.</span></span>

4. <span data-ttu-id="73dac-116">LINQ to Entities 쿼리에서 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="73dac-116">Call the method in a LINQ to Entities query.</span></span>  

## <a name="example"></a><span data-ttu-id="73dac-117">예제</span><span class="sxs-lookup"><span data-stu-id="73dac-117">Example</span></span>

<span data-ttu-id="73dac-118">다음 예제에서는 LINQ to Entities 쿼리 내에서 사용자 지정 데이터베이스 함수를 호출하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="73dac-118">The following example demonstrates how to call a custom database function from within a LINQ to Entities query.</span></span> <span data-ttu-id="73dac-119">이 예제에서는 School 모델을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="73dac-119">The example uses the School model.</span></span> <span data-ttu-id="73dac-120">School 모델에 대 한 자세한 내용은 [School 샘플 데이터베이스 만들기](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399731(v=vs.100)) 및 [School .edmx 파일 생성](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399739(v=vs.100))을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="73dac-120">For information about the School model, see [Creating the School Sample Database](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399731(v=vs.100)) and [Generating the School .edmx File](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399739(v=vs.100)).</span></span>

<span data-ttu-id="73dac-121">다음 코드에서는 `AvgStudentGrade` 함수를 School 샘플 데이터베이스에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="73dac-121">The following code adds the `AvgStudentGrade` function to the School sample database.</span></span>

> [!NOTE]
> <span data-ttu-id="73dac-122">사용자 지정 데이터베이스 함수를 호출하는 단계는 데이터베이스 서버에 상관없이 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="73dac-122">The steps for calling a custom database function are the same regardless of the database server.</span></span> <span data-ttu-id="73dac-123">그러나 아래의 코드는 SQL Server 데이터베이스에서 함수를 만드는 작업과 관련된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="73dac-123">However, the code below is specific to creating a function in a SQL Server database.</span></span> <span data-ttu-id="73dac-124">다른 데이터베이스 서버에서 사용자 지정 함수를 만드는 작업에 대한 코드는 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73dac-124">The code for creating a custom function in other database servers might differ.</span></span>

[!code-sql[DP L2E MapToDBFunction#1](~/samples/snippets/tsql/VS_Snippets_Data/dp l2e maptodbfunction/tsql/create_avgstudentgrade.sql#1)]

## <a name="example"></a><span data-ttu-id="73dac-125">예제</span><span class="sxs-lookup"><span data-stu-id="73dac-125">Example</span></span>

<span data-ttu-id="73dac-126">그런 다음 *.edmx* 파일의 SSDL (저장소 스키마 정의 언어)에서 함수를 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="73dac-126">Next, declare a function in the store schema definition language (SSDL) of your *.edmx* file.</span></span> <span data-ttu-id="73dac-127">다음 코드는 SSDL에서 `AvgStudentGrade` 함수를 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="73dac-127">The following code declares the `AvgStudentGrade` function in SSDL:</span></span>

[!code-xml[DP L2E MapToDBFunction#2](~/samples/snippets/csharp/VS_Snippets_Data/dp l2e maptodbfunction/cs/school.edmx#2)]

## <a name="example"></a><span data-ttu-id="73dac-128">예제</span><span class="sxs-lookup"><span data-stu-id="73dac-128">Example</span></span>

<span data-ttu-id="73dac-129">이제 메서드를 만들어 SSDL에 선언 된 함수에 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="73dac-129">Now, create a method and map it to the function declared in the SSDL.</span></span> <span data-ttu-id="73dac-130"><xref:System.Data.Objects.DataClasses.EdmFunctionAttribute>를 사용하여 다음 클래스의 메서드가 위의 SSDL에서 정의된 함수로 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="73dac-130">The method in the following class is mapped to the function defined in the SSDL (above) by using an <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute>.</span></span> <span data-ttu-id="73dac-131">이 메서드가 호출되면 데이터베이스에 있는 해당되는 함수가 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="73dac-131">When this method is called, the corresponding function in the database is executed.</span></span>

[!code-csharp[DP L2E MapToDBFunction#3](~/samples/snippets/csharp/VS_Snippets_Data/dp l2e maptodbfunction/cs/program.cs#3)]
[!code-vb[DP L2E MapToDBFunction#3](~/samples/snippets/visualbasic/VS_Snippets_Data/dp l2e maptodbfunction/vb/module1.vb#3)]

## <a name="example"></a><span data-ttu-id="73dac-132">예제</span><span class="sxs-lookup"><span data-stu-id="73dac-132">Example</span></span>

<span data-ttu-id="73dac-133">마지막으로 LINQ to Entities 쿼리에서 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="73dac-133">Finally, call the method in a LINQ to Entities query.</span></span> <span data-ttu-id="73dac-134">다음 코드에서는 학생의 성 및 평균 학점을 콘솔에 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="73dac-134">The following code displays students' last names and average grades to the console:</span></span>

[!code-csharp[DP L2E MapToDBFunction#4](~/samples/snippets/csharp/VS_Snippets_Data/dp l2e maptodbfunction/cs/program.cs#4)]
[!code-vb[DP L2E MapToDBFunction#4](~/samples/snippets/visualbasic/VS_Snippets_Data/dp l2e maptodbfunction/vb/module1.vb#4)]

## <a name="see-also"></a><span data-ttu-id="73dac-135">참조</span><span class="sxs-lookup"><span data-stu-id="73dac-135">See also</span></span>

- <span data-ttu-id="73dac-136">[.edmx 파일 개요](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc982042(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="73dac-136">[.edmx File Overview](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc982042(v=vs.100))</span></span>
- [<span data-ttu-id="73dac-137">LINQ to Entities에서 쿼리</span><span class="sxs-lookup"><span data-stu-id="73dac-137">Queries in LINQ to Entities</span></span>](queries-in-linq-to-entities.md)
