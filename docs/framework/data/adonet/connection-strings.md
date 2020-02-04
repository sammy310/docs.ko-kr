---
title: 연결 문자열
ms.date: 10/10/2018
ms.assetid: 745c5f95-2f02-4674-b378-6d51a7ec2490
ms.openlocfilehash: cb0b2831a22f3fe51dd7c5bfbe51e72f266a0003
ms.sourcegitcommit: 19014f9c081ca2ff19652ca12503828db8239d48
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "76980238"
---
# <a name="connection-strings-in-adonet"></a><span data-ttu-id="2caea-102">ADO.NET의 연결 문자열</span><span class="sxs-lookup"><span data-stu-id="2caea-102">Connection Strings in ADO.NET</span></span>

<span data-ttu-id="2caea-103">연결 문자열에는 데이터 공급자에서 데이터 소스에 매개 변수로 전달되는 초기화 정보가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2caea-103">A connection string contains initialization information that is passed as a parameter from a data provider to a data source.</span></span> <span data-ttu-id="2caea-104">데이터 공급자는 연결 문자열을 <xref:System.Data.Common.DbConnection.ConnectionString?displayProperty=nameWithType> 속성 값으로 받습니다.</span><span class="sxs-lookup"><span data-stu-id="2caea-104">The data provider receives the connection string as the value of the <xref:System.Data.Common.DbConnection.ConnectionString?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="2caea-105">공급자는 연결 문자열을 구문 분석 하 여 구문이 올바르고 키워드가 지원 되는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="2caea-105">The provider parses the connection string and ensures that the syntax is correct and that the keywords are supported.</span></span> <span data-ttu-id="2caea-106">그런 다음 <xref:System.Data.Common.DbConnection.Open?displayProperty=nameWithType> 메서드는 구문 분석 된 연결 매개 변수를 데이터 원본에 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="2caea-106">Then the <xref:System.Data.Common.DbConnection.Open?displayProperty=nameWithType> method passes the parsed connection parameters to the data source.</span></span> <span data-ttu-id="2caea-107">데이터 원본은 추가 유효성 검사를 수행 하 고 연결을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2caea-107">The data source performs further validation and establishes a connection.</span></span>

## <a name="connection-string-syntax"></a><span data-ttu-id="2caea-108">연결 문자열 구문</span><span class="sxs-lookup"><span data-stu-id="2caea-108">Connection string syntax</span></span>

<span data-ttu-id="2caea-109">연결 문자열은 세미콜론으로 구분 된 키/값 매개 변수 쌍의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="2caea-109">A connection string is a semicolon-delimited list of key/value parameter pairs:</span></span>

```csharp
keyword1=value; keyword2=value;
```

