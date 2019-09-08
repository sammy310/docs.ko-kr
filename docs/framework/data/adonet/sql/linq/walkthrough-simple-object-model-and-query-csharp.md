---
title: '연습: 간단한 개체 모델 및 쿼리(C#)'
ms.date: 03/30/2017
ms.assetid: 419961cc-92d6-45f5-ae8a-d485bdde3a37
ms.openlocfilehash: a9b3b57e37331cd13f2cd30b8a7663f2fb39d8c1
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/07/2019
ms.locfileid: "70792135"
---
# <a name="walkthrough-simple-object-model-and-query-c"></a><span data-ttu-id="65e7c-102">연습: 간단한 개체 모델 및 쿼리(C#)</span><span class="sxs-lookup"><span data-stu-id="65e7c-102">Walkthrough: Simple Object Model and Query (C#)</span></span>

<span data-ttu-id="65e7c-103">이 연습에서는 간단한 기본 엔드투엔드 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 시나리오에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="65e7c-103">This walkthrough provides a fundamental end-to-end [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] scenario with minimal complexities.</span></span> <span data-ttu-id="65e7c-104">샘플 Northwind 데이터베이스의 Customers 테이블을 모델링하는 엔터티 클래스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="65e7c-104">You will create an entity class that models the Customers table in the sample Northwind database.</span></span> <span data-ttu-id="65e7c-105">그런 다음 단순 쿼리를 만들어 London에 있는 고객을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="65e7c-105">You will then create a simple query to list customers who are located in London.</span></span>

<span data-ttu-id="65e7c-106">이 연습은 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 개념을 보여 주기 위한 코드를 중심으로 디자인되었습니다.</span><span class="sxs-lookup"><span data-stu-id="65e7c-106">This walkthrough is code-oriented by design to help show [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] concepts.</span></span> <span data-ttu-id="65e7c-107">일반적으로 개체 관계형 디자이너를 사용 하 여 개체 모델을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="65e7c-107">Normally speaking, you would use the Object Relational Designer to create your object model.</span></span>

[!INCLUDE[note_settings_general](../../../../../../includes/note-settings-general-md.md)]

<span data-ttu-id="65e7c-108">이 연습은 Visual C# 개발 설정을 사용하여 작성했습니다.</span><span class="sxs-lookup"><span data-stu-id="65e7c-108">This walkthrough was written by using Visual C# Development Settings.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="65e7c-109">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="65e7c-109">Prerequisites</span></span>

- <span data-ttu-id="65e7c-110">이 연습에서는 전용 폴더("c:\linqtest5")를 사용하여 파일을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="65e7c-110">This walkthrough uses a dedicated folder ("c:\linqtest5") to hold files.</span></span> <span data-ttu-id="65e7c-111">연습을 시작하기 전에 먼저 이 폴더를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="65e7c-111">Create this folder before you begin the walkthrough.</span></span>

- <span data-ttu-id="65e7c-112">이 연습을 수행하려면 Northwind 샘플 데이터베이스가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="65e7c-112">This walkthrough requires the Northwind sample database.</span></span> <span data-ttu-id="65e7c-113">이 데이터베이스가 개발 컴퓨터에 없는 경우 Microsoft 다운로드 사이트에서 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65e7c-113">If you do not have this database on your development computer, you can download it from the Microsoft download site.</span></span> <span data-ttu-id="65e7c-114">지침은 [샘플 데이터베이스 다운로드](downloading-sample-databases.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="65e7c-114">For instructions, see [Downloading Sample Databases](downloading-sample-databases.md).</span></span> <span data-ttu-id="65e7c-115">이 데이터베이스를 다운로드한 후 파일을 c:\linqtest5 폴더에 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="65e7c-115">After you have downloaded the database, copy the file to the c:\linqtest5 folder.</span></span>

