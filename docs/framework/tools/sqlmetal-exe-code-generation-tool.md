---
title: SqlMetal.exe(코드 생성 도구)
description: 코드 생성 도구인 SqlMetal.exe에 대해 알아봅니다. 이 도구를 사용하여 .NET의 LINQ to SQL 구성 요소에 대한 코드 및 매핑을 생성합니다.
ms.date: 03/30/2017
helpviewer_keywords:
- SQLMetal [LINQ to SQL]
- code generation tool
- SQLMetal.exe
- LINQ to SQL, serialization
- LINQ to SQL, DBML files
- LINQ to SQL, SQLMetal
ms.assetid: 819e5a96-7646-4fdb-b14b-fe31221b0614
ms.openlocfilehash: 4edf11315892ed8267bee17d69a70033348eca5c
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96272568"
---
# <a name="sqlmetalexe-code-generation-tool"></a><span data-ttu-id="de344-104">SqlMetal.exe(코드 생성 도구)</span><span class="sxs-lookup"><span data-stu-id="de344-104">SqlMetal.exe (Code Generation Tool)</span></span>

<span data-ttu-id="de344-105">SqlMetal 명령줄 도구는 .NET Framework의 [!INCLUDE[vbtecdlinq](../../../includes/vbtecdlinq-md.md)] 구성 요소에 사용할 코드 및 매핑을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="de344-105">The SqlMetal command-line tool generates code and mapping for the [!INCLUDE[vbtecdlinq](../../../includes/vbtecdlinq-md.md)] component of the .NET Framework.</span></span> <span data-ttu-id="de344-106">이 항목의 뒷부분에 나오는 옵션을 적용하면 SqlMetal을 통해 다음을 포함하는 다양한 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de344-106">By applying options that appear later in this topic, you can instruct SqlMetal to perform several different actions that include the following:</span></span>  
  
- <span data-ttu-id="de344-107">데이터베이스에서 소스 코드 및 매핑 특성이나 매핑 파일 생성</span><span class="sxs-lookup"><span data-stu-id="de344-107">From a database, generate source code and mapping attributes or a mapping file.</span></span>  
  
- <span data-ttu-id="de344-108">데이터베이스에서 사용자 지정에 사용할 중간 데이터베이스 태그 언어(.dbml) 파일 생성</span><span class="sxs-lookup"><span data-stu-id="de344-108">From a database, generate an intermediate database markup language (.dbml) file for customization.</span></span>  
  