<span data-ttu-id="2caea-110">키워드는 대/소문자를 구분 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2caea-110">Keywords are not case-sensitive.</span></span> <span data-ttu-id="2caea-111">그러나 값은 데이터 원본에 따라 대/소문자를 구분 하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2caea-111">Values, however, may be case-sensitive, depending on the data source.</span></span> <span data-ttu-id="2caea-112">키워드와 값 모두 [공백 문자](https://en.wikipedia.org/wiki/Whitespace_character#Unicode)를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2caea-112">Both keywords and values may contain [whitespace characters](https://en.wikipedia.org/wiki/Whitespace_character#Unicode).</span></span> <span data-ttu-id="2caea-113">선행 및 후행 공백은 키워드 및 따옴표 붙지 않은 값에서 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2caea-113">Leading and trailing white space is ignored in keywords and unquoted values.</span></span>

<span data-ttu-id="2caea-114">값에 세미콜론, [유니코드 제어 문자](https://en.wikipedia.org/wiki/Unicode_control_characters)또는 선행 또는 후행 공백이 포함 된 경우 작은따옴표 또는 큰따옴표로 묶어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2caea-114">If a value contains the semicolon, [Unicode control characters](https://en.wikipedia.org/wiki/Unicode_control_characters), or leading or trailing white space, it must be enclosed in single or double quotation marks.</span></span> <span data-ttu-id="2caea-115">예를 들면 다음과 같습니다.:</span><span class="sxs-lookup"><span data-stu-id="2caea-115">For example:</span></span>

```csharp
Keyword=" whitespace  ";
Keyword='special;character';
```

<span data-ttu-id="2caea-116">묶는 문자는 포함 하는 값 내에서 발생 하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2caea-116">The enclosing character may not occur within the value it encloses.</span></span> <span data-ttu-id="2caea-117">따라서 작은따옴표를 포함 하는 값은 큰따옴표로만 묶을 수 있으며 그 반대의 경우도 마찬가지입니다.</span><span class="sxs-lookup"><span data-stu-id="2caea-117">Therefore, a value containing single quotation marks can be enclosed only in double quotation marks, and vice versa:</span></span>

```csharp
Keyword='double"quotation;mark';
Keyword="single'quotation;mark";
```

<span data-ttu-id="2caea-118">두 가지 문자를 함께 사용 하 여 바깥쪽 문자를 이스케이프할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2caea-118">You can also escape the enclosing character by using two of them together:</span></span>

```csharp
Keyword="double""quotation";
Keyword='single''quotation';
```

<span data-ttu-id="2caea-119">따옴표 자체와 등호는 이스케이프를 요구 하지 않으므로 다음 연결 문자열을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2caea-119">The quotation marks themselves, as well as the equals sign, do not require escaping, so the following connection strings are valid:</span></span>

```csharp
Keyword=no "escaping" 'required';
Keyword=a=b=c
```

<span data-ttu-id="2caea-120">각 값은 다음 세미콜론 또는 문자열의 끝까지 읽기 때문에 두 번째 예제의 값은 `a=b=c`되며 최종 세미콜론은 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="2caea-120">Since each value is read till the next semicolon or the end of string, the value in the latter example is `a=b=c`, and the final semicolon is optional.</span></span>

<span data-ttu-id="2caea-121">모든 연결 문자열은 위에서 설명한 것과 동일한 기본 구문을 공유 합니다.</span><span class="sxs-lookup"><span data-stu-id="2caea-121">All connection strings share the same basic syntax described above.</span></span> <span data-ttu-id="2caea-122">그러나 인식 되는 키워드 집합은 공급자에 따라 다르며 *ODBC*와 같은 이전 api의 연도 이상으로 발전 했습니다.</span><span class="sxs-lookup"><span data-stu-id="2caea-122">The set of recognized keywords depends on the provider, however, and has evolved over the years from earlier APIs such as *ODBC*.</span></span> <span data-ttu-id="2caea-123">*.NET Framework* data provider for *SQL Server* (`SqlClient`)는 이전 api의 많은 키워드를 지원 하지만 일반적으로 더 유연 하며 대부분의 일반적인 연결 문자열 키워드에 대 한 동의어를 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="2caea-123">The *.NET Framework* data provider for *SQL Server* (`SqlClient`) supports many keywords from older APIs, but is generally more flexible and accepts synonyms for many of the common connection string keywords.</span></span>

<span data-ttu-id="2caea-124">실수를 입력 하면 오류가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2caea-124">Typing mistakes can cause errors.</span></span> <span data-ttu-id="2caea-125">예를 들어 `Integrated Security=true` 유효 하지만 `IntegratedSecurity=true` 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="2caea-125">For example, `Integrated Security=true` is valid, but `IntegratedSecurity=true` causes an error.</span></span>

<span data-ttu-id="2caea-126">유효성 검사 사용자 입력에서 런타임에 수동으로 생성 된 연결 문자열은 문자열 삽입 공격에 취약 하 고 데이터 원본의 보안을 위협 합니다.</span><span class="sxs-lookup"><span data-stu-id="2caea-126">Connection strings constructed manually at run time from unvalidated user input are vulnerable to string-injection attacks and jeopardize security at the data source.</span></span> <span data-ttu-id="2caea-127">이러한 문제를 해결 하기 위해 *ADO.NET* 2.0에는 각 *.NET Framework* 데이터 공급자에 대 한 [연결 문자열 빌더가](connection-string-builders.md) 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="2caea-127">To address these problems, *ADO.NET* 2.0 introduced [connection string builders](connection-string-builders.md) for each *.NET Framework* data provider.</span></span> <span data-ttu-id="2caea-128">이러한 연결 문자열 작성기는 매개 변수를 강력한 형식의 속성으로 노출 하 고, 연결 문자열을 데이터 원본으로 보내기 전에 유효성을 검사할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="2caea-128">These connection string builders expose parameters as strongly-typed properties, and make it possible to validate the connection string before it's sent to the data source.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="2caea-129">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="2caea-129">In This Section</span></span>

<span data-ttu-id="2caea-130">[연결 문자열 작성기](connection-string-builders.md)</span><span class="sxs-lookup"><span data-stu-id="2caea-130">[Connection String Builders](connection-string-builders.md)</span></span>\
<span data-ttu-id="2caea-131">`ConnectionStringBuilder` 클래스를 사용하여 런타임에 유효한 연결 문자열을 구성하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2caea-131">Demonstrates how to use the `ConnectionStringBuilder` classes to construct valid connection strings at run time.</span></span>

<span data-ttu-id="2caea-132">[연결 문자열 및 구성 파일](connection-strings-and-configuration-files.md)</span><span class="sxs-lookup"><span data-stu-id="2caea-132">[Connection Strings and Configuration Files](connection-strings-and-configuration-files.md)</span></span>\
<span data-ttu-id="2caea-133">구성 파일에서 연결 문자열을 저장하고 검색하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2caea-133">Demonstrates how to store and retrieve connection strings in configuration files.</span></span>

<span data-ttu-id="2caea-134">[연결 문자열 구문](connection-string-syntax.md)</span><span class="sxs-lookup"><span data-stu-id="2caea-134">[Connection String Syntax](connection-string-syntax.md)</span></span>\
<span data-ttu-id="2caea-135">`SqlClient`, `OracleClient`, `OleDb` 및 `Odbc`에 대한 공급자별 연결 문자열을 구성하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="2caea-135">Describes how to configure provider-specific connection strings for `SqlClient`, `OracleClient`, `OleDb`, and `Odbc`.</span></span>

<span data-ttu-id="2caea-136">[연결 정보 보호](protecting-connection-information.md)</span><span class="sxs-lookup"><span data-stu-id="2caea-136">[Protecting Connection Information](protecting-connection-information.md)</span></span>\
<span data-ttu-id="2caea-137">데이터 소스 연결에 사용되는 정보를 보호하는 기법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2caea-137">Demonstrates techniques for protecting information used to connect to a data source.</span></span>

## <a name="see-also"></a><span data-ttu-id="2caea-138">참조</span><span class="sxs-lookup"><span data-stu-id="2caea-138">See also</span></span>

- [<span data-ttu-id="2caea-139">데이터 소스에 연결</span><span class="sxs-lookup"><span data-stu-id="2caea-139">Connecting to a Data Source</span></span>](/cpp/data/odbc/connecting-to-a-data-source)
- [<span data-ttu-id="2caea-140">ADO.NET 개요</span><span class="sxs-lookup"><span data-stu-id="2caea-140">ADO.NET Overview</span></span>](ado-net-overview.md)