## <a name="overview"></a><span data-ttu-id="65e7c-116">개요</span><span class="sxs-lookup"><span data-stu-id="65e7c-116">Overview</span></span>

<span data-ttu-id="65e7c-117">이 연습은 다음과 같은 여섯 가지 주요 작업으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="65e7c-117">This walkthrough consists of six main tasks:</span></span>

- <span data-ttu-id="65e7c-118">Visual Studio에서 솔루션 만들기 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]</span><span class="sxs-lookup"><span data-stu-id="65e7c-118">Creating a [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] solution in Visual Studio.</span></span>

- <span data-ttu-id="65e7c-119">데이터베이스 테이블에 클래스 매핑</span><span class="sxs-lookup"><span data-stu-id="65e7c-119">Mapping a class to a database table.</span></span>

- <span data-ttu-id="65e7c-120">데이터베이스 열을 나타내도록 클래스의 속성 지정</span><span class="sxs-lookup"><span data-stu-id="65e7c-120">Designating properties on the class to represent database columns.</span></span>

- <span data-ttu-id="65e7c-121">Northwind 데이터베이스에 대한 연결 지정</span><span class="sxs-lookup"><span data-stu-id="65e7c-121">Specifying the connection to the Northwind database.</span></span>

- <span data-ttu-id="65e7c-122">데이터베이스에 대해 실행할 단순 쿼리 만들기</span><span class="sxs-lookup"><span data-stu-id="65e7c-122">Creating a simple query to run against the database.</span></span>

- <span data-ttu-id="65e7c-123">쿼리 실행 및 결과 검토</span><span class="sxs-lookup"><span data-stu-id="65e7c-123">Executing the query and observing the results.</span></span>

## <a name="creating-a-linq-to-sql-solution"></a><span data-ttu-id="65e7c-124">LINQ to SQL 솔루션 만들기</span><span class="sxs-lookup"><span data-stu-id="65e7c-124">Creating a LINQ to SQL Solution</span></span>

<span data-ttu-id="65e7c-125">이 첫 번째 작업에서는 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 프로젝트를 빌드하고 실행 하는 데 필요한 참조를 포함 하는 Visual Studio 솔루션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="65e7c-125">In this first task, you create a Visual Studio solution that contains the necessary references to build and run a [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] project.</span></span>

### <a name="to-create-a-linq-to-sql-solution"></a><span data-ttu-id="65e7c-126">LINQ to SQL 솔루션을 만들려면</span><span class="sxs-lookup"><span data-stu-id="65e7c-126">To create a LINQ to SQL solution</span></span>

1. <span data-ttu-id="65e7c-127">Visual Studio **파일** 메뉴에서 **새로 만들기**를 가리킨 다음 **프로젝트**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="65e7c-127">On the Visual Studio **File** menu, point to **New**, and then click **Project**.</span></span>

2. <span data-ttu-id="65e7c-128">**새 프로젝트** 대화 상자의 **프로젝트 형식** 창에서 **C#시각적 개체**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="65e7c-128">In the **Project types** pane of the **New Project** dialog box, click **Visual C#**.</span></span>

3. <span data-ttu-id="65e7c-129">**템플릿** 창에서 **콘솔 애플리케이션**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="65e7c-129">In the **Templates** pane, click **Console Application**.</span></span>

4. <span data-ttu-id="65e7c-130">**이름** 상자에 **linqconsoleapp 입력**을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="65e7c-130">In the **Name** box, type **LinqConsoleApp**.</span></span>

5. <span data-ttu-id="65e7c-131">**위치** 상자에서 프로젝트 파일을 저장할 위치를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="65e7c-131">In the **Location** box, verify where you want to store your project files.</span></span>

6. <span data-ttu-id="65e7c-132">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="65e7c-132">Click **OK**.</span></span>

## <a name="adding-linq-references-and-directives"></a><span data-ttu-id="65e7c-133">LINQ 참조 및 지시문 추가</span><span class="sxs-lookup"><span data-stu-id="65e7c-133">Adding LINQ References and Directives</span></span>