- <span data-ttu-id="de344-109">.dbml 파일에서 코드 및 매핑 특성이나 매핑 파일 생성</span><span class="sxs-lookup"><span data-stu-id="de344-109">From a .dbml file, generate code and mapping attributes or a mapping file.</span></span>  
  
 <span data-ttu-id="de344-110">이 도구는 자동으로 Visual Studio와 함께 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="de344-110">This tool is automatically installed with Visual Studio.</span></span> <span data-ttu-id="de344-111">기본적으로 이 파일은 `drive`:\Program Files\Microsoft SDKs\Windows\v`n.nn`\bin에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de344-111">By default, the file is located at `drive`:\Program Files\Microsoft SDKs\Windows\v`n.nn`\bin.</span></span> <span data-ttu-id="de344-112">Visual Studio를 설치하지 않으면 [Windows SDK](https://go.microsoft.com/fwlink/?LinkId=142225)를 다운로드하여 SQLMetal 파일도 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de344-112">If you do not install Visual Studio, you can also get the SQLMetal file by downloading the [Windows SDK](https://go.microsoft.com/fwlink/?LinkId=142225).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="de344-113">Visual Studio를 사용하는 개발자는 개체 관계형 디자이너를 사용하여 엔터티 클래스를 생성할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de344-113">Developers who use Visual Studio can also use the Object Relational Designer to generate entity classes.</span></span> <span data-ttu-id="de344-114">명령줄 방식을 사용하면 대규모 데이터베이스에 대해 효율적으로 크기를 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de344-114">The command-line approach scales well for large databases.</span></span> <span data-ttu-id="de344-115">SqlMetal은 명령줄 도구이므로 빌드 프로세스에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de344-115">Because SqlMetal is a command-line tool, you can use it in a build process.</span></span>  
  
 <span data-ttu-id="de344-116">이 도구를 실행하려면 Visual Studio용 개발자 명령 프롬프트(또는 Windows 7의 Visual Studio 명령 프롬프트)를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="de344-116">To run the tool, use the Developer Command Prompt for Visual Studio (or the Visual Studio Command Prompt in Windows 7).</span></span> <span data-ttu-id="de344-117">자세한 내용은 [명령 프롬프트](developer-command-prompt-for-vs.md)를 참조하세요. 명령 프롬프트에 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="de344-117">For more information, see [Command Prompts](developer-command-prompt-for-vs.md).At the command prompt, type the following:</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="de344-118">구문</span><span class="sxs-lookup"><span data-stu-id="de344-118">Syntax</span></span>  
  
```console  
sqlmetal [options] [<input file>]  
```  
  
## <a name="options"></a><span data-ttu-id="de344-119">옵션</span><span class="sxs-lookup"><span data-stu-id="de344-119">Options</span></span>  

 <span data-ttu-id="de344-120">최신 옵션 목록을 보려면 설치한 위치의 명령 프롬프트에서 `sqlmetal /?` 를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="de344-120">To view the most current option list, type `sqlmetal /?` at a command prompt from the installed location.</span></span>  
  
 <span data-ttu-id="de344-121">**연결 옵션**</span><span class="sxs-lookup"><span data-stu-id="de344-121">**Connection Options**</span></span>  
  
|<span data-ttu-id="de344-122">옵션</span><span class="sxs-lookup"><span data-stu-id="de344-122">Option</span></span>|<span data-ttu-id="de344-123">설명</span><span class="sxs-lookup"><span data-stu-id="de344-123">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="de344-124">**/server:** *\<name>*</span><span class="sxs-lookup"><span data-stu-id="de344-124">**/server:** *\<name>*</span></span>|<span data-ttu-id="de344-125">데이터베이스 서버 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="de344-125">Specifies database server name.</span></span>|  
|<span data-ttu-id="de344-126">**/database:** *\<name>*</span><span class="sxs-lookup"><span data-stu-id="de344-126">**/database:** *\<name>*</span></span>|<span data-ttu-id="de344-127">서버의 데이터베이스 카탈로그를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="de344-127">Specifies database catalog on server.</span></span>|  
|<span data-ttu-id="de344-128">**/user:** *\<name>*</span><span class="sxs-lookup"><span data-stu-id="de344-128">**/user:** *\<name>*</span></span>|<span data-ttu-id="de344-129">로그온 사용자 ID를 지정합니다. 기본값: Windows 인증 사용.</span><span class="sxs-lookup"><span data-stu-id="de344-129">Specifies logon user id. Default value: Use Windows authentication.</span></span>|  
|<span data-ttu-id="de344-130">**/password:** *\<password>*</span><span class="sxs-lookup"><span data-stu-id="de344-130">**/password:** *\<password>*</span></span>|<span data-ttu-id="de344-131">로그온 암호를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="de344-131">Specifies logon password.</span></span> <span data-ttu-id="de344-132">기본값: Windows 인증 사용.</span><span class="sxs-lookup"><span data-stu-id="de344-132">Default value: Use Windows authentication.</span></span>|  
|<span data-ttu-id="de344-133">**/conn:** *\<connection string>*</span><span class="sxs-lookup"><span data-stu-id="de344-133">**/conn:** *\<connection string>*</span></span>|<span data-ttu-id="de344-134">데이터베이스 연결 문자열을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="de344-134">Specifies database connection string.</span></span> <span data-ttu-id="de344-135">**/server**, **/database**, **/user** 또는 **/password** 옵션과 함께 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="de344-135">Cannot be used with **/server**, **/database**, **/user**, or **/password** options.</span></span><br /><br /> <span data-ttu-id="de344-136">연결 문자열에 파일 이름을 포함하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="de344-136">Do not include the file name in the connection string.</span></span> <span data-ttu-id="de344-137">대신 파일 이름을 명령줄에 입력 파일로 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="de344-137">Instead, add the file name to the command line as the input file.</span></span> <span data-ttu-id="de344-138">예를 들어 **sqlmetal /code:"c:\northwind.cs" /language:csharp "c:\northwnd.mdf"** 에서는 "c:\northwnd.mdf"를 입력 파일로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="de344-138">For example, the following line specifies "c:\northwnd.mdf" as the input file: **sqlmetal /code:"c:\northwind.cs" /language:csharp "c:\northwnd.mdf"**.</span></span>|  
|<span data-ttu-id="de344-139">**/timeout:** *\<seconds>*</span><span class="sxs-lookup"><span data-stu-id="de344-139">**/timeout:** *\<seconds>*</span></span>|<span data-ttu-id="de344-140">SqlMetal이 데이터베이스에 액세스할 때의 시간 제한 값을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="de344-140">Specifies time-out value when SqlMetal accesses the database.</span></span> <span data-ttu-id="de344-141">기본값: 0(시간 제한 없음).</span><span class="sxs-lookup"><span data-stu-id="de344-141">Default value: 0 (that is, no time limit).</span></span>|  
  
 <span data-ttu-id="de344-142">**추출 옵션**</span><span class="sxs-lookup"><span data-stu-id="de344-142">**Extraction options**</span></span>  
  
|<span data-ttu-id="de344-143">옵션</span><span class="sxs-lookup"><span data-stu-id="de344-143">Option</span></span>|<span data-ttu-id="de344-144">설명</span><span class="sxs-lookup"><span data-stu-id="de344-144">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="de344-145">**/views**</span><span class="sxs-lookup"><span data-stu-id="de344-145">**/views**</span></span>|<span data-ttu-id="de344-146">데이터베이스 뷰를 추출합니다.</span><span class="sxs-lookup"><span data-stu-id="de344-146">Extracts database views.</span></span>|  
|<span data-ttu-id="de344-147">**/functions**</span><span class="sxs-lookup"><span data-stu-id="de344-147">**/functions**</span></span>|<span data-ttu-id="de344-148">데이터베이스 기능을 추출합니다.</span><span class="sxs-lookup"><span data-stu-id="de344-148">Extracts database functions.</span></span>|  
|<span data-ttu-id="de344-149">**/sprocs**</span><span class="sxs-lookup"><span data-stu-id="de344-149">**/sprocs**</span></span>|<span data-ttu-id="de344-150">저장 프로시저를 추출합니다.</span><span class="sxs-lookup"><span data-stu-id="de344-150">Extracts stored procedures.</span></span>|  
  
 <span data-ttu-id="de344-151">**출력 옵션**</span><span class="sxs-lookup"><span data-stu-id="de344-151">**Output options**</span></span>  
  
|<span data-ttu-id="de344-152">옵션</span><span class="sxs-lookup"><span data-stu-id="de344-152">Option</span></span>|<span data-ttu-id="de344-153">설명</span><span class="sxs-lookup"><span data-stu-id="de344-153">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="de344-154">**/dbml** *[:file]*</span><span class="sxs-lookup"><span data-stu-id="de344-154">**/dbml** *[:file]*</span></span>|<span data-ttu-id="de344-155">출력을 .dbml로 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="de344-155">Sends output as .dbml.</span></span> <span data-ttu-id="de344-156">**/map** 옵션과 함께 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="de344-156">Cannot be used with **/map** option.</span></span>|  
|<span data-ttu-id="de344-157">**/code** *[:file]*</span><span class="sxs-lookup"><span data-stu-id="de344-157">**/code** *[:file]*</span></span>|<span data-ttu-id="de344-158">출력을 소스 코드로 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="de344-158">Sends output as source code.</span></span> <span data-ttu-id="de344-159">**/dbml** 옵션과 함께 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="de344-159">Cannot be used with **/dbml** option.</span></span>|  
|<span data-ttu-id="de344-160">**/map** *[:file]*</span><span class="sxs-lookup"><span data-stu-id="de344-160">**/map** *[:file]*</span></span>|<span data-ttu-id="de344-161">특성 대신 XML 매핑 파일을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="de344-161">Generates an XML mapping file instead of attributes.</span></span> <span data-ttu-id="de344-162">**/dbml** 옵션과 함께 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="de344-162">Cannot be used with **/dbml** option.</span></span>|  
  
 <span data-ttu-id="de344-163">**기타**</span><span class="sxs-lookup"><span data-stu-id="de344-163">**Miscellaneous**</span></span>  
  
|<span data-ttu-id="de344-164">옵션</span><span class="sxs-lookup"><span data-stu-id="de344-164">Option</span></span>|<span data-ttu-id="de344-165">설명</span><span class="sxs-lookup"><span data-stu-id="de344-165">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="de344-166">**/language:** *\<language>*</span><span class="sxs-lookup"><span data-stu-id="de344-166">**/language:** *\<language>*</span></span>|<span data-ttu-id="de344-167">소스 코드 언어를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="de344-167">Specifies source code language.</span></span><br /><br /> <span data-ttu-id="de344-168">유효한 *\<language>* : vb, csharp.</span><span class="sxs-lookup"><span data-stu-id="de344-168">Valid *\<language>*: vb, csharp.</span></span><br /><br /> <span data-ttu-id="de344-169">기본값: 코드 파일 이름의 확장명에서 파생됩니다.</span><span class="sxs-lookup"><span data-stu-id="de344-169">Default value: Derived from extension on code file name.</span></span>|  
|<span data-ttu-id="de344-170">**/namespace:** *\<name>*</span><span class="sxs-lookup"><span data-stu-id="de344-170">**/namespace:** *\<name>*</span></span>|<span data-ttu-id="de344-171">생성된 코드의 네임스페이스를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="de344-171">Specifies namespace of the generated code.</span></span> <span data-ttu-id="de344-172">기본적으로는 네임스페이스가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="de344-172">Default value: no namespace.</span></span>|  
|<span data-ttu-id="de344-173">**/context:** *\<type>*</span><span class="sxs-lookup"><span data-stu-id="de344-173">**/context:** *\<type>*</span></span>|<span data-ttu-id="de344-174">데이터 컨텍스트 클래스의 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="de344-174">Specifies name of data context class.</span></span> <span data-ttu-id="de344-175">기본값: 데이터베이스 이름에서 파생됩니다.</span><span class="sxs-lookup"><span data-stu-id="de344-175">Default value: Derived from database name.</span></span>|  
|<span data-ttu-id="de344-176">**/entitybase:** *\<type>*</span><span class="sxs-lookup"><span data-stu-id="de344-176">**/entitybase:** *\<type>*</span></span>|<span data-ttu-id="de344-177">생성된 코드에서 엔터티 클래스의 기본 클래스를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="de344-177">Specifies the base class of the entity classes in the generated code.</span></span> <span data-ttu-id="de344-178">기본값: 엔터티에 기본 클래스가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="de344-178">Default value: Entities have no base class.</span></span>|  
|<span data-ttu-id="de344-179">**/pluralize**</span><span class="sxs-lookup"><span data-stu-id="de344-179">**/pluralize**</span></span>|<span data-ttu-id="de344-180">클래스 및 멤버 이름을 자동으로 복수 및 단수로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="de344-180">Automatically pluralizes or singularizes class and member names.</span></span><br /><br /> <span data-ttu-id="de344-181">이 옵션은 미국에서만 사용할 수 있습니다. 영어 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="de344-181">This option is available only in the U.S. English version.</span></span>|  
|<span data-ttu-id="de344-182">**/serialization:** *\<option>*</span><span class="sxs-lookup"><span data-stu-id="de344-182">**/serialization:** *\<option>*</span></span>|<span data-ttu-id="de344-183">serialize 가능한 클래스를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="de344-183">Generates serializable classes.</span></span><br /><br /> <span data-ttu-id="de344-184">유효한 *\<option>* : None, Unidirectional.</span><span class="sxs-lookup"><span data-stu-id="de344-184">Valid *\<option>*: None, Unidirectional.</span></span> <span data-ttu-id="de344-185">기본값: 없음</span><span class="sxs-lookup"><span data-stu-id="de344-185">Default value: None.</span></span><br /><br /> <span data-ttu-id="de344-186">자세한 내용은 [Serialization](../data/adonet/sql/linq/serialization.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="de344-186">For more information, see [Serialization](../data/adonet/sql/linq/serialization.md).</span></span>|  
  
 <span data-ttu-id="de344-187">**입력 파일**</span><span class="sxs-lookup"><span data-stu-id="de344-187">**Input File**</span></span>  
  
|<span data-ttu-id="de344-188">옵션</span><span class="sxs-lookup"><span data-stu-id="de344-188">Option</span></span>|<span data-ttu-id="de344-189">설명</span><span class="sxs-lookup"><span data-stu-id="de344-189">Description</span></span>|  
|------------|-----------------|  
|**\<input file>**|<span data-ttu-id="de344-190">SQL Server Express .mdf 파일, SQL Server Compact 3.5 .sdf 파일 또는 .dbml 중간 파일을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="de344-190">Specifies a SQL Server Express .mdf file, a SQL Server Compact 3.5 .sdf file, or a .dbml intermediate file.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="de344-191">설명</span><span class="sxs-lookup"><span data-stu-id="de344-191">Remarks</span></span>  

 <span data-ttu-id="de344-192">실제로 SqlMetal 기능에는 다음과 같은 두 단계가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="de344-192">SqlMetal functionality actually involves two steps:</span></span>  
  
- <span data-ttu-id="de344-193">데이터베이스의 메타데이터를 .dbml 파일에 추출</span><span class="sxs-lookup"><span data-stu-id="de344-193">Extracting the metadata of the database into a .dbml file.</span></span>  
  
- <span data-ttu-id="de344-194">코드 출력 파일 생성</span><span class="sxs-lookup"><span data-stu-id="de344-194">Generating a code output file.</span></span>  
  
     <span data-ttu-id="de344-195">적절한 명령줄 옵션을 사용하면 Visual Basic 또는 C# 소스 코드를 생성하거나 XML 매핑 파일을 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de344-195">By using the appropriate command-line options, you can produce Visual Basic or C# source code, or you can produce an XML mapping file.</span></span>  
  
 <span data-ttu-id="de344-196">.mdf 파일에서 메타데이터를 추출하려면 다른 모든 옵션 뒤에 .mdf 파일 이름을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="de344-196">To extract the metadata from an .mdf file, you must specify the name of the .mdf file after all other options.</span></span>  
  
 <span data-ttu-id="de344-197">**/server** 가 지정되어 있지 않으면 **localhost/sqlexpress** 로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="de344-197">If no **/server** is specified, **localhost/sqlexpress** is assumed.</span></span>  
  
 <span data-ttu-id="de344-198">Microsoft SQL Server 2005는 다음 조건 중 하나 이상이 true이면 예외를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="de344-198">Microsoft SQL Server 2005 throws an exception if one or more of the following conditions are true:</span></span>  
  
- <span data-ttu-id="de344-199">SqlMetal이 자기 자신을 호출하는 저장 프로시저의 추출을 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="de344-199">SqlMetal tries to extract a stored procedure that calls itself.</span></span>  
  
- <span data-ttu-id="de344-200">저장 프로시저, 함수 또는 뷰의 중첩 수준이 32를 초과합니다.</span><span class="sxs-lookup"><span data-stu-id="de344-200">The nesting level of a stored procedure, function, or view exceeds 32.</span></span>  
  
     <span data-ttu-id="de344-201">SqlMetal이 이 예외를 catch하여 경고로 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="de344-201">SqlMetal catches this exception and reports it as a warning.</span></span>  
  
 <span data-ttu-id="de344-202">입력 파일 이름을 지정하려면 이름을 명령줄에 입력 파일로 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="de344-202">To specify an input file name, add the name to the command line as the input file.</span></span> <span data-ttu-id="de344-203">**/conn** 옵션을 사용하여 연결 문자열에 파일 이름을 포함할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="de344-203">Including the file name in the connection string (using the **/conn** option) is not supported.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="de344-204">예</span><span class="sxs-lookup"><span data-stu-id="de344-204">Examples</span></span>  

 <span data-ttu-id="de344-205">추출된 SQL 메타데이터를 포함하는 .dbml 파일을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="de344-205">Generate a .dbml file that includes extracted SQL metadata:</span></span>  
  
 <span data-ttu-id="de344-206">**sqlmetal /server:myserver /database:northwind /dbml:mymeta.dbml**</span><span class="sxs-lookup"><span data-stu-id="de344-206">**sqlmetal /server:myserver /database:northwind /dbml:mymeta.dbml**</span></span>  
  
 <span data-ttu-id="de344-207">SQL Server Express를 사용하여 .mdf 파일에서 추출한 SQL 메타데이터를 포함하는 .dbml 파일을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="de344-207">Generate a .dbml file that includes extracted SQL metadata from an .mdf file by using SQL Server Express:</span></span>  
  
 <span data-ttu-id="de344-208">**sqlmetal /dbml:mymeta.dbml mydbfile.mdf**</span><span class="sxs-lookup"><span data-stu-id="de344-208">**sqlmetal /dbml:mymeta.dbml mydbfile.mdf**</span></span>  
  
 <span data-ttu-id="de344-209">SQL Server Express에서 추출한 SQL 메타데이터를 포함하는 .dbml 파일을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="de344-209">Generate a .dbml file that includes extracted SQL metadata from SQL Server Express:</span></span>  
  
 <span data-ttu-id="de344-210">**sqlmetal /server:.\sqlexpress /dbml:mymeta.dbml /database:northwind**</span><span class="sxs-lookup"><span data-stu-id="de344-210">**sqlmetal /server:.\sqlexpress /dbml:mymeta.dbml /database:northwind**</span></span>  
  
 <span data-ttu-id="de344-211">.dbml 메타데이터 파일에서 소스 코드를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="de344-211">Generate source code from a .dbml metadata file:</span></span>  
  
 <span data-ttu-id="de344-212">**sqlmetal /namespace:nwind /code:nwind.cs /language:csharp mymetal.dbml**</span><span class="sxs-lookup"><span data-stu-id="de344-212">**sqlmetal /namespace:nwind /code:nwind.cs /language:csharp mymetal.dbml**</span></span>  
  
 <span data-ttu-id="de344-213">SQL 메타데이터에서 직접 소스 코드를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="de344-213">Generate source code from SQL metadata directly:</span></span>  
  
 <span data-ttu-id="de344-214">**sqlmetal /server:myserver /database:northwind /namespace:nwind /code:nwind.cs /language:csharp**</span><span class="sxs-lookup"><span data-stu-id="de344-214">**sqlmetal /server:myserver /database:northwind /namespace:nwind /code:nwind.cs /language:csharp**</span></span>  
  
> [!NOTE]
> <span data-ttu-id="de344-215">Northwind 샘플 데이터베이스에 **/pluralize** 옵션을 사용하는 경우에는 다음 동작에 유의하세요.</span><span class="sxs-lookup"><span data-stu-id="de344-215">When you use the **/pluralize** option with the Northwind sample database, note the following behavior.</span></span> <span data-ttu-id="de344-216">SqlMetal이 테이블에 대해 행 형식 이름을 만들면 테이블 이름은 단수가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="de344-216">When SqlMetal makes row-type names for tables, the table names are singular.</span></span> <span data-ttu-id="de344-217">그리고 테이블에 대해 <xref:System.Data.Linq.DataContext> 속성을 만드는 경우에는 테이블 이름이 복수가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="de344-217">When it makes <xref:System.Data.Linq.DataContext> properties for tables, the table names are plural.</span></span> <span data-ttu-id="de344-218">이와 동시에 Northwind 샘플 데이터베이스의 테이블은 미리 복수로 지정되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de344-218">Coincidentally, the tables in the Northwind sample database are already plural.</span></span> <span data-ttu-id="de344-219">그러므로 이러한 작업이 실제로 수행되는지 확인할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="de344-219">Therefore, you do not see that part working.</span></span> <span data-ttu-id="de344-220">일반적으로는 데이터베이스 테이블 이름을 단수로 지정하지만 .NET에서는 컬렉션 이름을 복수로 지정하는 경우도 많습니다.</span><span class="sxs-lookup"><span data-stu-id="de344-220">Although it is common practice to name database tables singular, it is also a common practice in .NET to name collections plural.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de344-221">참조</span><span class="sxs-lookup"><span data-stu-id="de344-221">See also</span></span>

- [<span data-ttu-id="de344-222">방법: Visual Basic 또는 C#에서 개체 모델 생성</span><span class="sxs-lookup"><span data-stu-id="de344-222">How to: Generate the Object Model in Visual Basic or C#</span></span>](../data/adonet/sql/linq/how-to-generate-the-object-model-in-visual-basic-or-csharp.md)
- [<span data-ttu-id="de344-223">LINQ to SQL에서 코드 생성</span><span class="sxs-lookup"><span data-stu-id="de344-223">Code Generation in LINQ to SQL</span></span>](../data/adonet/sql/linq/code-generation-in-linq-to-sql.md)
- [<span data-ttu-id="de344-224">외부 매핑</span><span class="sxs-lookup"><span data-stu-id="de344-224">External Mapping</span></span>](../data/adonet/sql/linq/external-mapping.md)