<span data-ttu-id="65e7c-134">이 연습에서는 프로젝트에 기본적으로 설치되어 있지 않을 수 있는 어셈블리를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="65e7c-134">This walkthrough uses assemblies that might not be installed by default in your project.</span></span> <span data-ttu-id="65e7c-135">System.object가 프로젝트에 참조로 나열 되지 않은 경우 ( **솔루션 탐색기**의 **참조** 노드 확장) 다음 단계에 설명 된 대로 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="65e7c-135">If System.Data.Linq is not listed as a reference in your project (expand the **References** node in **Solution Explorer**), add it, as explained in the following steps.</span></span>

### <a name="to-add-systemdatalinq"></a><span data-ttu-id="65e7c-136">System.Data.Linq를 추가하려면</span><span class="sxs-lookup"><span data-stu-id="65e7c-136">To add System.Data.Linq</span></span>

1. <span data-ttu-id="65e7c-137">**솔루션 탐색기**에서 **참조**를 마우스 오른쪽 단추로 클릭 한 다음 **참조 추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="65e7c-137">In **Solution Explorer**, right-click **References**, and then click **Add Reference**.</span></span>

2. <span data-ttu-id="65e7c-138">**참조 추가** 대화 상자에서 **.net**을 클릭 하 고 system.xml 어셈블리를 클릭 한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="65e7c-138">In the **Add Reference** dialog box, click **.NET**, click the System.Data.Linq assembly, and then click **OK**.</span></span>

     <span data-ttu-id="65e7c-139">어셈블리가 프로젝트에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="65e7c-139">The assembly is added to the project.</span></span>

3. <span data-ttu-id="65e7c-140">**Program.cs**의 맨 위에 다음 지시문을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="65e7c-140">Add the following directives at the top of **Program.cs**:</span></span>

     [!code-csharp[DLinqWalk1CS#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk1CS/cs/Program.cs#1)]

## <a name="mapping-a-class-to-a-database-table"></a><span data-ttu-id="65e7c-141">데이터베이스 테이블에 클래스 매핑</span><span class="sxs-lookup"><span data-stu-id="65e7c-141">Mapping a Class to a Database Table</span></span>

<span data-ttu-id="65e7c-142">이 단계에서는 클래스를 생성하여 데이터베이스 테이블에 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="65e7c-142">In this step, you create a class and map it to a database table.</span></span> <span data-ttu-id="65e7c-143">이러한 클래스를 *엔터티 클래스*라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="65e7c-143">Such a class is termed an *entity class*.</span></span> <span data-ttu-id="65e7c-144">매핑을 수행하려면 <xref:System.Data.Linq.Mapping.TableAttribute> 특성을 추가하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="65e7c-144">Note that the mapping is accomplished by just adding the <xref:System.Data.Linq.Mapping.TableAttribute> attribute.</span></span> <span data-ttu-id="65e7c-145"><xref:System.Data.Linq.Mapping.TableAttribute.Name%2A> 속성은 데이터베이스의 테이블 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="65e7c-145">The <xref:System.Data.Linq.Mapping.TableAttribute.Name%2A> property specifies the name of the table in the database.</span></span>

### <a name="to-create-an-entity-class-and-map-it-to-a-database-table"></a><span data-ttu-id="65e7c-146">엔터티 클래스를 만들어 데이터베이스 테이블에 매핑하려면</span><span class="sxs-lookup"><span data-stu-id="65e7c-146">To create an entity class and map it to a database table</span></span>

- <span data-ttu-id="65e7c-147">다음 코드를 Program.cs에서 `Program` 클래스 선언 바로 위에 입력하거나 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="65e7c-147">Type or paste the following code into Program.cs immediately above the `Program` class declaration:</span></span>

     [!code-csharp[DLinqWalk1CS#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk1CS/cs/Program.cs#2)]

## <a name="designating-properties-on-the-class-to-represent-database-columns"></a><span data-ttu-id="65e7c-148">데이터베이스 열을 나타내도록 클래스의 속성 지정</span><span class="sxs-lookup"><span data-stu-id="65e7c-148">Designating Properties on the Class to Represent Database Columns</span></span>

<span data-ttu-id="65e7c-149">이 단계에서는 다음과 같은 몇 가지 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="65e7c-149">In this step, you accomplish several tasks.</span></span>

- <span data-ttu-id="65e7c-150"><xref:System.Data.Linq.Mapping.ColumnAttribute> 특성을 사용하여 데이터베이스 테이블의 열을 나타내도록 엔터티 클래스의 `CustomerID` 및 `City` 속성을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="65e7c-150">You use the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute to designate `CustomerID` and `City` properties on the entity class as representing columns in the database table.</span></span>

- <span data-ttu-id="65e7c-151">데이터베이스의 기본 키 열을 나타내도록 `CustomerID` 속성을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="65e7c-151">You designate the `CustomerID` property as representing a primary key column in the database.</span></span>

- <span data-ttu-id="65e7c-152">전용 스토리지에 `_CustomerID` 및 `_City` 필드를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="65e7c-152">You designate `_CustomerID` and `_City` fields for private storage.</span></span> <span data-ttu-id="65e7c-153">그러면 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에서 비즈니스 논리가 포함된 공용 접근자를 사용하는 대신 값을 직접 저장하고 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65e7c-153">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] can then store and retrieve values directly, instead of using public accessors that might include business logic.</span></span>

### <a name="to-represent-characteristics-of-two-database-columns"></a><span data-ttu-id="65e7c-154">두 데이터베이스 열의 특징을 나타내려면</span><span class="sxs-lookup"><span data-stu-id="65e7c-154">To represent characteristics of two database columns</span></span>

- <span data-ttu-id="65e7c-155">다음 코드를 Program.cs에서 `Customer` 클래스의 중괄호 내에 입력하거나 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="65e7c-155">Type or paste the following code into Program.cs inside the curly braces for the `Customer` class.</span></span>

     [!code-csharp[DLinqWalk1CS#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk1CS/cs/Program.cs#3)]

## <a name="specifying-the-connection-to-the-northwind-database"></a><span data-ttu-id="65e7c-156">Northwind 데이터베이스에 대한 연결 지정</span><span class="sxs-lookup"><span data-stu-id="65e7c-156">Specifying the Connection to the Northwind Database</span></span>

<span data-ttu-id="65e7c-157">이 단계에서는 <xref:System.Data.Linq.DataContext> 개체를 사용하여 코드 기반 데이터 구조체와 데이터베이스 자체 간의 연결을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65e7c-157">In this step you use a <xref:System.Data.Linq.DataContext> object to establish a connection between your code-based data structures and the database itself.</span></span> <span data-ttu-id="65e7c-158"><xref:System.Data.Linq.DataContext>는 데이터베이스에서 개체를 검색하고 변경 내용을 전송할 때 사용하는 기본 채널입니다.</span><span class="sxs-lookup"><span data-stu-id="65e7c-158">The <xref:System.Data.Linq.DataContext> is the main channel through which you retrieve objects from the database and submit changes.</span></span>

<span data-ttu-id="65e7c-159">또한 `Table<Customer>`이 데이터베이스의 Customers 테이블에 대한 쿼리에 대해 형식화된 논리적 테이블로 사용되도록 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="65e7c-159">You also declare a `Table<Customer>` to act as the logical, typed table for your queries against the Customers table in the database.</span></span> <span data-ttu-id="65e7c-160">이후 단계에서 이러한 쿼리를 만들고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="65e7c-160">You will create and execute these queries in later steps.</span></span>

### <a name="to-specify-the-database-connection"></a><span data-ttu-id="65e7c-161">데이터베이스 연결을 지정하려면</span><span class="sxs-lookup"><span data-stu-id="65e7c-161">To specify the database connection</span></span>

- <span data-ttu-id="65e7c-162">다음 코드를 `Main` 메서드에 입력하거나 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="65e7c-162">Type or paste the following code into the `Main` method.</span></span>

     <span data-ttu-id="65e7c-163">`northwnd.mdf` 파일이 linqtest5 폴더 내에 있는 것으로 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="65e7c-163">Note that the `northwnd.mdf` file is assumed to be in the linqtest5 folder.</span></span> <span data-ttu-id="65e7c-164">자세한 내용은 이 연습 앞부분의 사전 요구 사항 단원을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="65e7c-164">For more information, see the Prerequisites section earlier in this walkthrough.</span></span>

     [!code-csharp[DLinqWalk1CS#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk1CS/cs/Program.cs#4)]

## <a name="creating-a-simple-query"></a><span data-ttu-id="65e7c-165">단순 쿼리 작성</span><span class="sxs-lookup"><span data-stu-id="65e7c-165">Creating a Simple Query</span></span>

<span data-ttu-id="65e7c-166">이 단계에서는 데이터베이스 Customers 테이블에서 London에 있는 고객을 찾는 쿼리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="65e7c-166">In this step, you create a query to find which customers in the database Customers table are located in London.</span></span> <span data-ttu-id="65e7c-167">이 단계의 쿼리 코드는 쿼리를 설명하기만 하고</span><span class="sxs-lookup"><span data-stu-id="65e7c-167">The query code in this step just describes the query.</span></span> <span data-ttu-id="65e7c-168">실행하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="65e7c-168">It does not execute it.</span></span> <span data-ttu-id="65e7c-169">이 방법을 *지연 된 실행*이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="65e7c-169">This approach is known as *deferred execution*.</span></span> <span data-ttu-id="65e7c-170">자세한 내용은 [LINQ 쿼리 소개(C#)](../../../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="65e7c-170">For more information, see [Introduction to LINQ Queries (C#)](../../../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md).</span></span>

<span data-ttu-id="65e7c-171">또한 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에서 생성하는 SQL 명령을 보여 주는 로그 출력을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="65e7c-171">You will also produce a log output to show the SQL commands that [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] generates.</span></span> <span data-ttu-id="65e7c-172"><xref:System.Data.Linq.DataContext.Log%2A>를 사용하는 이 로깅 기능은 디버깅할 때와 데이터베이스로 전송되는 명령이 쿼리를 정확히 나타내는지 확인할 때 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="65e7c-172">This logging feature (which uses <xref:System.Data.Linq.DataContext.Log%2A>) is helpful in debugging, and in determining that the commands being sent to the database accurately represent your query.</span></span>

### <a name="to-create-a-simple-query"></a><span data-ttu-id="65e7c-173">단순 쿼리를 작성하려면</span><span class="sxs-lookup"><span data-stu-id="65e7c-173">To create a simple query</span></span>

- <span data-ttu-id="65e7c-174">다음 코드를 `Main` 메서드에서 `Table<Customer>` 선언 뒤에 입력하거나 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="65e7c-174">Type or paste the following code into the `Main` method after the `Table<Customer>` declaration.</span></span>

     [!code-csharp[DLinqWalk1ACS#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk1ACS/cs/Program.cs#5)]

## <a name="executing-the-query"></a><span data-ttu-id="65e7c-175">쿼리 실행</span><span class="sxs-lookup"><span data-stu-id="65e7c-175">Executing the Query</span></span>

<span data-ttu-id="65e7c-176">이 단계에서는 실제로 쿼리를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="65e7c-176">In this step, you actually execute the query.</span></span> <span data-ttu-id="65e7c-177">앞의 단계에서 만든 쿼리 식은 결과가 필요할 때까지 계산되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="65e7c-177">The query expressions you created in the previous steps are not evaluated until the results are needed.</span></span> <span data-ttu-id="65e7c-178">`foreach` 반복을 시작하면 데이터베이스에 대해 SQL 명령이 실행되고 개체가 구체화됩니다.</span><span class="sxs-lookup"><span data-stu-id="65e7c-178">When you begin the `foreach` iteration, a SQL command is executed against the database and objects are materialized.</span></span>

### <a name="to-execute-the-query"></a><span data-ttu-id="65e7c-179">쿼리를 실행하려면</span><span class="sxs-lookup"><span data-stu-id="65e7c-179">To execute the query</span></span>

1. <span data-ttu-id="65e7c-180">다음 코드를 `Main` 메서드의 끝(쿼리 설명 뒤)에 입력하거나 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="65e7c-180">Type or paste the following code at the end of the `Main` method (after the query description).</span></span>

     [!code-csharp[DLinqWalk1ACS#6](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk1ACS/cs/Program.cs#6)]

2. <span data-ttu-id="65e7c-181">F5 키를 눌러 애플리케이션을 디버깅합니다.</span><span class="sxs-lookup"><span data-stu-id="65e7c-181">Press F5 to debug the application.</span></span>

    > [!NOTE]
    > <span data-ttu-id="65e7c-182">응용 프로그램에서 런타임 오류를 생성 하는 경우 [연습에서 학습](learning-by-walkthroughs.md)의 문제 해결 섹션을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="65e7c-182">If your application generates a run-time error, see the Troubleshooting section of [Learning by Walkthroughs](learning-by-walkthroughs.md).</span></span>

     <span data-ttu-id="65e7c-183">콘솔 창의 쿼리 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="65e7c-183">The query results in the console window should appear as follows:</span></span>

     `ID=AROUT, City=London`

     `ID=BSBEV, City=London`

     `ID=CONSH, City=London`

     `ID=EASTC, City=London`

     `ID=NORTS, City=London`

     `ID=SEVES, City=London`

3. <span data-ttu-id="65e7c-184">콘솔 창에서 Enter 키를 눌러 애플리케이션을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="65e7c-184">Press Enter in the console window to close the application.</span></span>

## <a name="next-steps"></a><span data-ttu-id="65e7c-185">다음 단계</span><span class="sxs-lookup"><span data-stu-id="65e7c-185">Next Steps</span></span>

<span data-ttu-id="65e7c-186">[연습: 관계 간 쿼리 (C#)](walkthrough-querying-across-relationships-csharp.md) 토픽은이 연습을 종료 하는 위치에서 계속 됩니다.</span><span class="sxs-lookup"><span data-stu-id="65e7c-186">The [Walkthrough: Querying Across Relationships (C#)](walkthrough-querying-across-relationships-csharp.md) topic continues where this walkthrough ends.</span></span> <span data-ttu-id="65e7c-187">관계 간 쿼리 연습에서는에서 관계형 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 데이터베이스의 *조인과* 유사 하 게 테이블을 쿼리 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="65e7c-187">The Query Across Relationships walkthrough demonstrates how [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] can query across tables, similar to *joins* in a relational database.</span></span>

<span data-ttu-id="65e7c-188">관계 간 쿼리 연습을 수행하려면 방금 완료한 연습의 솔루션을 저장해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="65e7c-188">If you want to do the Query Across Relationships walkthrough, make sure to save the solution for the walkthrough you have just completed, which is a prerequisite.</span></span>

## <a name="see-also"></a><span data-ttu-id="65e7c-189">참고자료</span><span class="sxs-lookup"><span data-stu-id="65e7c-189">See also</span></span>

- [<span data-ttu-id="65e7c-190">연습으로 학습</span><span class="sxs-lookup"><span data-stu-id="65e7c-190">Learning by Walkthroughs</span></span>](learning-by-walkthroughs.md)
